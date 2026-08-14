# Muscular Response III

#BioForge #BioForge_V0_54T #Mutation #Rarity_epic #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `muscular_response_iii`. Source: `data/bioforge/mutations/simple_effect_tiers.json`.

## Description

Extreme muscular stimulation grants Strength III but consumes food rapidly

## Gameplay behavior

- Apply `minecraft:strength` level 3 for 120 ticks every 60 ticks on continuous.
- Add 0.22 exhaustion every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: epic; random-selection weight: 4.
- Requires: [[Muscular Response II]].
- No explicit mutation conflict.
- Behavior tags: `beneficial`, `simple_effect`, `strength`, `tier_3`.

## Interactions

- **muscular response upgrade iii:** with [[Muscular Response II]]; removes [[Muscular Response II]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

