# Pathogen Reagent

#BioForge #BioForge_V2_0 #Build_V0_54T #Item #Medicine #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This medical item changes infection risk, symptoms, strain parameters, or treatment outcomes.
It reveals a broad pathogen class without exposing full strain data.
## Obtaining

- **crafting shapeless** (`pathogen_reagent.json`): [[Laboratory Glassware]], [[Sterile Filter]], `#bioforge:ingredients/minecraft/fermented_spider_eye`, `#bioforge:ingredients/minecraft/glowstone_dust`, `#bioforge:ingredients/minecraft/quartz` → 1 × Pathogen Reagent.
- **[[Pharma Mixer]]** (`pathogen_reagent.json`): [[Laboratory Glassware]], [[Sterile Filter]], `#bioforge:ingredients/minecraft/fermented_spider_eye`, `#bioforge:ingredients/minecraft/glowstone_dust`, [[Activated Carbon]] → 2 × Pathogen Reagent in 200 ticks, plus [[Laboratory Waste]].

## Function

- It reveals a broad pathogen class without exposing full strain data.
- **description:** Identifies the pathogen class in infected blood
- **negative:** No pathogen detected

## Progression connections

- Primarily consumed or interpreted by its linked special interaction rather than ordinary crafting.

## Stored data and safety

- Program, strain, target, quality, and research payloads are server-authoritative and use BioForge biological-data helpers.

## Registry and pack integration

- Registry ID: `bioforge:pathogen_reagent`.
- No dedicated BioForge ingredient tag is currently bundled.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

