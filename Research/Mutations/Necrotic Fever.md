# Necrotic Fever

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_uncommon #Pathogen_BACTERIA #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `necrotic_fever`. Source: `data/bioforge/mutations/necrotic_fever.json`.

## Description

Causes persistent fever and weakness

## Gameplay behavior

- Set `temperature_plus` to **true** using set on apply.
- Apply `minecraft:weakness` level 1 for 240 ticks every 100 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: BACTERIA.
- Rarity: uncommon; random-selection weight: 50.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `inflammation`, `temperature`.

## Interactions

- **hypervirulent fever:** with [[Hypervirulence]]; modifies 1 owned effect parameter(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

