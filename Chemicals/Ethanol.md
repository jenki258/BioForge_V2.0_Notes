# Ethanol

#BioForge #BioForge_V2_0 #Build_V0_54T #Item #Chemicals #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This chemical or processed reagent occupies a defined step in BioForge's sterile production chain.
It is made from Wine Must and can clean compatible empty medical tools.
## Obtaining

- **crafting shapeless** (`ethanol.json`): `#bioforge:ingredients/minecraft/water_bucket`, `#bioforge:ingredients/minecraft/glass_bottle`, `#bioforge:ingredients/minecraft/sugar`, [[Wine Must]] → 2 × Ethanol.
- **[[Chemical Synthesizer]]** (`ethanol.json`): `#bioforge:ingredients/minecraft/potion`, `#bioforge:ingredients/minecraft/sugar`, [[Wine Must]] → 3 × Ethanol in 120 ticks.

## Function

- It is made from Wine Must and can clean compatible empty medical tools.
- **cleaned:** Culture Vial cleaned!
- **syringe cleaned:** Syringe infection wiped clean.
- **syringe not empty:** Syringe must be empty of blood first.
- **tooltip.clean vial:** Cleans Dirty Culture Vials
- **tooltip.clean syringe:** Removes infection from empty Syringes
- **tooltip.usage:** Hold the item to clean in your other hand and right‑click

## Progression connections

- Used to produce: [[Chemical-Resistant Coating]], [[Sterilizing Solution]], [[Surfactant Concentrate]].

## Stored data and safety

- It carries no readable biological payload by default, although contaminated ingredients can still propagate a strain.

## Registry and pack integration

- Registry ID: `bioforge:ethanol`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/ethanol`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]
# 2.1 update

Ethanol coating protects supported BioForge blocks from pathogen contamination and creates a short-range protection halo around the coated block. The wiki should clearly distinguish this from the active decontamination flask and from the passive Air Vent.
