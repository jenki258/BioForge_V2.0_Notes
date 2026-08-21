# Pollinator's Grace

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_epic #Pathogen_FUNGI #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `pollinators_grace`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Airborne floral adaptation grants controlled falling and improved luck

## Gameplay behavior

- Apply `minecraft:slow_falling` level 1 for 100 ticks every 80 ticks on continuous.
- Modify `minecraft:generic.luck` by 1 with operation add every 80 ticks on continuous.
- Spawn `minecraft:happy_villager` particles (2 per event) every 80 ticks (20% chance) on continuous.

## Compatibility and selection

- Compatible pathogens: FUNGI, PARASITE, UNIVERSAL.
- Rarity: epic; random-selection weight: 9.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `plant`.

## Interactions

- **stable pollination:** with [[Pollination Dependency]]; removes [[Pollination Dependency]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

