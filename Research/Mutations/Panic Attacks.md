# Panic Attacks

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_rare #Pathogen_PRION #Pathogen_VIRUS #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `panic_attacks`. Source: `data/bioforge/mutations/legacy_v1_catalog.json`.

## Description

Adrenal spikes create erratic bursts followed by weakness

## Gameplay behavior

- Apply `minecraft:speed` level 2 for 50 ticks every 120 ticks (24% chance) on continuous.
- Apply `minecraft:weakness` level 1 for 90 ticks every 120 ticks (24% chance) on continuous.
- Spawn `minecraft:angry_villager` particles (5 per event) every 120 ticks (24% chance) on continuous.

## Compatibility and selection

- Compatible pathogens: PRION, VIRUS, UNIVERSAL.
- Rarity: rare; random-selection weight: 20.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `legacy_v1`, `symptom`, `neural`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

