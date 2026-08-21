# Night Blindness

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_uncommon #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `night_blindness`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Low light severely disrupts vision

## Gameplay behavior

- React to **dark** light by applying `minecraft:blindness` every 20 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: uncommon; random-selection weight: 32.
- No mutation prerequisite.
- Conflicts with: [[Night Vision]], [[Blindness Resistance]].
- Behavior tags: `legacy_v1`, `detrimental`, `visual`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

