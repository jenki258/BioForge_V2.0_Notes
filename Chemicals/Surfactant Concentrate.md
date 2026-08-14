# Surfactant Concentrate

#BioForge #BioForge_V0_54T #Item #Chemicals #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This chemical or processed reagent occupies a defined step in BioForge's sterile production chain.

## Obtaining

- **crafting shapeless** (`surfactant_concentrate.json`): `#bioforge:ingredients/minecraft/slime_ball`, [[Ethanol]], [[Sterilizing Solution]], `#bioforge:ingredients/minecraft/honey_bottle` → 2 × Surfactant Concentrate.
- **[[Chemical Synthesizer]]** (`surfactant.json`): `#bioforge:ingredients/minecraft/slime_ball`, [[Ethanol]], `#bioforge:ingredients/minecraft/honey_bottle` → 3 × Surfactant Concentrate in 180 ticks.

## Function

- Its behavior is defined by its recipe role and linked workstation or equipment system.

## Progression connections

- Used to produce: [[Decontamination Flask]].

## Stored data and safety

- It carries no readable biological payload by default, although contaminated ingredients can still propagate a strain.

## Registry and pack integration

- Registry ID: `bioforge:surfactant_concentrate`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/surfactant_concentrate`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

