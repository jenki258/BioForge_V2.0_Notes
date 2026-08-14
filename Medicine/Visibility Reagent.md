# Visibility Reagent

#BioForge #BioForge_V0_54T #Item #Medicine #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This medical item changes infection risk, symptoms, strain parameters, or treatment outcomes.
Microscope success follows the hidden visibility tier: extreme is reliable, medium is uncertain, and very low often fails.
## Obtaining

- **crafting shapeless** (`visibility_reagent.json`): [[Laboratory Glassware]], [[Sterile Filter]], `#bioforge:ingredients/minecraft/amethyst_shard`, `#bioforge:ingredients/minecraft/glow_ink_sac`, `#bioforge:ingredients/minecraft/redstone` → 1 × Visibility Reagent.
- **[[Pharma Mixer]]** (`visibility_reagent.json`): [[Laboratory Glassware]], [[Sterile Filter]], `#bioforge:ingredients/minecraft/amethyst_shard`, `#bioforge:ingredients/minecraft/glow_ink_sac`, `#bioforge:ingredients/minecraft/redstone` → 2 × Visibility Reagent in 200 ticks, plus [[Laboratory Waste]].

## Function

- Microscope success follows the hidden visibility tier: extreme is reliable, medium is uncertain, and very low often fails.
- **description:** Tests how readily an infection reacts to contrast reagent
- **negative:** No visible reaction
- **inconclusive:** A weak infection may produce a false negative

## Progression connections

- Primarily consumed or interpreted by its linked special interaction rather than ordinary crafting.

## Stored data and safety

- Program, strain, target, quality, and research payloads are server-authoritative and use BioForge biological-data helpers.

## Registry and pack integration

- Registry ID: `bioforge:visibility_reagent`.
- No dedicated BioForge ingredient tag is currently bundled.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

