# Paranoia

#BioForge #BioForge_V0_54T #Mutation #Rarity_epic #Pathogen_PRION #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `paranoia`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Neural inflammation produces darkness, unease and false threat responses

## Gameplay behavior

- Apply `minecraft:darkness` level 1 for 80 ticks every 140 ticks (22% chance) on continuous.
- Spawn `minecraft:witch` particles (4 per event) every 140 ticks (22% chance) on continuous.
- Play `bioforge:symptom.paranoia_voice` every 180 ticks (16% chance) on continuous; configured as a gameplay event where supplied.

## Compatibility and selection

- Compatible pathogens: PRION, PARASITE, UNIVERSAL.
- Rarity: epic; random-selection weight: 10.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `symptom`, `neural`, `visual`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

