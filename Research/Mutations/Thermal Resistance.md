# Thermal Resistance

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_epic #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `heat_cold_resistance`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Thermoregulation suppresses infection-driven fever and hypothermia

## Gameplay behavior

- Set `temperature_plus` to **false** using set on apply.
- Set `temperature_minus` to **false** using set on apply.
- Apply `minecraft:fire_resistance` level 1 for 100 ticks every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: epic; random-selection weight: 10.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `thermal`.

## Interactions

- **thermal stabilization:** with [[Thermal Instability]]; removes [[Thermal Instability]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

