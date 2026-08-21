# Zoonotic Adaptation

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_rare #Pathogen_BACTERIA #Pathogen_PARASITE #Pathogen_VIRUS #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `zoonotic_adaptation`. Source: `data/bioforge/mutations/zoonotic_adaptation.json`.

## Description

Allows the strain to propagate through infected animals and their products

## Gameplay behavior

- Add the **ANIMALS** transmission route on apply.

## Compatibility and selection

- Compatible pathogens: BACTERIA, PARASITE, VIRUS.
- Rarity: rare; random-selection weight: 24.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `animal`, `transmission`, `food_chain`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

