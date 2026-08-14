# Respiratory Shedding

#BioForge #BioForge_V0_54T #Mutation #Rarity_uncommon #Pathogen_VIRUS #Pathogen_BACTERIA #Pathogen_FUNGI #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `respiratory_shedding`. Source: `data/bioforge/mutations/respiratory_shedding.json`.

## Description

Forces airborne transmission and causes productive crackling respiration

## Gameplay behavior

- Add the **AIR BORNE** transmission route on apply.
- Set `lung_sound` to **CRACKLE** using set on apply.

## Compatibility and selection

- Compatible pathogens: VIRUS, BACTERIA, FUNGI.
- Rarity: uncommon; random-selection weight: 55.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `transmission`, `airborne`, `respiratory`.

## Interactions

- **aerosolized spores:** with [[Spore Cloud]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

