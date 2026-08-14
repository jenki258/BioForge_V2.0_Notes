# Area Contamination Scanner

#BioForge #BioForge_V0_54T #Item #Tools #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This instrument performs one field or laboratory task and complements the other diagnostic tools.
Right-click to scan nearby contaminated surfaces and airborne reservoirs. It reports hazard level without revealing the strain and briefly marks affected positions.
## Obtaining

- **crafting shaped** (`area_contamination_scanner.json`): [[Optical Lens]], [[Black Steel Plate]], [[Biomedical Processor]], [[Sterile Filter]] → 1 × Area Contamination Scanner.

## Function

- Right-click to scan nearby contaminated surfaces and airborne reservoirs. It reports hazard level without revealing the strain and briefly marks affected positions.
- **visualization:** Yellow/red marks surfaces; blue marks contaminated air
- **privacy:** Reports hazard only; does not identify a strain
- **level.clean:** CLEAN
- **level.low:** LOW
- **level.medium:** MEDIUM
- **level.high:** HIGH
- **level.critical:** CRITICAL

## Progression connections

- Primarily consumed or interpreted by its linked special interaction rather than ordinary crafting.

## Stored data and safety

- It carries no readable biological payload by default, although contaminated ingredients can still propagate a strain.

## Registry and pack integration

- Registry ID: `bioforge:area_contamination_scanner`.
- No dedicated BioForge ingredient tag is currently bundled.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

