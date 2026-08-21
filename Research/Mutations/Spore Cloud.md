# Spore Cloud

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_common #Pathogen_FUNGI #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `spore_cloud`. Source: `data/bioforge/mutations/spore_cloud.json`.

## Description

Periodically releases visible spores around the host

## Gameplay behavior

- Spawn `minecraft:spore_blossom_air` particles (10 per event) every 20 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: FUNGI.
- Rarity: common; random-selection weight: 100.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `spore`, `visual`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

