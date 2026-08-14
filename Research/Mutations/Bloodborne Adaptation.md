# Bloodborne Adaptation

#BioForge #BioForge_V0_54T #Mutation #Rarity_uncommon #Pathogen_BACTERIA #Pathogen_FUNGI #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `bloodborne`. Source: `data/bioforge/mutations/bloodborne.json`.

## Description

Adds blood transmission to the infection

## Gameplay behavior

- Add the **BLOOD** transmission route on apply.

## Compatibility and selection

- Compatible pathogens: BACTERIA, FUNGI.
- Rarity: uncommon; random-selection weight: 50.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `transmission`, `blood`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

