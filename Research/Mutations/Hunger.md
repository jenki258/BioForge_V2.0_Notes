# Hunger

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_common #Pathogen_PARASITE #Pathogen_VIRUS #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `hunger`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The infection consumes host energy reserves

## Gameplay behavior

- Apply `minecraft:hunger` level 1 for 120 ticks every 100 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: PARASITE, VIRUS, UNIVERSAL.
- Rarity: common; random-selection weight: 46.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `symptom`, `metabolic`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

