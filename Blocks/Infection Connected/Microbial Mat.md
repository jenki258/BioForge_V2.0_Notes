#Blocks
Microbial Mat is a surface‑covering growth that spreads from a Colony Core. It is the first visible sign of an underground colony, appearing on top of organic substrates (dirt, grass, etc. (It right now uses blocks that sculk can spread on too)). Mats grow over time, slow down entities walking on them, and can eventually turn into Infested Blocks (underground) or Sporocarps (for Fungi).

### How it is created

- **From Colony Core** - The core randomly places Microbial Mats on air blocks above valid substrates within its radius (costs 1 resource per attempt).
- **From Infested Blocks** - An Infested Block (underground) can occasionally spawn a Mat on the surface above it.
- **From Sporocarp burst** - When a Sporocarp bursts, it can create new Mats nearby.

When a Mat is placed, it receives the same strain data as its parent core, including pathogen type, colony ID, and all symptom values.

### Growth stages

Mats have a `growth` property (0‑4). Growth chance depends on the pathogen:

| Pathogen | Growth chance per random tick |
|----------|------------------------------|
| Fungi    | 30%                          |
| Bacteria | 15%                          |
| Parasite | 5%                           |
| Prion    | 2%                           |
| Virus    | 0% (does not form Mats)      |

- Growth consumes **1 resource** from the core (via `consumeResources`).
- When growth reaches stage 4 and the pathogen is **Fungi**, the Mat tries to convert into a **Sporocarp** (if no other Sporocarp is within 10 blocks). If a Sporocarp already exists nearby, the Mat remains at stage 4.

### Spreading (horizontal expansion)

- Mats with growth ≥ 1 can spread to adjacent air blocks (on the same level or up one block).
- Spread chance per random tick:
  - Fungi: 25%
  - Bacteria: 10%
  - Parasite: 4%
  - Prion: 1%
- Spread costs **1 resource** from the core.
- The new Mat is placed at growth stage 0 and linked to the same core.

### Conversion to Infested Block

- When a Mat reaches growth ≥ 2, it has a 15% chance per random tick to convert the **block below** it (the substrate) into an **Infested Block**.
- This costs **2 resources** from the core and increments the core’s infested block count.
- The new Infested Block inherits the strain and stores the original substrate block state (so it can revert when the colony dies).

### Sunlight sensitivity (non‑Fungi)

- For pathogens that are **not Fungi**, the Mat will die (turn into Necrotic Patch) if exposed to sky light ≥ 10.
- Fungi are tolerant of light and can survive on the surface.

### Entity interaction

- **Walking on Mat** - Entities receive Slowness I while standing on a Microbial Mat (or Infested Block).
- **Swabbing** - Right‑click a Mat with a clean Swab to obtain a contaminated swab with the colony’s strain (message: “Swab contaminated with microbial mat strain”). The Mat is **not consumed**.

### Death (Necrotic Patch)

- If a Mat is outside the colony’s radius (distance > colony radius from core), it turns into a **Necrotic Patch** block.
- A Necrotic Patch slowly decays (5% chance per random tick) and eventually disappears (turns to air).

### Visual & colour

- Mats have a base colour depending on the pathogen (via `PetriDishColorHandler`):
  - Fungi: Yellowish (`0xFFCCCC66`)
  - Bacteria: Greenish (`0xFF66CC66`)
  - Virus: Reddish (`0xFFCC6666`)
  - Parasite: Purple (`0xFFCC66CC`)
  - Prion: Light grey (`0xFFCCCCCC`)
- Each mat has a slight random colour variation based on its position or colony UUID.