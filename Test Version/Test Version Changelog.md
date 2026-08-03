#Extra 

This records the completed work represented by the current BioForge V2 test source. It is grouped by system rather than commit.

## Blood, sampling, and tools

- Fixed JEI displaying an empty Test Tube for the filled-blood recipe.
- Prevented explosions and indirect damage, including End Crystal explosions, from triggering accidental self-blood collection.
- Added Test Tube -> compatible Syringe blood transfer, including infection transfer.
- Made the Thermometer unable to break blocks while swung/prepared.
- Fixed Thermometer readings not being written to the active Clipboard.

## Clipboard and documents

- Fixed mob selection with the Clipboard.
- Fixed the target-change message sometimes appearing twice.
- Added Clipboard -> Medical Report printing and exact-infection binding.
- Added Medical Report copying with paper and stack size 16.
- Added Medical Report/Clipboard -> Book and Quill export without clearing source data.
- Prevented the book GUI from opening during transfer.
- Added interaction tooltips.
- Added separate CRISPR Notes, cloning, and template loading.
- Applied NBT obfuscation to newer research/document items with supported legacy reads.

## GUI and interaction

- Matched Incubator/Microscope text colors to the Centrifuge.
- Reworked Vaccine Maker into CRISPR, Journal, and Synthesis pages sharing one inventory.
- Kept crafting slots on Synthesis while exposing document/Gene Imprint research interactions on CRISPR.
- Separated the Medical Report/document slot from the reagent slot.
- Moved dense explanations into tooltips.
- Added numerical CRISPR quality and corrected base-changing hitboxes.
- Added page/button textures and an `18x19` slot-frame resource with lower shadow.
- Added compatible textured controls for Microscope buttons.

## Incubator and JEI

- Converted Incubator processing into JSON recipes.
- Added Incubator JEI integration.
- Added bundled generation/cloning recipes and kept catalyst mappings data-driven.

## Mutations

- Reworked mutations into reloadable JSON definitions.
- Added pathogen compatibility, rarity, weight, enabled/hidden state, icons, tags, requirements, and conflicts.
- Added apply, continuous, and remove triggers.
- Added symptom/infection-route changes, potions, particles, attributes, damage, healing, exhaustion, ignition, and sounds.
- Added mutation interactions that modify/suppress effects, add effects, grant mutations, or remove mutations.
- Added compound behavior such as Reinforced Vaccine Defense.
- Reapplied runtime effects after login, respawn, load, and data reload.
- Expanded `/bioforge mutate` administration/inspection.
- Connected the upgraded mutation scroll to real mutation and synthesis-failure events.

## CRISPR and Vaccine Maker

- Added 15 editable four-base CRISPR cartridges and three guide groups.
- Added data-driven guide profiles and functional Cas/PAM compatibility/efficiency.
- Added localized Cas and Gene Imprint target names.
- Added unknown Gene Imprints identified in the Microscope.
- Allowed complete templates to load into 15 cartridges regardless of current sample/Cas mismatch.
- Added exact-strain report evidence, quality caps, finding/blood/imprint bonuses.
- Added button and rising-redstone synthesis.
- Added recipe-defined time, consumption, weights, minimum quality, uses, and defense risk.
- Added low-quality mutation failure.
- Added addon page and client renderer registries.

## Vaccines, immunity, and naming

- Added Full Strain, Mutation, Transmission, Symptom, and Random Mutation vaccine families.
- Fixed specialized carrier insertion/recipe validation.
- Required directed carrier/imprint and clone-family matches.
- Added JSON vaccine actions with auto-opposite behavior.
- Made full curing probabilistic through quality, similarity, strength, blood/Rh, and defense mutations.
- Moved cure balance into per-world `serverconfig`.
- Added temporary exact-strain immunity with quality-scaled duration and inventory/effect display.
- Added automatic first-discovery naming GUI and administrator moderation commands.
- Restricted strain names to appropriate cultures, complete reports, and immunity UI.
- Reduced Live Culture Vial disclosure and removed names from vaccines/notes/imprints.

## Visuals and maintenance

- Changed vaccines to shared syringe models with family palettes and stable strain tint variation.
- Added unknown/category/symptom model routes for Gene Imprints.
- Removed Java source comments as requested.
- Directly compiled all 225 Java files with Java 17 without Gradle.
- Validated bundled JSON syntax.

