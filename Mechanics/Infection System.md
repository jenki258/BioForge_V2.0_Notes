# Infection System

#BioForge #BioForge_V0_54T #Mechanic #Infection #PlayerGuide #ModpackGuide #AddonDevelopment

BioForge stores an active infection as a server-authoritative strain rather than as one ordinary potion effect. A strain combines a pathogen class, transmission routes, clinical parameters, mutations, lifecycle state, identity/fingerprint, catalogue name, and treatment-relevant data.

## What an infection controls

- Whether and how the host can expose other entities, blocks, food, water, tools, or samples.
- Which clinical readings diagnostic tools can measure.
- Which mutation behaviors run after incubation.
- How long incubation lasts and whether the strain adapts to hot or cold conditions.
- Infectivity, infection strength, lifespan, cure resistance, visibility, and environmental colony limits.
- Compatibility with vaccines, pills, immunity, reports, assays, scanners, and natural-host rules.

## Authority and persistence

The server owns infection state, ticks lifecycle and behavior, saves it on entities/items/world data, and sends limited client data needed for presentation. Biological payloads are written through BioForge's NBT obfuscator, so a player cannot obtain the full intended research answer by reading ordinary item NBT.

## Competition and transfer

When a contaminated item or exposure attempts to apply a strain, BioForge validates immunity, complete infection invulnerability, route rules, PPE, enabled definitions, and existing infection state. The exact result is determined by the relevant transfer/competition code rather than blindly stacking arbitrary effects.

Related: [[Infection Lifecycle]], [[Transmission System]], [[Symptom System]], [[Mutation System]], [[Vaccines and Immunity]].

