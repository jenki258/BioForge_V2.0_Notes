# Chameleon

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_epic #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `chameleon`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The host fades from view while remaining nearly motionless

## Gameplay behavior

- Camouflage the host in **still** conditions every 5 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: epic; random-selection weight: 8.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `camouflage`.

## Interactions

- **adaptive camouflage:** with [[Water Camouflage]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

