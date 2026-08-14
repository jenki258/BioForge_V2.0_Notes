#BioForge #BioForge_V0_54T #AddonDevelopment #LegacyUpdated

#Addons

The biological runtime is no longer limited to the original Java enums. Pathogens, transmission routes and symptoms use stable namespaced IDs and resolve from a common versioned registry.

## What a modpack can edit

- pathogens, their colors, environmental flag, allowed routes and starting symptom ranges;
- transmission routes composed from built-in behaviors;
- typed symptoms (`boolean`, `integer`, `float`, `string`, `enum`), ranges and display metadata;
- mutations, effects, interactions, requirements, conflicts, rarity and weights;
- CRISPR profiles, Cas/PAM modules, assays and vaccine correction targets;
- Vaccine Maker, centrifuge and decalcification recipes;
- microscope entries/calibration and incubator catalyst mappings.

Definitions support schema versioning, priorities, replacements, disabling and aliases. A failed biological reload is atomic: the invalid set is rejected and the last working snapshot stays active. `/bioforge validate` explains the current state.

## What an addon can add in Java

`BioForgeAddonApi` mirrors the data systems and adds code hooks for custom transmission behavior, symptom behavior, mutation effects and Vaccine Maker operations. Addons can also register CRISPR/research definitions, machine recipes, microscope content, catalysts and Vaccine Maker pages.

All Java registrations happen before server start and are then frozen. This keeps server/client ordering deterministic and prevents a world from changing its type registry in the middle of a tick.

Custom pathogen IDs are preserved across the physical gameplay loop: catalyst vial, Incubator generation, samples and contaminated items, microscope, CRISPR, correction, vaccines, immunity and transmission runtime. Legacy enum getters still report a compatible fallback for old addon code, but internal identity comparisons use canonical IDs.

## Compatibility

Old IDs, enums, recipes, commands and machine behavior remain intact. Infection saves now contain canonical pathogen/transmission IDs plus legacy fields. Old worlds and old strain strings upgrade automatically. Server definitions are synchronized to clients and are resent after `/reload`.

The practical format reference, working examples and Java setup are in `BIOFORGE_ADDON_CREATION_GUIDE.md` in this folder.
