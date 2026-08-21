# Regenerative Tissue II

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_epic #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `regenerative_tissue_ii`. Source: `data/bioforge/mutations/simple_effect_tiers.json`.

## Description

Rapid tissue repair grants Regeneration II and consumes food reserves

## Gameplay behavior

- Apply `minecraft:regeneration` level 2 for 100 ticks every 80 ticks on continuous.
- Add 0.22 exhaustion every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: epic; random-selection weight: 6.
- Requires: [[Regenerative Tissue I]].
- No explicit mutation conflict.
- Behavior tags: `beneficial`, `simple_effect`, `regeneration`, `tier_2`.

## Interactions

- **regenerative tissue upgrade ii:** with [[Regenerative Tissue I]]; removes [[Regenerative Tissue I]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

