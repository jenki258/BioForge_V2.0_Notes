# Regenerative Tissue I

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `regenerative_tissue_i`. Source: `data/bioforge/mutations/simple_effect_tiers.json`.

## Description

Slow tissue repair grants Regeneration I

## Gameplay behavior

- Apply `minecraft:regeneration` level 1 for 100 ticks every 100 ticks on continuous.
- Add 0.1 exhaustion every 100 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 16.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `beneficial`, `simple_effect`, `regeneration`, `tier_1`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

