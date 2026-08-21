# Nausea

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_common #Pathogen_PARASITE #Pathogen_PRION #Pathogen_VIRUS #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `nausea`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Neurological and gastrointestinal disruption distorts vision

## Gameplay behavior

- Apply `minecraft:nausea` level 1 for 100 ticks every 120 ticks (35% chance) on continuous.

## Compatibility and selection

- Compatible pathogens: PARASITE, PRION, VIRUS, UNIVERSAL.
- Rarity: common; random-selection weight: 44.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `symptom`, `neural`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

