# BioForge Research Tablet

#BioForge #BioForge_V2_0 #Build_V0_54T #Item #Research_Items #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This research item carries or supports biological knowledge that must be earned through the laboratory workflow.
It unlocks permanent discoveries, research toasts, scrolling pages, and visual recipe layouts.
## Obtaining

- **crafting shapeless** (`research_journal.json`): `#bioforge:ingredients/minecraft/book`, `#bioforge:ingredients/minecraft/ink_sac`, `#bioforge:ingredients/minecraft/paper` → 1 × Research Journal.

## Function

- It unlocks permanent discoveries, research toasts, scrolling pages, and visual recipe layouts.
- **tooltip:** A persistent tablet for BioForge discoveries
- **progression:** New research unlocks after obtaining related items

## Progression connections

- Primarily consumed or interpreted by its linked special interaction rather than ordinary crafting.

## Stored data and safety

- Program, strain, target, quality, and research payloads are server-authoritative and use BioForge biological-data helpers.

## Registry and pack integration

- Registry ID: `bioforge:research_journal`.
- No dedicated BioForge ingredient tag is currently bundled.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]
