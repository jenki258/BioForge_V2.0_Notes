# Hemorrhagic Lesions

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_VIRUS #Pathogen_BACTERIA #Pathogen_PARASITE #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `hemorrhagic_lesions`. Source: `data/bioforge/mutations/hemorrhagic_lesions.json`.

## Description

Produces bleeding lesions and opens a blood transmission route

## Gameplay behavior

- Add the **BLOOD** transmission route on apply.
- Modify `otoscope_lesions` using **max 0.8**, clamped to 0–1 on apply.

## Compatibility and selection

- Compatible pathogens: VIRUS, BACTERIA, PARASITE.
- Rarity: rare; random-selection weight: 22.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `blood`, `lesion`, `transmission`.

## Interactions

- **hypervirulent bleeding:** with [[Hypervirulence]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

