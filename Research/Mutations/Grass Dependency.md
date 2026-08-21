# Grass Dependency

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_uncommon #Pathogen_PARASITE #Pathogen_FUNGI #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `grass_dependency`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The host must remain on living grass-like substrate or suffer escalating hunger and metabolic weakness

## Gameplay behavior

- Enforce grass-substrate dependency with 0.35 exhaustion every 40 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: PARASITE, FUNGI, UNIVERSAL.
- Rarity: uncommon; random-selection weight: 30.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `detrimental`, `plant`, `substrate_dependency`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

