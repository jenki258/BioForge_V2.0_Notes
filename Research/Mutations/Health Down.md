# Health Down

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_PRION #Pathogen_PARASITE #Pathogen_VIRUS #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `health_down`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Progressive systemic damage reduces maximum health

## Gameplay behavior

- Modify `minecraft:generic.max_health` by -4 with operation add every 80 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: PRION, PARASITE, VIRUS, UNIVERSAL.
- Rarity: rare; random-selection weight: 20.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `symptom`, `detrimental`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

