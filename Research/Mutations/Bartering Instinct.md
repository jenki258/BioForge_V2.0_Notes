# Bartering Instinct

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `bartering_instinct`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Heightened social pattern recognition improves luck while infected

## Gameplay behavior

- Modify `minecraft:generic.luck` by 2 with operation add every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 18.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `behavioral`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

