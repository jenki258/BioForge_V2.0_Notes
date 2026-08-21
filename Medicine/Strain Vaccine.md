# Strain Vaccine

#BioForge #BioForge_V2_0 #Build_V0_54T #Item #Medicine #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This medical item changes infection risk, symptoms, strain parameters, or treatment outcomes.
This exact-strain syringe attempts a cure and grants temporary immunity; quality, host fit, strength, and cure resistance affect it.
## Obtaining

- **crafting shapeless** (`blank_vaccine.json`): [[Laboratory Glassware]], [[Nutrient Medium]], [[Sterile Filter]], [[Black Steel Nugget]], `#bioforge:ingredients/minecraft/golden_carrot` → 1 × Strain Vaccine.

## Function

- This exact-strain syringe attempts a cure and grants temporary immunity; quality, host fit, strength, and cure resistance affect it.
- **empty:** Unconfigured vaccine
- **empty hint:** Use as the carrier in a Vaccine Maker.
- **use:** Right-click yourself or use directly on another living entity
- **match hint:** Compares pathogen, transmission, symptoms, and mutations
- **assay hint:** Use with a blood-filled tube to prepare a hidden efficacy assay
- **immunity hint:** Successful use grants temporary immunity to this exact strain
- **strength hint:** Stronger infections are harder to cure
- **failure hint:** A failed dose may select for vaccine defense

## Progression connections

- Used to produce: [[Mutation Vaccine]], [[Random Mutation Vaccine]], [[Symptom Vaccine]], [[Transmission Vaccine]], [[Vaccine Maker]].

## Stored data and safety

- Program, strain, target, quality, and research payloads are server-authoritative and use BioForge biological-data helpers.

## Registry and pack integration

- Registry ID: `bioforge:vaccine`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/vaccine`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

