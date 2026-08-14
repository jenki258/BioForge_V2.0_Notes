# Metabolic Overdrive

#BioForge #BioForge_V0_54T #Mutation #Rarity_rare #Pathogen_UNIVERSAL #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `metabolic_overdrive`. Source: `data/bioforge/mutations/metabolic_overdrive.json`.

## Description

Accelerates the infection while exhausting its host

## Gameplay behavior

- Set `heart_rate` to **TACHY** using set on apply.
- Modify `infection_strength` using **add 0.12**, clamped to 0–1 on apply.
- Add 0.35 exhaustion every 120 ticks on continuous.

## Compatibility and selection

- Compatible pathogens: UNIVERSAL.
- Rarity: rare; random-selection weight: 25.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `metabolic`, `virulence`, `cardiac`.

## Interactions

- **hypermetabolic collapse:** with [[Hypervirulence]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

