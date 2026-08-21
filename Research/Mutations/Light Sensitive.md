# Light Sensitive

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_uncommon #Pathogen_PRION #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `light_sensitive`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Bright environments trigger visual and motor distress

## Gameplay behavior

- React to **bright** light by applying `minecraft:weakness` every 20 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: PRION, PARASITE, UNIVERSAL.
- Rarity: uncommon; random-selection weight: 30.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `detrimental`, `visual`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

