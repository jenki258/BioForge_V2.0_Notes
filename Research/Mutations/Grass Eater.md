# Grass Eater

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_PARASITE #Pathogen_FUNGI #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `grass_eater`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Plant-adapted metabolism stabilizes hunger and repairs minor damage

## Gameplay behavior

- Apply `minecraft:saturation` level 1 for 40 ticks every 160 ticks (18% chance) on continuous.
- Apply `minecraft:regeneration` level 1 for 50 ticks every 160 ticks (12% chance) on continuous.

## Compatibility and selection

- Compatible pathogens: PARASITE, FUNGI, UNIVERSAL.
- Rarity: rare; random-selection weight: 20.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `plant`.

## Interactions

- **plant metabolism:** with [[Grass Dependency]]; removes [[Grass Dependency]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

