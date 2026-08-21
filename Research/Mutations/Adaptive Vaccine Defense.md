# Adaptive Vaccine Defense

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_epic #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `vaccine_defense`. Source: `data/bioforge/mutations/vaccine_defense.json`.

## Description

An immune-escape response selected after surviving vaccine pressure

## Gameplay behavior

- This definition is a marker/interaction/lifecycle mutation; its effect is consumed by another BioForge system rather than a direct repeating effect.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: epic; random-selection weight: 0.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `vaccine_defense`, `immune_escape`, `treatment_resistance`.

## Interactions

- **hypervirulent escape:** with [[Hypervirulence]]; grants [[Reinforced Vaccine Defense]].

## Pack and addon notes

- Weight zero means ordinary weighted random selection does not choose it; lifecycle, vaccine pressure, wild-host rules, commands, or interactions may still grant it.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

