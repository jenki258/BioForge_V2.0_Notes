# Sterile Filter

#BioForge #BioForge_V2_0 #Build_V0_54T #Item #Materials #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This engineered material is a progression component for workstations, medical hardware, protection, or sterile processing.

## Obtaining

- **crafting shaped** (`sterile_filter.json`): [[Sterile Polymer Sheet]], `#bioforge:ingredients/minecraft/paper`, [[Activated Carbon]] → 2 × Sterile Filter.
- **[[Sterilization Chamber]]** (`sterile_filter.json`): [[Activated Carbon]] → 1 × Sterile Filter in 140 ticks.

## Function

- Its behavior is defined by its recipe role and linked workstation or equipment system.

## Progression connections

- Used to produce: [[Activated Biofilter]], [[Air Vent]], [[Area Contamination Scanner]], [[Strain Vaccine]], [[Contaminated Substrate]], [[Gene Imprint]], [[Incubator]], [[Pathogen Reagent]], [[Visibility Reagent]].

## Stored data and safety

- It carries no readable biological payload by default, although contaminated ingredients can still propagate a strain.

## Registry and pack integration

- Registry ID: `bioforge:sterile_filter`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/sterile_filter`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

