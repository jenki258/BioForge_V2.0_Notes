#Blocks
The Sporocarp is a **fruiting body** that forms from a fully grown (stage 4) **Fungal** Microbial Mat. It acts as a spore dispersal structure - when exposed to sunlight, it bursts open and spreads new Microbial Mats in a radius around it. Sporocarps also periodically regenerate nearby Mats.

### How it is created

- A **Fungal** Microbial Mat at growth stage 4 will attempt to transform into a Sporocarp if there is **no other Sporocarp within 10 blocks** (checked via `hasNearbySporocarp`).
- When it transforms, the Sporocarp block entity receives the same strain data as the parent Mat (pathogen type, colony ID, infection types, symptoms).
- The Mat block is replaced by the Sporocarp block.

### Bursting (spore dispersal)

- When the Sporocarp receives a **random tick** and the **sky light level** at its position is ≥ 10 (i.e., exposed to sunlight), it triggers a **burst**.
- Burst effect:
  - Spawns **5‑10** new Microbial Mats within a **5‑block radius** (in any direction, including vertical).
  - Each target position must be air and have a valid organic substrate below (tag `bioforge:substrate/organic`).
  - The new Mats are placed at growth stage 0 and linked to the same colony core.
- After bursting, the Sporocarp block is **destroyed** (does not drop itself).

### Regeneration (periodic growth boost)

- The Sporocarp has an **internal cooldown counter** (regenCooldown) that increments every tick.
- Every **1200 ticks (60 seconds)**, if the Sporocarp is still alive and has a valid core, it triggers **regeneration**:
  - Scans all blocks within a 10‑block radius.
  - Finds any Microbial Mat belonging to the same colony (matching colony ID).
  - Increases the growth stage of those Mats by 1 (up to stage 4).
- This allows the Sporocarp to “nurture” nearby Mats, accelerating their development.

### How to harvest / sample

- Right‑click the Sporocarp with a **clean Swab** → you obtain a contaminated swab with the Sporocarp’s strain (message: “Swab contaminated with sporocarp strain”).
- The Sporocarp is **not consumed** by swabbing - you can take multiple samples.

### Death & removal

- If the Sporocarp is exposed to sunlight (sky light ≥ 10), it will burst and be destroyed (as described above).
- If the colony core is destroyed or the Sporocarp moves out of colony radius, it will eventually die (though the burst mechanic is the primary removal method).
- There is no Necrotic Patch stage for Sporocarps - they vanish in a puff of spores.

### Pathogen restrictions

- Only **Fungi** can produce Sporocarps. The code explicitly checks `pathogen == PathogenType.FUNGI` before allowing the Mat → Sporocarp conversion.
- Other pathogens (Bacteria, Virus, etc.) will never form Sporocarps, even if their Mats reach stage 4.

### Visual & text feedback

- Swabbing gives a chat message.
- Bursting creates a small explosion of new Mats (no sound effect is specified in the code, but the block is destroyed).