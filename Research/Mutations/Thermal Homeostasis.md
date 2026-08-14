# Thermal Homeostasis

#BioForge #BioForge_V0_54T #Mutation #Rarity_legendary #Pathogen_VIRUS #Pathogen_BACTERIA #Pathogen_FUNGI #Pathogen_PARASITE #Pathogen_PRION #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `thermal_homeostasis`. Source: `data/bioforge/mutations/lifecycle_mutations.json`.

## Description

The strain remains stable at both climatic extremes

## Gameplay behavior

- This definition is a marker/interaction/lifecycle mutation; its effect is consumed by another BioForge system rather than a direct repeating effect.

## Compatibility and selection

- Compatible pathogens: VIRUS, BACTERIA, FUNGI, PARASITE, PRION, UNIVERSAL.
- Rarity: legendary; random-selection weight: 0.
- Requires: [[Heat Adaptation]], [[Cold Adaptation]].
- No explicit mutation conflict.
- Behavior tags: `climate_adaptation`, `heat_immunity`, `cold_immunity`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Weight zero means ordinary weighted random selection does not choose it; lifecycle, vaccine pressure, wild-host rules, commands, or interactions may still grant it.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

