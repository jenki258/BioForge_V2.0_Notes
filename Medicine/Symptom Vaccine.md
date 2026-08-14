# Symptom Vaccine

#BioForge #BioForge_V0_54T #Item #Medicine #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This medical item changes infection risk, symptoms, strain parameters, or treatment outcomes.
It adds or removes one programmed clinical parameter from the matching infection.
## Obtaining

- **crafting shapeless** (`symptom_vaccine.json`): [[Strain Vaccine]], `#bioforge:ingredients/minecraft/glistering_melon_slice`, `#bioforge:ingredients/minecraft/spider_eye`, [[Sterile Polymer Sheet]] → 1 × Symptom Vaccine.

## Function

- It adds or removes one programmed clinical parameter from the matching infection.

## Progression connections

- Primarily consumed or interpreted by its linked special interaction rather than ordinary crafting.

## Stored data and safety

- Program, strain, target, quality, and research payloads are server-authoritative and use BioForge biological-data helpers.

## Registry and pack integration

- Registry ID: `bioforge:symptom_vaccine`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/symptom_vaccine`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

