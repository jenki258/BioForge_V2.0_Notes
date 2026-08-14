# Gastrointestinal Shedding

#BioForge #BioForge_V0_54T #Mutation #Rarity_uncommon #Pathogen_BACTERIA #Pathogen_PARASITE #Pathogen_VIRUS #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `gastrointestinal_shedding`. Source: `data/bioforge/mutations/gastrointestinal_shedding.json`.

## Description

Adds food transmission and greatly increases secretion

## Gameplay behavior

- Add the **FOOD BORNE** transmission route on apply.
- Modify `otoscope_secretion` using **max 0.75**, clamped to 0–1 on apply.

## Compatibility and selection

- Compatible pathogens: BACTERIA, PARASITE, VIRUS.
- Rarity: uncommon; random-selection weight: 50.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `food`, `secretion`, `transmission`.

## Interactions

- **zoonotic food chain:** with [[Zoonotic Adaptation]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

