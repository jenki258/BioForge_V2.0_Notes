# Regenerative Tissue III

#BioForge #BioForge_V0_54T #Mutation #Rarity_legendary #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `regenerative_tissue_iii`. Source: `data/bioforge/mutations/simple_effect_tiers.json`.

## Description

Aggressive tissue reconstruction grants Regeneration III at severe metabolic cost

## Gameplay behavior

- Apply `minecraft:regeneration` level 3 for 100 ticks every 60 ticks on continuous.
- Add 0.38 exhaustion every 60 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: legendary; random-selection weight: 2.
- Requires: [[Regenerative Tissue II]].
- No explicit mutation conflict.
- Behavior tags: `beneficial`, `simple_effect`, `regeneration`, `tier_3`.

## Interactions

- **regenerative tissue upgrade iii:** with [[Regenerative Tissue II]]; removes [[Regenerative Tissue II]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

