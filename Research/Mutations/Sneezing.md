# Sneezing

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_common #Pathogen_VIRUS #Pathogen_BACTERIA #Pathogen_FUNGI #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `sneezing`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Intermittent sneezing produces visible respiratory shedding

## Gameplay behavior

- Spawn `minecraft:sneeze` particles (6 per event) every 70 ticks (40% chance) on continuous.
- Play `bioforge:symptom.sneeze` every 70 ticks (40% chance) on continuous; configured as a gameplay event where supplied.

## Compatibility and selection

- Compatible pathogens: VIRUS, BACTERIA, FUNGI, UNIVERSAL.
- Rarity: common; random-selection weight: 48.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `symptom`, `respiratory`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

