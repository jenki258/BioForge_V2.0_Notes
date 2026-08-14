# Transmission, PPE, and symptom gameplay

#BioForge #BioForge_V0_54T #Research #LegacyUpdated

BioForge V2 treats transmission routes as independent mechanics that can also reinforce one another. A route is no longer only descriptive strain data.

## Air and rooms

`AIR_BORNE` uses a bounded room scan around the infected host. Solid walls and closed doors stop the search; open doors and other open passages connect spaces. Sealed rooms retain infectious concentration, while open, outdoor, and oversized spaces strongly dilute it. Exposure accumulates over time rather than rolling one instant chance through a wall.

A medical mask completely blocks outward airborne shedding and greatly reduces inward exposure. A complete HazCure suit blocks both directions.

## Surfaces and environmental persistence

`CONTACT_BASED` and `ENVIRONMENTAL` strains can contaminate ordinary blocks without replacing them. Walking on, interacting with, or breaking a contaminated block can expose a living entity. Rain, contact, time, and decontamination reduce the hidden contamination state.

Environmental strains remain on surfaces longer. An airborne strain that is also environmental can settle from a concentrated room onto nearby surfaces. Secretion symptoms increase surface shedding. Protective gloves block outward contact shedding; a complete HazCure suit also blocks inward surface exposure.

Thrown Decontamination Flasks clean hidden block contamination and reduce airborne concentration in the configured area. They can also destroy blocks included in the decontamination target tag.

## Other transmission routes

- `ATTACK_BASED` spreads through attacks and is stronger when combined with `BLOOD`.
- `BLOOD` is carried by infected needles and syringes, with a configurable exposure chance. A full HazCure suit cannot be pierced.
- `FOOD_BORNE` persists in infected crops, food drops, and crafted products.
- `WATER_BORNE` persists in contaminated drinks, water bottles filled from infected sources, and brewed potions.
- `ANIMALS` transfers an infected animal's strain to relevant drops, including food products.

Crafting propagates the strongest compatible strain from ingredients to the output, so processing an infected ingredient does not silently sterilize it.

## Symptom gameplay

Built-in symptoms now affect the host: heart and lung abnormalities limit exertion, low oxygen reduces underwater breathing time, poor perfusion reduces healing, neurological/reflex damage applies control penalties, lesions consume blood, secretion contaminates surfaces, and temperature instability can inflict heat or freezing damage.

Ice Bags and Magma Bags suppress the corresponding temperature hazard. A Vaccine Maker can produce a programmed Symptom Tablet from an identified symptom Gene Imprint. The tablet temporarily suppresses one symptom but does not cure the infection; quality, infection strength, and analgesic-resistance mutations affect its duration.

## Mutation expansion

The bundled set adds hypoxic, respiratory, hemorrhagic, thermal, gastrointestinal, zoonotic, surface-persistence, metabolic, analgesic-resistance, and protective-coating mutations. Their JSON definitions include cross-mutation interactions and route/symptom effects.

## Per-world modpack controls

`serverconfig/bioforge-server.toml` contains:

- a master spreading switch and one switch for every built-in transmission route;
- a master symptom switch and one switch for every built-in symptom;
- a master mutation switch and one switch for every bundled mutation;
- room volume/radius, exposure chances, surface lifetime, and decontamination radius;
- the existing vaccine, immunity, infection-strength, and blood-compatibility balance.

Disabled built-in features are filtered from generated strains, commands, machines, serialization, data reloads, runtime behavior, and microscope output. Addon-defined mutations remain controlled by their own JSON unless the global mutation switch is disabled.

## Vaccine assay feedback

Full vaccines preserve the programmed CRISPR sequence. A vaccinated blood assay can show base-by-base green/yellow/red feedback in the Microscope after calibration and scanning, while the player still receives only the combined assay result rather than separate hidden quality components.

The Vaccine Maker correction page uses explicit True/False values for binary fields, 101 states for percentages, and direct numeric entry for large colony-radius and infestation-capacity values.

