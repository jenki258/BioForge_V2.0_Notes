# Poison Resistance

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_BACTERIA #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `poison_resistance`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Enhanced detoxification continuously clears poison

## Gameplay behavior

- Continuously clear `minecraft:poison` every 20 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: BACTERIA, PARASITE, UNIVERSAL.
- Rarity: rare; random-selection weight: 20.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `toxin`.

## Interactions

- **poison compensation:** with [[Poison]]; removes [[Poison]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

