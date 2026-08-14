# Gene Imprint

#BioForge #BioForge_V0_54T #Item #Research_Items #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This research item carries or supports biological knowledge that must be earned through the laboratory workflow.
The Microscope writes an identified symptom, mutation, route, or other target into it for directed Vaccine Maker work.
## Obtaining

- **crafting shapeless** (`gene_imprint.json`): [[Sterile Polymer Sheet]], `#bioforge:ingredients/minecraft/paper`, `#bioforge:ingredients/minecraft/redstone`, `#bioforge:ingredients/minecraft/amethyst_shard`, [[Sterile Filter]] → 1 × Gene Imprint.

## Function

- The Microscope writes an identified symptom, mutation, route, or other target into it for directed Vaccine Maker work.
- **empty:** Blank gene imprint
- **copy hint:** Right-click while holding a blank Gene Imprint in the other hand to copy
- **capture:** Use on an infected entity to record a target
- **cycle:** Right-click: next target; Shift + right-click: next target class
- **extract:** Extract an unknown fragment in the Vaccine Maker
- **unidentified:** Target structure unidentified
- **microscope:** Calibrate a microscope to identify this fragment

## Progression connections

- Primarily consumed or interpreted by its linked special interaction rather than ordinary crafting.

## Stored data and safety

- Program, strain, target, quality, and research payloads are server-authoritative and use BioForge biological-data helpers.

## Registry and pack integration

- Registry ID: `bioforge:gene_imprint`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/gene_imprint`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

