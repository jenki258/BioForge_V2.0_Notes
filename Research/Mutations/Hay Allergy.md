# Hay Allergy

#BioForge #BioForge_V0_54T #Mutation #Rarity_common #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `hay_allergy`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Plant fibres provoke weakness and frequent visible sneezing

## Gameplay behavior

- Apply `minecraft:weakness` level 1 for 90 ticks every 80 ticks on continuous.
- Spawn `minecraft:sneeze` particles (4 per event) every 100 ticks (35% chance) on continuous.
- Play `bioforge:symptom.sneeze` every 100 ticks (35% chance) on continuous; configured as a gameplay event where supplied.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: common; random-selection weight: 45.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `detrimental`, `respiratory`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

