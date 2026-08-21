# Fast Regeneration

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_epic #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `fast_regeneration`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Aggressive tissue repair restores health at a high metabolic cost

## Gameplay behavior

- Apply `minecraft:regeneration` level 1 for 80 ticks every 60 ticks on continuous.
- Add 0.2 exhaustion every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: epic; random-selection weight: 10.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `regeneration`.

## Interactions

- **carnivorous repair:** with [[Flesh Cravings]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

