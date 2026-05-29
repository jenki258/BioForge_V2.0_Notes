#Blocks

The Petri Dish is a culture container for growing pathogen samples collected with a Swab. It allows you to multiply a strain, then harvest it with a fresh swab to transfer the culture elsewhere. The dish can be placed as a block or held as an item; both work similarly.

### How to use it

| Action                                                                                            | Result                                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Right‑click a **clean Petri Dish** (item) while holding a **contaminated Swab** in the other hand | Inoculates the dish - the swab’s strain is transferred to the dish. The dish becomes “inoculated”.                                                                                                                                    |
| Right‑click a **placed Petri Dish** (block) with a contaminated Swab                              | Same as above - inoculates the block.                                                                                                                                                                                                 |
| Wait (random ticks)                                                                               | The culture grows over time. Each growth stage changes the block model (stage 0-4).                                                                                                                                                   |
| Right‑click a **fully grown dish** (stage ≥3) with a **clean Swab**                               | Harvests the culture - the swab becomes contaminated with the dish’s strain. If stage was 3, the dish resets to stage 0 (can be used again). If stage 4, it might behave similarly (code shows stage 3 resets, stage 4 likely stays). |
| Break the dish (block)                                                                            | Drops the dish item with the current growth stage and strain data preserved.                                                                                                                                                          |

### Growth stages

- **Stage 0** - Inoculated but no visible growth.
- **Stage 1-2** - Intermediate growth (faster for bacteria/fungi, slower for prions).
- **Stage 3** - Fully mature. Harvesting resets the dish to stage 0 but keeps the strain (you can re‑inoculate later).
- **Stage 4** - Overgrown (code allows up to stage 4). Harvesting behaviour from stage 4 is similar (resets to 0? The code only checks `growthStage >= 3` for harvest, and after harvest if `growthStage == 3` it clears; stage 4 might remain inoculated? The logic is slightly unclear, but effectively you can harvest multiple times).

Growth chance depends on pathogen type (from the strain data):
- Bacteria: 30% per random tick
- Fungi: 25%
- Virus: 20%
- Parasite: 15%
- Prion: 8%

### Interaction with other systems

- **Swab** - Primary tool for inoculating and harvesting.
- **Block colour** - The dish’s culture has a tint based on pathogen type (green for bacteria, red for virus, etc.) with slight random variation per position.

### Visual & text feedback

- **Tooltip (item)** - Empty: “Empty dish” + usage hint. Inoculated: “Culture growing” + “Growth stage: X”.
- **Messages** - “Petri dish inoculated”, “Sample collected from dish”.
- **Block model** - Changes with growth stage (different texture/model per stage).