#Blocks 
[[Infested Crop]]
[[Colony Core]]

Contaminated Substrate is a **colonisation starter** for environmental pathogens (Fungi and Bacteria). You inoculate it with a contaminated Swab, then place it as a block to create an underground colony. The substrate transforms into a Colony Core, which then spreads Microbial Mats and Infested Blocks within its radius.

### How to use it

| Action                                                                                                             | Result                                                                                                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Hold **clean Contaminated Substrate** in main hand and a **contaminated Swab** in off‑hand, then right‑click (air) | Inoculates the substrate - the swab's strain is transferred. Substrate becomes “inoculated”.                                                                                                                                 |
| Right‑click an **infectable crop** with an inoculated substrate                                                    | Infects that crop block (requires the crop to be `infectable_crops` tag). Substrate is consumed.                                                                                                                             |
| Right‑click on a **solid block** (anywhere) with inoculated substrate                                              | Places the substrate as a **block** (looks like a grey patch). After placement, it automatically converts into a **Colony Core** if the pathogen is environmental (Fungi or Bacteria). If not, it breaks and shows an error. |

- The substrate must be **inoculated** before it can be placed or used on crops.
- The swab is **not consumed** - only the substrate gains the strain (and the swab’s NBT is copied, but the swab remains contaminated? Actually reading: `replaceColonyId` generates a new colony UUID for the substrate, so the swab is unchanged and can be reused).
- The substrate’s strain data is obfuscated using `NbtObfuscator`.

### What happens when you place it

- When an inoculated substrate block is placed, it immediately checks the pathogen type from the strain.
- If the pathogen is **environmental** (`PathogenType.isEnvironmental()` - Fungi or Bacteria), the block replaces itself with a **Colony Core** block, and the Colony Core block entity receives the strain data.
- If the pathogen is **not environmental** (e.g., Virus, Parasite, Prion), the block breaks into air, and the placer receives a message: "This pathogen cannot form a colony! Only fungi and bacteria are environmental pathogens."

### Interaction with other systems

- **Swab** - Used to inoculate the substrate. After inoculation, the swab’s strain is copied (new colony ID generated), but the swab remains contaminated (you can use it again).
- **Crops** - Right‑clicking an inoculable crop with the substrate directly infects that crop (using the crop infection capability). The substrate is consumed.
- **Colony Core** - The placed substrate becomes a Colony Core, which then expands the colony via Microbial Mats and Infested Blocks.

### Visual & text feedback

- **Tooltip (item)** - Clean: “Empty - needs inoculation” + usage hint. Inoculated: “Inoculated - ready to place” (with dark red colour).
- **Messages** - “Substrate inoculated. You can now place it to start a colony.” / “Crop successfully infected!” / “This pathogen cannot form a colony! Only fungi and bacteria are environmental pathogens.” / “This crop is already infected!”