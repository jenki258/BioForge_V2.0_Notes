# Muscular Response II

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `muscular_response_ii`. Source: `data/bioforge/mutations/simple_effect_tiers.json`.

## Description

A stronger muscle response grants Strength II at a higher metabolic cost

## Gameplay behavior

- Apply `minecraft:strength` level 2 for 140 ticks every 80 ticks on continuous.
- Add 0.1 exhaustion every 100 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 12.
- Requires: [[Muscular Response I]].
- No explicit mutation conflict.
- Behavior tags: `beneficial`, `simple_effect`, `strength`, `tier_2`.

## Interactions

- **muscular response upgrade ii:** with [[Muscular Response I]]; removes [[Muscular Response I]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

