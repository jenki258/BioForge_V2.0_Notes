# Pollination Dependency

#BioForge #BioForge_V0_54T #Mutation #Rarity_uncommon #Pathogen_FUNGI #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `pollination_dependency`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The strain depends on unstable floral metabolites

## Gameplay behavior

- Apply `minecraft:weakness` level 1 for 100 ticks every 80 ticks on continuous.
- Add 0.15 exhaustion every 100 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: FUNGI, PARASITE, UNIVERSAL.
- Rarity: uncommon; random-selection weight: 28.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `detrimental`, `plant`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

