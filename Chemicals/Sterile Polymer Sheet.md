# Sterile Polymer Sheet

#BioForge #BioForge_V0_54T #Item #Chemicals #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This chemical or processed reagent occupies a defined step in BioForge's sterile production chain.

## Obtaining

- **smelting** (`sterile_polymer_sheet.json`): process input → 1 × Sterile Polymer Sheet.
- **[[Sterilization Chamber]]** (`sterile_polymer_sheet.json`): [[Polymer Resin]] → 1 × Sterile Polymer Sheet in 160 ticks.

## Function

- Its behavior is defined by its recipe role and linked workstation or equipment system.

## Progression connections

- Used to produce: [[Blood Slide]], [[CRISPR gRNA Cartridge]], [[Gene Imprint]], [[Laboratory Glassware]], [[Live Culture Vial]], [[Mutation Vaccine]], [[Petri Dish]], [[Random Mutation Vaccine]], [[Sealed Biofabric]], [[Sterile Filter]], [[Symptom Vaccine]], [[Syringe]], [[Transmission Vaccine]], [[Test Tube]].

## Stored data and safety

- It carries no readable biological payload by default, although contaminated ingredients can still propagate a strain.

## Registry and pack integration

- Registry ID: `bioforge:sterile_polymer_sheet`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/sterile_polymer_sheet`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]
