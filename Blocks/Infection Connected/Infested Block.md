#Blocks 
Infested Block is the **underground form** of the colony. It replaces organic substrate blocks (dirt, grass, etc.) when the colony spreads beneath the surface. Infested Blocks slowly grow, generate resources for the colony core, and can spawn Microbial Mats on the surface above them. They are the "root system" of the colony.

### How it is created

- **From Microbial Mat** - When a Microbial Mat reaches growth ≥ 2, it has a 15% chance per random tick to convert the block **below** it into an Infested Block. This costs 2 resources from the core and increments the core’s infested block count.
- **Underground spread from another Infested Block** - An existing Infested Block can spread to neighbouring organic substrate blocks (including directly below, or horizontally at the same level) via `attemptUndergroundSpread`. This costs 1 resource from the core and consumes the original substrate block state (stored as `hostState`).

When created, the Infested Block stores:
- The original `hostState` (the block it replaced, e.g., dirt, grass, farmland) - used to revert when the colony dies.
- The strain data (pathogen type, colony ID, symptoms).
- A reference to the colony core position.

### Growth stages

Infested Blocks have a `growth` property (0-4). Growth chance per random tick depends on the pathogen:

| Pathogen | Growth chance |
| -------- | ------------- |
| Fungi    | 30%           |
| Bacteria | 15%           |

- Growth does **not** consume resources - it is free.
- Higher growth stages increase the chance of spreading and spawning surface Mats.

### Spreading behaviour

Every 3 ticks (on average), an Infested Block may attempt to spread underground:

1. **70% chance to spread downward** - converts the block directly below into another Infested Block (if it is a valid organic substrate).
2. Otherwise, picks a random neighbouring block (dx, dz in -1..1, dy = -1 or 0) and tries to convert it.

Spreading costs **1 resource** from the core and increments the core’s infested count. The new Infested Block stores the original block state it replaced.

### Surface Mat spawning

- When an Infested Block reaches growth ≥ 2, it has a **10% chance per random tick** to spawn a **Microbial Mat** on the surface above it.
- The target must be air, and the block below (the Infested Block itself) is considered a valid substrate.
- The spawned Mat starts at growth stage 0 and is linked to the same colony core.
- This is how the colony “breaks through” to the surface.

### Resource generation

- Every 5 ticks (on average), each Infested Block adds **1 resource** to the colony core (`generateResources`).
- This provides a steady income for the core to fund further expansion.

### Death (reversion)

If an Infested Block finds itself **outside the colony radius** (distance > colonyRadius from the core), it **dies**:

- It reverts to its original `hostState` (e.g., dirt, grass, farmland) - stored when the block was created.
- It decrements the core’s infested block count.
- It does **not** drop any items.

### Entity interaction

- **Walking on Infested Block** - Entities receive Slowness I (same as Microbial Mat). Applied via `MatSlownessHandler`.
- **Swabbing** - Right‑click with a clean Swab to obtain a contaminated swab with the colony strain (message: “Swab contaminated with microbial mat strain”). The block is not consumed.
- **Infection spread to entities** - If the pathogen is **Fungi**, standing on an Infested Block can infect the entity (see `stepOn` method). The infection strength of the block is compared to the entity’s existing infection, and the stronger strain may take over.

### Visual & colour

- Infested Block uses the same colour tinting as other infection blocks, based on pathogen type (with random variation).
- The block model is a full cube (16×16×16), but the original texture is replaced by a custom model (the actual visual appearance depends on the resource pack - in the code there is no specific texture reference, just a generic block).