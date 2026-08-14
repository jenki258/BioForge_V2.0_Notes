# Dermal Reinforcement I

#BioForge #BioForge_V0_54T #Mutation #Rarity_uncommon #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `dermal_reinforcement_i`. Source: `data/bioforge/mutations/simple_effect_tiers.json`.

## Description

Altered connective tissue grants Resistance I

## Gameplay behavior

- Apply `minecraft:resistance` level 1 for 140 ticks every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: uncommon; random-selection weight: 22.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `beneficial`, `simple_effect`, `resistance`, `tier_1`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

