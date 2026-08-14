# Dermal Reinforcement II

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `dermal_reinforcement_ii`. Source: `data/bioforge/mutations/simple_effect_tiers.json`.

## Description

Dense connective tissue grants Resistance II but slows the host slightly

## Gameplay behavior

- Apply `minecraft:resistance` level 2 for 140 ticks every 80 ticks on continuous.
- Apply `minecraft:slowness` level 1 for 80 ticks every 100 ticks (20% chance) on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 9.
- Requires: [[Dermal Reinforcement I]].
- No explicit mutation conflict.
- Behavior tags: `beneficial`, `simple_effect`, `resistance`, `tier_2`.

## Interactions

- **dermal reinforcement upgrade ii:** with [[Dermal Reinforcement I]]; removes [[Dermal Reinforcement I]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

