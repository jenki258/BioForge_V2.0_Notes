# Cas PAM Module

#BioForge #BioForge_V2_0 #Build_V0_54T #Item #Research_Items #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This research item carries or supports biological knowledge that must be earned through the laboratory workflow.
The selected Cas/PAM profile changes the sequence constraints accepted by the Vaccine Maker. Bundled profiles are SpCas9, Cas12a, and Cas13d.
## Obtaining

- **crafting shaped** (`cas_module.json`): [[Black Steel Plate]], [[Optical Lens]], `#bioforge:ingredients/minecraft/quartz`, [[Precision Mechanism]], `#bioforge:ingredients/minecraft/redstone`, `#bioforge:ingredients/minecraft/diamond` → 1 × Cas PAM Module.

## Function

- The selected Cas/PAM profile changes the sequence constraints accepted by the Vaccine Maker. Bundled profiles are SpCas9, Cas12a, and Cas13d.
- **pathogens.any:** any
- **tooltip:** An incompatible nuclease cannot synthesize this strain's vaccine
- **cycle:** Right-click to cycle the loaded Cas/PAM definition

## Progression connections

- Primarily consumed or interpreted by its linked special interaction rather than ordinary crafting.

## Stored data and safety

- Program, strain, target, quality, and research payloads are server-authoritative and use BioForge biological-data helpers.

## Registry and pack integration

- Registry ID: `bioforge:cas_module`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/cas_module`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

