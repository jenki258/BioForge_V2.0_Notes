# Dermal Reinforcement III

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_legendary #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `dermal_reinforcement_iii`. Source: `data/bioforge/mutations/simple_effect_tiers.json`.

## Description

Armoured tissue grants Resistance III while increasingly restricting movement

## Gameplay behavior

- Apply `minecraft:resistance` level 3 for 120 ticks every 60 ticks on continuous.
- Apply `minecraft:slowness` level 1 for 100 ticks every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: legendary; random-selection weight: 2.
- Requires: [[Dermal Reinforcement II]].
- No explicit mutation conflict.
- Behavior tags: `beneficial`, `simple_effect`, `resistance`, `tier_3`.

## Interactions

- **dermal reinforcement upgrade iii:** with [[Dermal Reinforcement II]]; removes [[Dermal Reinforcement II]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

