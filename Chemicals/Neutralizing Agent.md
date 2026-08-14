# Neutralizing Agent

#BioForge #BioForge_V0_54T #Item #Chemicals #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: implemented in V0.54T.

## Overview

This chemical or processed reagent occupies a defined step in BioForge's sterile production chain.

## Obtaining

- **crafting shapeless** (`neutralizing_agent.json`): `#bioforge:ingredients/minecraft/bone_meal`, `#bioforge:ingredients/minecraft/charcoal`, [[Sterilizing Solution]], `#bioforge:ingredients/minecraft/potion` → 2 × Neutralizing Agent.
- **[[Chemical Synthesizer]]** (`neutralizing_agent.json`): `#bioforge:ingredients/minecraft/bone_meal`, `#bioforge:ingredients/minecraft/charcoal`, [[Sterilizing Solution]] → 3 × Neutralizing Agent in 180 ticks.

## Function

- Its behavior is defined by its recipe role and linked workstation or equipment system.

## Progression connections

- Used to produce: [[Decontamination Flask]], [[Symptom Suppressant Tablet]].

## Stored data and safety

- It carries no readable biological payload by default, although contaminated ingredients can still propagate a strain.

## Registry and pack integration

- Registry ID: `bioforge:neutralizing_agent`.
- Preferred ingredient tag: `#bioforge:ingredients/bioforge/neutralizing_agent`.
- Recipes can be replaced without renaming the stable item ID; JEI and the Research Tablet display loaded recipes.

## Related pages

- [[Progression and Advancements]]
- [[Recipe and Tag Compatibility]]
- [[NBT Obfuscation and Biological Data]]

