# Blindness Resistance

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `blindness_resistance`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Neural compensation continuously clears blindness

## Gameplay behavior

- Continuously clear `minecraft:blindness` every 20 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 20.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `neural`.

## Interactions

- **visual compensation:** with [[Blindness]] or [[Night Blindness]]; removes [[Blindness]], [[Night Blindness]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

