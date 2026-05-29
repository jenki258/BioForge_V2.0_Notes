#Blocks 
Infected crops are regular vanilla or mod crops (wheat, carrots, potatoes, etc.) that have been contaminated with a pathogen strain. The infection affects the crop's drops - infected crops have a chance to drop **contaminated items** that can spread the infection when eaten or planted.

### How crops become infected

| Method | Description |
|--------|-------------|
| **Contaminated Substrate** | Right‑click an inoculated Contaminated Substrate on a mature crop. The substrate is consumed, and the crop becomes infected. |
| **Placing infected seeds** | If you plant a seed that has a pathogen strain in its NBT (e.g., from an infected drop), the planted crop starts infected. |
| **Natural spread** | Infected mature crops can spread the infection to adjacent mature crops (randomly, based on random tick speed). |

- Only crops in the `bioforge:infectable_crops` block tag can be infected. This tag includes vanilla crops and any mod crops you add.
- A crop must be **mature** (its `age` property at maximum) to spread infection.

### What happens to infected crops

- **Drops** - When you break an infected crop, the event is cancelled and custom drops are generated.
  - The original crop drops (e.g., wheat, seeds) are calculated via `Block.getDrops()`.
  - Each drop has a chance to become **contaminated** based on the crop's `InfectionStrength` (a value between 0 and 1).
  - If the drop is contaminated, its NBT receives the **strain data** (without the colony ID - the `stripColonyId` method removes the colony UUID part, leaving only pathogen type, transmission types, and symptom values).
  - If the infection strength is low (≤0.0) or random chance fails, the drop is clean.
  - The crop block is replaced with air.

- **Eating contaminated food** - If you eat a food item that has a strain NBT and that strain includes `FOOD_BORNE` transmission type, you become infected with that pathogen (symptoms applied).

- **Planting infected seeds** - If you plant a seed that has a strain NBT, the newly placed crop block is immediately infected with that strain (via the `CropInfection` capability on the chunk).

### Spreading mechanics

- Every 20 ticks (1 second) on the server, the spread handler runs.
- For each loaded chunk, it checks all infected crop positions.
- For each infected mature crop, it attempts up to 3 times to spread to a random neighbouring crop (same Y level, within 1 block horizontally).
- The chance per attempt is `(randomTickSpeed * 2) / 4096` (scales with the game rule `randomTickSpeed`).
- If the neighbour is a mature, infectable crop and not already infected, it becomes infected with the same strain.

### How to detect infected crops

- There is **no visual difference** in the crop model - you cannot see that a crop is infected.
- You can use a **Swab** on the crop (right‑click while holding a clean swab) to sample the infection. If the crop is infected, the swab becomes contaminated with the strain, and you get a message: “Swab contaminated with infected crop strain.”
- Alternatively, you can break the crop and look at the drops - contaminated drops will have obfuscated NBT.

### Tag requirements

- `bioforge:infectable_crops` - block tag. Add any crop block that can be infected.
- The crop must have an `age` property (integer) to determine maturity. The handler finds the first property named “age” and assumes the max value is the mature stage.