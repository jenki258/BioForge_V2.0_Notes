# Strength

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `strength`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Muscle recruitment increases attack damage

## Gameplay behavior

- Modify `minecraft:generic.attack_damage` by 2 with operation add every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 18.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `physical`.

## Interactions

- **motor recovery:** with [[Weak Grip]]; removes [[Weak Grip]].

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

