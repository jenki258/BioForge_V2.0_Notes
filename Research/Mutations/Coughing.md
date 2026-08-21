# Coughing

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_common #Pathogen_VIRUS #Pathogen_BACTERIA #Pathogen_FUNGI #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `coughing`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Repeated coughing exhausts the host and visibly sheds respiratory material

## Gameplay behavior

- Spawn `minecraft:cloud` particles (5 per event) every 60 ticks (35% chance) on continuous.
- Add 0.15 exhaustion every 60 ticks (35% chance) on continuous.
- Play `bioforge:symptom.cough` every 60 ticks (35% chance) on continuous; configured as a gameplay event where supplied.

## Compatibility and selection

- Compatible pathogens: VIRUS, BACTERIA, FUNGI, UNIVERSAL.
- Rarity: common; random-selection weight: 48.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `symptom`, `respiratory`, `suppressible:coughing`.

## Interactions

- **aerosol cough:** with [[Respiratory Shedding]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

