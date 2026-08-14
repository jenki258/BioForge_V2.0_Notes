# Sterilizing Solution

#BioForge #BioForge_V0_54T #Item #Chemicals #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This chemical or processed reagent occupies a defined step in BioForge's sterile production chain.

## Obtaining

- **crafting shapeless** (`sterilizing_solution.json`): [[Ethanol]], [[Sulfuric Acid]], `#bioforge:ingredients/minecraft/water_bucket`, `#bioforge:ingredients/minecraft/glass_bottle` → 2 × Sterilizing Solution.
- **[[Chemical Synthesizer]]** (`sterilizing_solution.json`): [[Ethanol]], [[Sulfuric Acid]], `#bioforge:ingredients/minecraft/potion` → 3 × Sterilizing Solution in 140 ticks.

## Function

- Its behavior is defined by its recipe role and linked workstation or equipment system.

## Progression connections

- Used to produce: [[Anti-A Reagent]], [[Anti-B Reagent]], [[Anti-D Reagent]], [[Decontamination Flask]], [[Hardened Needle]], [[Black Steel Needle]], [[Neutralizing Agent]], [[Nutrient Medium]], [[Petri Dish]], [[Sterile Rubber]], [[Surfactant Concentrate]], [[Swab]], [[Symptom Suppressant Tablet]], [[Syringe]], [[Thermal Gel]], [[Wipe]].

## Stored data and safety

- It carries no readable biological payload by default, although contaminated ingredients can still propagate a strain.

## Registry and pack integration

- Registry ID: `bioforge:sterilizing_solution`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/sterilizing_solution`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

