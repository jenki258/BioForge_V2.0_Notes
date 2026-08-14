# Reinforced Vaccine Defense

#BioForge #BioForge_V0_54T #Mutation #Rarity_legendary #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `reinforced_vaccine_defense`. Source: `data/bioforge/mutations/reinforced_vaccine_defense.json`.

## Description

A stable compound adaptation produced by vaccine defense and hypervirulence

## Gameplay behavior

- Modify `infection_strength` using **add 0.15**, clamped to 0–1 on apply.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: legendary; random-selection weight: 0.
- Requires: [[Adaptive Vaccine Defense]], [[Hypervirulence]].
- No explicit mutation conflict.
- Behavior tags: `vaccine_defense`, `immune_escape`, `compound_mutation`, `treatment_resistance`, `vaccine_requires_rh_negative`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Weight zero means ordinary weighted random selection does not choose it; lifecycle, vaccine pressure, wild-host rules, commands, or interactions may still grant it.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

