# Surface Persistence

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_BACTERIA #Pathogen_FUNGI #Pathogen_VIRUS #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `surface_persistence`. Source: `data/bioforge/mutations/surface_persistence.json`.

## Description

Creates long-lived environmental reservoirs with a wider colony footprint

## Gameplay behavior

- Add the **ENVIRONMENTAL** transmission route on apply.
- Modify `colony_radius` using **multiply 1.5**, clamped to 0–10000 on apply.
- Modify `max_infested_blocks` using **multiply 1.75**, clamped to 0–10000 on apply.

## Compatibility and selection

- Compatible pathogens: BACTERIA, FUNGI, VIRUS.
- Rarity: rare; random-selection weight: 28.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `surface`, `environmental`, `transmission`.

## Interactions

- **persistent spore reservoir:** with [[Spore Cloud]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

