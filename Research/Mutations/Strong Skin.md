# Strong Skin

#BioForge #BioForge_V0_54T #Mutation #Rarity_epic #Pathogen_BACTERIA #Pathogen_FUNGI #Pathogen_PARASITE #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `strong_skin`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Dense dermal tissue increases armour and knockback resistance

## Gameplay behavior

- Modify `minecraft:generic.armor` by 4 with operation add every 80 ticks on continuous.
- Modify `minecraft:generic.knockback_resistance` by 0.15 with operation add every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: BACTERIA, FUNGI, PARASITE, UNIVERSAL.
- Rarity: epic; random-selection weight: 10.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `beneficial`, `physical`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

