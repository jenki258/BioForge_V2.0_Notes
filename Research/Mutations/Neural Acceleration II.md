# Neural Acceleration II

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `neural_acceleration_ii`. Source: `data/bioforge/mutations/simple_effect_tiers.json`.

## Description

Accelerated neural signalling grants Speed II and mild hunger

## Gameplay behavior

- Apply `minecraft:speed` level 2 for 140 ticks every 80 ticks on continuous.
- Add 0.08 exhaustion every 100 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 12.
- Requires: [[Neural Acceleration I]].
- No explicit mutation conflict.
- Behavior tags: `beneficial`, `simple_effect`, `speed`, `tier_2`.

## Interactions

- **neural acceleration upgrade ii:** with [[Neural Acceleration I]]; removes [[Neural Acceleration I]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

