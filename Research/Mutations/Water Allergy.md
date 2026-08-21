# Water Allergy

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_uncommon #Pathogen_FUNGI #Pathogen_PRION #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `water_allergy`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Contact with water damages unstable tissue

## Gameplay behavior

- Deal 1 drown damage every 60 ticks while in water on continuous.

## Compatibility and selection

- Compatible pathogens: FUNGI, PRION, UNIVERSAL.
- Rarity: uncommon; random-selection weight: 30.
- No mutation prerequisite.
- Conflicts with: [[Water Camouflage]], [[Self Respiration]].
- Behavior tags: `legacy_v1`, `detrimental`, `aquatic`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

