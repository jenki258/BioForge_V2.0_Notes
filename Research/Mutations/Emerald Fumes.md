# Emerald Fumes

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_BACTERIA #Pathogen_FUNGI #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `emerald_fumes`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The infection periodically releases visible toxic metabolic vapour

## Gameplay behavior

- Spawn `minecraft:witch` particles (7 per event) every 40 ticks on continuous.
- Apply `minecraft:poison` level 1 for 80 ticks every 80 ticks (8% chance) on continuous.

## Compatibility and selection

- Compatible pathogens: BACTERIA, FUNGI, UNIVERSAL.
- Rarity: rare; random-selection weight: 18.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `detrimental`, `visual`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

