# Self Respiration

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_epic #Pathogen_BACTERIA #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `self_respiration`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

The infection maintains the host's air supply underwater

## Gameplay behavior

- Maintain underwater respiration every 10 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: BACTERIA, PARASITE, UNIVERSAL.
- Rarity: epic; random-selection weight: 9.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `aquatic`.

## Interactions

- **aquatic adaptation:** with [[Amphibious Fatigue]]; removes [[Amphibious Fatigue]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

