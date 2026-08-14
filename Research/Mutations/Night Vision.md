# Night Vision

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `night_vision`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Retinal adaptation reveals dark environments

## Gameplay behavior

- Apply `minecraft:night_vision` level 1 for 260 ticks every 200 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 18.
- No mutation prerequisite.
- Conflicts with: [[Night Blindness]].
- Behavior tags: `legacy_v1`, `beneficial`, `visual`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

