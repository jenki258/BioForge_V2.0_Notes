# Scanner Evasion

#BioForge #BioForge_V0_54T #Mutation #Rarity_epic #Pathogen_VIRUS #Pathogen_PRION #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `scanner_evasion`. Source: `data/bioforge/mutations/scanner_evasion.json`.

## Description

The strain suppresses the biomarkers used by BioForge viral scanners, allowing infected hosts to pass undetected

## Gameplay behavior

- Set `microscope_visibility` to **VERY_LOW** using set on apply.
- Spawn `minecraft:smoke` particles (2 per event) every 100 ticks (8% chance) on continuous.

## Compatibility and selection

- Compatible pathogens: VIRUS, PRION, UNIVERSAL.
- Rarity: epic; random-selection weight: 10.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `scanner_evasion`, `stealth`, `diagnostic_evasion`, `vaccine_target`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

