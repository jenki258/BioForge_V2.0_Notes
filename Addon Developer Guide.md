# Addon Developer Guide

#BioForge #BioForge_V2_0 #Build_V0_54T #AddonDevelopment #JavaAPI #JSONAPI #Datapack

> Target environment: Minecraft 1.20.1, Forge 47.4.10, Java 17, BioForge addon API version 3.

## Pick the smallest extension surface

- Use JSON when existing BioForge behavior can express the content.
- Use Java for genuinely new runtime behavior, machine logic, page logic, or effect handlers.
- Use a hybrid addon when Java supplies behavior and JSON supplies strains, recipes, tuning, and pack-overridable content.

## Reference by subsystem

- [[Definition API]] — pathogens, symptoms, transmissions, aliases, priorities, and behaviors.
- [[Mutation API]] — definition lifecycle, effects, interactions, requirements, conflicts, and custom handlers.
- [[Infection Lifecycle API]] — incubation, climate adaptation, lifespan, infectivity, cure resistance, and natural strains.
- [[Laboratory Recipe API]] — Chemical Synthesizer, Pharma Mixer, Sterilization Chamber, Barrel Press, Centrifuge, and Incubator.
- [[Microscope API]] — sample mappings, symptom presentation, visibility, calibration, and assays.
- [[Vaccine Maker API]] — recipes, CRISPR profiles, Cas/PAM modules, actions, correction profiles, and Java pages.
- [[Research Tablet API]] — JSON and Java pages, unlocks, item triggers, and recipe views.
- [[Biological NBT API]] — safe read/write/copy boundaries and obfuscation.
- [[Addon Compatibility Checklist]] — registration timing, client/server boundaries, validation, and stable IDs.
- [[Localization and Translation]] — translation keys, resource-pack responsibilities, and known literal fallbacks.

The exhaustive, copy-ready guide remains at [[BioForge addon creation guide]]. The shorter pages above are designed for quick lookup and linking from individual content pages.
