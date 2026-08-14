# Speed Bursts

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `speed_bursts`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Short unpredictable bursts of extreme speed disrupt normal movement

## Gameplay behavior

- Apply `minecraft:speed` level 3 for 60 ticks every 100 ticks (28% chance) on continuous.
- Add 0.3 exhaustion every 100 ticks (28% chance) on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 18.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `mixed`, `mobility`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

