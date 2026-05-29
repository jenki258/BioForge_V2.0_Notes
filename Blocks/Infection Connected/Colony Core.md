#Blocks
[[Microbial Mat]]
[[Sporocarp]]
[[Infested Block]]
The Colony Core is the **heart of an underground pathogen colony**. It is created automatically when you place an inoculated Contaminated Substrate block (only for environmental pathogens - Fungi or Bacteria). The core consumes resources to spread Microbial Mats and Infested Blocks within its territory, acting as a centralised hive mind for the colony.

### How it is created

- Place an **inoculated Contaminated Substrate** on any solid block.
- If the pathogen is **environmental** (Fungi or Bacteria), the substrate block immediately transforms into a **Colony Core** block, and the strain data is transferred to the core’s block entity.
- If the pathogen is not environmental (Virus, Parasite, Prion), the block breaks and a message appears (“This pathogen cannot form a colony…”).

### Core properties

| Property                | Default            | Description                                                                                                      |
| ----------------------- | ------------------ | ---------------------------------------------------------------------------------------------------------------- |
| **Resources**           | 25                 | The core starts with 25 units. It gains resources from infected blocks/mats when they die. Max 5000.             |
| **Colony radius**       | 20 blocks          | The core can only influence blocks within this distance (Chebyshev distance? Actually `closerThan` - Euclidean). |
| **Max Infested Blocks** | 100                | Maximum number of `InfestedBlock` blocks that can exist in the colony (counted by the core).                     |
| **Pathogen & strain**   | From the substrate | Stores the full strain data (obfuscated), including pathogen type, transmission types, and symptom values.       |

### Resource system

- **Gaining resources**: When an Infested Block or Microbial Mat is destroyed (or dies), the core gains 10 resources per death (see `InfestedBlockDeathHandler`).
- **Spending resources**:
  - Placing a new Microbial Mat costs **1 resource** (per attempt, with 1‑3 attempts per random tick).
  - Converting a Microbial Mat into an Infested Block (underground spread) costs **2 resources**.
- The core’s resource count is saved and synchronised with the block entity.

### Spreading behaviour

Every **random tick** (not every tick), the Colony Core attempts to spread:

1. **1‑3 attempts** per random tick.
2. For each attempt, it consumes 1 resource.
3. It picks a random target position within 3 blocks horizontally and 0‑1 blocks vertically (50% chance dy=1, else dy=0).
4. If the target is **air** and the block **below** it is a valid substrate (tag `bioforge:substrate/organic`), it places a **Microbial Mat** block (growth stage 0) and links it to the core.
5. The Microbial Mat block entity receives the same strain data and core position.

The spread is **constrained** by the colony radius - any mat or infested block outside the radius will die and revert to its host state (or dirt).

### Other core functions

- **Tracks infested block count** - increments when a new Infested Block is created (via Microbial Mat conversion), decrements when an Infested Block dies.
- **Can be swabbed** - Right‑clicking the core with a clean Swab gives you a contaminated swab with the colony’s strain (message: “Swab contaminated with colony core strain”).
- **Supports only environmental pathogens** - The core will only function if the pathogen is Fungi or Bacteria. Other pathogens cannot form a colony.

### Interaction with other blocks

- **Microbial Mats** - The core spawns them on valid substrates. Mats grow over time and can convert into Infested Blocks or Sporocarps (if Fungi).
- **Infested Blocks** - Created when a Microbial Mat grows enough and the core spends resources. They also generate resources for the core when they die.
- **Necrotic Patch** - When a Microbial Mat is outside the colony radius or exposed to sunlight (non‑Fungi), it turns into a Necrotic Patch, which slowly decays to air.

### Visual & text feedback

- The core block has a purple colour (`MapColor.COLOR_PURPLE`).
- There is **no GUI** or overlay for resources - you cannot see resource count in‑game without commands.
- Swabbing the core gives a chat message: “Swab contaminated with colony core strain.”