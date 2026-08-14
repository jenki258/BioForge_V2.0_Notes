# Honey Immunity

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_BACTERIA #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `honey_immunity`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The strain metabolizes common toxins before they affect the host

## Gameplay behavior

- Continuously clear `minecraft:poison` every 20 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: BACTERIA, PARASITE, UNIVERSAL.
- Rarity: rare; random-selection weight: 18.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `toxin`.

## Interactions

- **toxin neutralization:** with [[Poison]]; removes [[Poison]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

