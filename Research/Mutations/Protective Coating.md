# Protective Coating

#BioForge #BioForge_V0_54T #Mutation #Rarity_epic #Pathogen_BACTERIA #Pathogen_FUNGI #Pathogen_PRION #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `protective_coating`. Source: `data/bioforge/mutations/protective_coating.json`.

## Description

Builds a durable environmental shell and improves treatment resistance

## Gameplay behavior

- Add the **ENVIRONMENTAL** transmission route on apply.
- Modify `perfusion_index` using **add -0.12**, clamped to 0–1 on apply.

## Compatibility and selection

- Compatible pathogens: BACTERIA, FUNGI, PRION.
- Rarity: epic; random-selection weight: 12.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `environmental`, `surface`, `treatment_resistance`.

## Interactions

- **coated vaccine escape:** with [[Adaptive Vaccine Defense]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

