# Symptom Suppressant Tablet

#BioForge #BioForge_V0_54T #Item #Medicine #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This medical item changes infection risk, symptoms, strain parameters, or treatment outcomes.
It temporarily suppresses one programmed penalty but does not cure, remove, or conceal the infection.
## Obtaining

- **crafting shapeless** (`symptom_tablet.json`): `#bioforge:ingredients/minecraft/sugar`, [[Sterilizing Solution]], [[Neutralizing Agent]], `#bioforge:ingredients/minecraft/glass_bottle` → 4 × Symptom Suppressant Tablet.

## Function

- It temporarily suppresses one programmed penalty but does not cure, remove, or conceal the infection.
- **blank:** Unprogrammed symptom tablet
- **vaccine maker:** Program with an identified symptom Gene Imprint in the Vaccine Maker
- **not cure:** Suppresses a penalty; does not cure or hide the symptom

## Progression connections

- Primarily consumed or interpreted by its linked special interaction rather than ordinary crafting.

## Stored data and safety

- Program, strain, target, quality, and research payloads are server-authoritative and use BioForge biological-data helpers.

## Registry and pack integration

- Registry ID: `bioforge:symptom_tablet`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/symptom_tablet`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

