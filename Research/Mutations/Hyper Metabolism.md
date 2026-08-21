# Hyper Metabolism

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_uncommon #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `hyper_metabolism`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Movement accelerates while food reserves collapse

## Gameplay behavior

- Modify `minecraft:generic.movement_speed` by 0.06 with operation add every 80 ticks on continuous.
- Apply `minecraft:hunger` level 1 for 100 ticks every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: uncommon; random-selection weight: 30.
- No mutation prerequisite.
- Conflicts with: [[Metabolic Overdrive]].
- Behavior tags: `legacy_v1`, `metabolic`, `mixed`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

