# Agar Powder

#BioForge #BioForge_V2_0 #Build_V0_54T #Item #Chemicals #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This chemical or processed reagent occupies a defined step in BioForge's sterile production chain.

## Obtaining

- **crafting shapeless** (`agar_powder.json`): `#bioforge:ingredients/minecraft/dried_kelp`, `#bioforge:ingredients/minecraft/bone_meal`, `#bioforge:ingredients/minecraft/sugar` → 3 × Agar Powder.
- **[[Pharma Mixer]]** (`agar_powder.json`): `#bioforge:ingredients/minecraft/dried_kelp`, `#bioforge:ingredients/minecraft/bone_meal`, `#bioforge:ingredients/minecraft/sugar` → 4 × Agar Powder in 100 ticks, plus [[Laboratory Waste]].

## Function

- Its behavior is defined by its recipe role and linked workstation or equipment system.

## Progression connections

- Used to produce: [[Contaminated Substrate]], [[Nutrient Medium]].

## Stored data and safety

- It carries no readable biological payload by default, although contaminated ingredients can still propagate a strain.

## Registry and pack integration

- Registry ID: `bioforge:agar_powder`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/agar_powder`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

