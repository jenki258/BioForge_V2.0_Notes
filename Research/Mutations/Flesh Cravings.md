# Flesh Cravings

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_rare #Pathogen_PARASITE #Pathogen_VIRUS #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `flesh_cravings`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The host can digest only meat; feeding the craving restores tissue but an empty stomach quickly becomes dangerous

## Gameplay behavior

- Apply `minecraft:strength` level 1 for 100 ticks every 80 ticks on continuous.
- Add 0.18 exhaustion every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: PARASITE, VIRUS, UNIVERSAL.
- Rarity: rare; random-selection weight: 18.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `metabolic`, `mixed`, `diet:meat_only`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

