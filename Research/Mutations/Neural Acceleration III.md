# Neural Acceleration III

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_epic #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `neural_acceleration_iii`. Source: `data/bioforge/mutations/simple_effect_tiers.json`.

## Description

Unstable neural overclocking grants Speed III with a substantial metabolic drain

## Gameplay behavior

- Apply `minecraft:speed` level 3 for 120 ticks every 60 ticks on continuous.
- Add 0.18 exhaustion every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: epic; random-selection weight: 4.
- Requires: [[Neural Acceleration II]].
- No explicit mutation conflict.
- Behavior tags: `beneficial`, `simple_effect`, `speed`, `tier_3`.

## Interactions

- **neural acceleration upgrade iii:** with [[Neural Acceleration II]]; removes [[Neural Acceleration II]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

