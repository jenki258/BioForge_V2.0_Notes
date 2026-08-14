# Random Mutation Vaccine

#BioForge #BioForge_V0_54T #Item #Medicine #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This medical item changes infection risk, symptoms, strain parameters, or treatment outcomes.
It adds one random compatible mutation to a matching infection and uses the mutation slot-machine reveal.
## Obtaining

- **crafting shapeless** (`random_mutation_vaccine.json`): [[Strain Vaccine]], `#bioforge:ingredients/minecraft/echo_shard`, `#bioforge:ingredients/minecraft/chorus_fruit`, [[Sterile Polymer Sheet]] → 1 × Random Mutation Vaccine.

## Function

- It adds one random compatible mutation to a matching infection and uses the mutation slot-machine reveal.
- **encoded:** Experimental mutagenic dose
- **warning:** Introduces one unknown compatible mutation into a matching active infection

## Progression connections

- Primarily consumed or interpreted by its linked special interaction rather than ordinary crafting.

## Stored data and safety

- Program, strain, target, quality, and research payloads are server-authoritative and use BioForge biological-data helpers.

## Registry and pack integration

- Registry ID: `bioforge:random_mutation_vaccine`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/random_mutation_vaccine`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

