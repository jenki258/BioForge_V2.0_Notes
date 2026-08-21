# Amphibious Fatigue

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_uncommon #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `amphibious_fatigue`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Water causes intense muscular fatigue until the strain develops aquatic respiration

## Gameplay behavior

- Apply `minecraft:slowness` level 2 for 80 ticks every 40 ticks while in water on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: uncommon; random-selection weight: 35.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `detrimental`, `aquatic`.

## Interactions

- **aquatic compensation:** with [[Self Respiration]]; removes [[Amphibious Fatigue]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

