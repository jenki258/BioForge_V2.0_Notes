# Pyrolytic Self-Destruction

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_rare #Pathogen_VIRUS #Pathogen_BACTERIA #Pathogen_FUNGI #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `pyrolytic_self_destruct`. Source: `data/bioforge/mutations/lifecycle_mutations.json`.

## Description

The pathogen irreversibly destroys itself when exposed to fire

## Gameplay behavior

- Attempt to destroy the active infection every 20 ticks (20% chance) when on fire on continuous.

## Compatibility and selection

- Compatible pathogens: VIRUS, BACTERIA, FUNGI, UNIVERSAL.
- Rarity: rare; random-selection weight: 12.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `self_destruct`, `environment_reaction`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

