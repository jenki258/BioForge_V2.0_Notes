# Fever

#BioForge #BioForge_V0_54T #Mutation #Rarity_common #Pathogen_VIRUS #Pathogen_BACTERIA #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `fever`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The infection drives temperature upward and produces visible heat stress

## Gameplay behavior

- Set `temperature_plus` to **true** using set on apply.
- Spawn `minecraft:ash` particles (3 per event) every 80 ticks (22% chance) on continuous.

## Compatibility and selection

- Compatible pathogens: VIRUS, BACTERIA, PARASITE, UNIVERSAL.
- Rarity: common; random-selection weight: 48.
- No mutation prerequisite.
- Conflicts with: [[Thermal Resistance]].
- Behavior tags: `legacy_v1`, `symptom`, `thermal`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

