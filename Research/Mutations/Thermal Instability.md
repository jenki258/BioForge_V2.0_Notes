# Thermal Instability

#BioForge #BioForge_V0_54T #Mutation #Rarity_uncommon #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `thermal_instability`. Source: `data/bioforge/mutations/thermal_instability.json`.

## Description

Destabilizes host temperature regulation

## Gameplay behavior

- Set `temperature_plus` to **true** using set on apply.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: uncommon; random-selection weight: 42.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `temperature`, `metabolic`.

## Interactions

- **necrotic thermal spike:** with [[Necrotic Fever]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

