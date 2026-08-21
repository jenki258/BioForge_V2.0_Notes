# Hay Infusion

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_rare #Pathogen_FUNGI #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `hay_infusion`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Fibrous biological reinforcement improves damage resistance

## Gameplay behavior

- Apply `minecraft:resistance` level 1 for 100 ticks every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: FUNGI, PARASITE, UNIVERSAL.
- Rarity: rare; random-selection weight: 18.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `plant`.

## Interactions

- **allergen tolerance:** with [[Hay Allergy]]; removes [[Hay Allergy]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

