# Weakness

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_common #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `weakness`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Systemic damage reduces physical power

## Gameplay behavior

- Apply `minecraft:weakness` level 1 for 100 ticks every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: common; random-selection weight: 46.
- No mutation prerequisite.
- Conflicts with: [[Strength]].
- Behavior tags: `legacy_v1`, `symptom`, `physical`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

