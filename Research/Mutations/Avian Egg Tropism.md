# Avian Egg Tropism

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_legendary #Pathogen_VIRUS #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `avian_egg_tropism`. Source: `data/bioforge/mutations/wild_host_mutations.json`.

## Description

A wild-host gene isolated from infected avian blood

## Gameplay behavior

- Add the **food borne** transmission route on apply.

## Compatibility and selection

- Compatible pathogens: VIRUS, UNIVERSAL.
- Rarity: legendary; random-selection weight: 0.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `wild_only`, `avian_origin`, `vaccine_target`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Weight zero means ordinary weighted random selection does not choose it; lifecycle, vaccine pressure, wild-host rules, commands, or interactions may still grant it.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

