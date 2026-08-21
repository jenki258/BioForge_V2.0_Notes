# Blindness

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_uncommon #Pathogen_PRION #Pathogen_VIRUS #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `blindness`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The infection repeatedly disrupts visual processing

## Gameplay behavior

- Apply `minecraft:blindness` level 1 for 100 ticks every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: PRION, VIRUS, UNIVERSAL.
- Rarity: uncommon; random-selection weight: 30.
- No mutation prerequisite.
- Conflicts with: [[Blindness Resistance]].
- Behavior tags: `legacy_v1`, `symptom`, `visual`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

