# Weak Grip

#BioForge #BioForge_V0_54T #Mutation #Rarity_uncommon #Pathogen_PRION #Pathogen_VIRUS #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `weak_grip`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Motor damage reduces attack damage and handling speed

## Gameplay behavior

- Modify `minecraft:generic.attack_damage` by -2 with operation add every 80 ticks on continuous.
- Modify `minecraft:generic.attack_speed` by -0.35 with operation add every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: PRION, VIRUS, UNIVERSAL.
- Rarity: uncommon; random-selection weight: 32.
- No mutation prerequisite.
- Conflicts with: [[Strength]].
- Behavior tags: `legacy_v1`, `detrimental`, `neural`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

