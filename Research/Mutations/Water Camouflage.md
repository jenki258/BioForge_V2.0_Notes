# Water Camouflage

#BioForge #BioForge_V0_54T #Mutation #Rarity_epic #Pathogen_BACTERIA #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `water_camouflage`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The host becomes nearly invisible while submerged

## Gameplay behavior

- Camouflage the host in **water** conditions every 5 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: BACTERIA, PARASITE, UNIVERSAL.
- Rarity: epic; random-selection weight: 9.
- No mutation prerequisite.
- Conflicts with: [[Water Allergy]].
- Behavior tags: `legacy_v1`, `beneficial`, `camouflage`, `aquatic`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

