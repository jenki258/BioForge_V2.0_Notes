# Analgesic Resistance

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_epic #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `analgesic_resistance`. Source: `data/bioforge/mutations/analgesic_resistance.json`.

## Description

Makes symptom-suppressing tablets substantially less durable

## Gameplay behavior

- Modify `infection_strength` using **add 0.06**, clamped to 0–1 on apply.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: epic; random-selection weight: 10.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `treatment_resistance`, `symptom_suppression`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

