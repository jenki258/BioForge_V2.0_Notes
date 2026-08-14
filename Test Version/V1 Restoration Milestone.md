# V1 Restoration Milestone

This milestone restores selected BioForge V1 concepts as integrated V2 systems rather than direct copies.

## Advancement tree

BioForge now has a compact 20-goal advancement tree. Its branches cover field diagnostics, blood and culture processing, laboratory engineering, chemical production, microscopy, CRISPR vaccination, and environmental containment. The V1 approach of dozens of small crafting notifications is intentionally not restored.

## Research Journal

The Research Tablet is a dependency-free in-game guide with its own tablet interface, unlock progression, cyan laboratory styling, scrollable chapters, and slot-based recipe displays. Its JSON and Java page registries cover diagnostics, blood work, cultivation, microscopy, CRISPR and vaccines, chemistry, machines, and containment. Patchouli is not required.

## Legacy mutations

The active mutation catalogue now contains 76 definitions, including 44 reworked V1 mutations and twelve tiered effect mutations. Legacy traits have real effects, conflicts, tags, and interactions. Restored concepts include climbing, camouflage, aquatic respiration, light sensitivity, night vision and night blindness, poison and blindness resistance, metabolic traits, movement and strength traits, allergies, dependencies, coughing, sneezing, fever, fatigue, panic, paranoia, and other V1 host changes.

The legacy catalogue is data-driven and supports aggregate mutation files. Custom runtime behaviors cover wall climbing, aquatic respiration, camouflage, effect clearing, and light-dependent reactions. Vaccine vulnerability is also recognized by vaccine matching logic.

## Laboratory production

Three rotating four-input machines were added:

- Chemical Synthesizer for acids, polymers, technical gels, and chemical agents.
- Sterilization Chamber for sterile solutions, sheets, filters, rubber, and glassware.
- Pharma Mixer for agar, nutrient media, and diagnostic reagents.

All three use one extensible processing engine. Recipes load from separate files in `data/*/laboratory_processing/` and may also be registered through Java. Existing crafting recipes remain available as an emergency path, while machine recipes give improved output. The Barrel Press has also returned as its own alcohol-production station with a three-dimensional inventory model.

## Containment and symptoms

The handheld Area Contamination Scanner measures nearby contaminated surfaces and airborne room reservoirs. Four redstone Viral Scanner variants provide full, ceiling, open-left, and open-right checkpoint layouts. Scanner Evasion can hide a carrier from those gates. The passive Air Vent continuously blocks and removes airborne contamination in a ten-block radius. No Medical HUD was added.

Respiratory crackles now create visible cough particles around the host. Severe tissue lesions create damage particles, and secretion events create splash particles while contaminating the contacted surface.

## Assets still required

No generated art was added. The following authored textures are expected:

- `textures/block/air_vent.png` (one texture for all faces and the inventory model)

## Deferred V1 concepts

The old Medical HUD remains explicitly excluded. A larger walk-through testing chamber could still be revisited later, but only if it adds gameplay beyond the restored redstone scanner gates.
