# Hypervirulence

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `hypervirulence`. Source: `data/bioforge/mutations/hypervirulence.json`.

## Description

Increases infection strength by 50%

## Gameplay behavior

- Modify `infection_strength` using **multiply 1.5**, clamped to 0–1 on apply.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 20.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `infection`, `virulence`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

