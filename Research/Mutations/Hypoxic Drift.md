# Hypoxic Drift

#BioForge #BioForge_V2_0 #Build_V0_54T #Mutation #Rarity_uncommon #Pathogen_VIRUS #Pathogen_BACTERIA #Pathogen_PARASITE #PlayerGuide #ModpackGuide #AddonDevelopment

> Mutation ID: `hypoxic_drift`. Source: `data/bioforge/mutations/hypoxic_drift.json`.

## Description

Reduces host oxygen saturation and becomes neurotoxic beside respiratory adaptations

## Gameplay behavior

- Modify `oxygen_saturation` using **add -0.18**, clamped to 0.15–1 on apply.
- Play `minecraft:entity.player.breath` every 100 ticks (25% chance) on continuous; configured as a gameplay event where supplied.

## Compatibility and selection

- Compatible pathogens: VIRUS, BACTERIA, PARASITE.
- Rarity: uncommon; random-selection weight: 45.
- No mutation prerequisite.
- No explicit mutation conflict.
- Behavior tags: `respiratory`, `oxygen`.

## Interactions

- **respiratory hypoxia:** with [[Respiratory Shedding]]; adds 1 extra effect(s).

## Pack and addon notes

- Enabled definitions participate in compatible weighted selection after requirements and conflicts are checked.
- Keep the ID stable once worlds have saved it. Replace/tune the JSON through a datapack or register new executable effect behavior in Java.

Related: [[Mutation System]], [[Mutation Interactions]], [[Mutation API]].

