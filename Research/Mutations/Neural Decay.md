# Neural Decay

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_epic #Pathogen_PRION #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `neural_decay`. Source: `data/bioforge/mutations/neural_decay.json`.

## Description

Causes severe neural damage and delayed reflexes

## Gameplay behavior

- Set `neural_damage` to **1** using max on apply.
- Set `reflex_delay` to **0.9** using max on apply.

## Compatibility and selection

- Compatible pathogens: PRION.
- Rarity: epic; random-selection weight: 8.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `neural`, `reflex`.

## Interactions

- No explicit cross-mutation interaction is declared in this definition.

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

