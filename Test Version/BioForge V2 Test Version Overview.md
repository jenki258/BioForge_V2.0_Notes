# BioForge V2 Test Version Overview

This page is the authoritative feature map for the current BioForge V2 test build. It describes what exists now, how the systems connect, and which parts still need an in-game test pass.

## What BioForge V2 is

BioForge V2 is a medical-research and infection-engineering mod. The intended experience is not simply “get sick, drink a cure.” A player observes a patient, collects biological material, separates and cultures samples, identifies useful genetic information, builds a CRISPR program, synthesizes an appropriate vaccine, and then deals with treatment resistance and mutation risk.

The central design rules are:

- Information is earned through tools and machines.
- A sample, report, gene, and vaccine refer to an exact infection rather than a generic disease flag.
- Blood type, Rh factor, infection strength, mutations, symptoms, and transmission routes can affect research or treatment.
- Failure creates gameplay: bad synthesis can waste material or mutate the strain.
- Modpack authors can extend most research content through JSON instead of replacing Java code.

See [[Integrated Gameplay Loop]] for the complete player journey.

## Current system map

### Blood and sampling

The mod tracks blood amount, blood group, Rh factor, donor identity, reagent knowledge, and infection data where relevant. Needles, syringes, test tubes, blood slides, plasma samples, and cell pellets move that information between field work and laboratory machines.

Current behavior:

- Blood collection is tied to intentional direct interaction. Indirect damage and explosions no longer make the player accidentally collect their own blood.
- A filled Test Tube can transfer blood back into an empty syringe, or into a syringe that already contains compatible blood. Infection data transfers with the blood.
- The JEI blood-tube recipe displays a genuinely filled tube rather than an empty visual substitute.
- Sensitive item data uses the NBT obfuscation layer, including newer research and vaccine items.

See [[Blood Mechanic]], [[Needle]], [[Syringe]], [[Test Tube]], [[Blood Slide]], [[Plasma Sample]], and [[Cell Pellet]].

### Diagnostics and documentation

The Clipboard assigns a patient and gathers readings from medical tools. The Thermometer, Stethoscope, Pulse Oximeter, Otoscope, Reflex Hammer, and blood reagents feed one medical record instead of unrelated minigames.

- Clipboard data can be printed into a Medical Report.
- Medical Reports can be copied with paper and stack up to 16.
- Clipboard and report text can be appended to a Book and Quill without deleting the source record.
- The book GUI is suppressed during transfer.
- Tooltips explain copy and book actions.
- Temperature readings are included in Clipboard data.
- Reports used by the Vaccine Maker are bound to the exact infection they describe.

See [[Clipboard]], [[Medical Report]], and [[CRISPR Notes]].

### Laboratory machines

| Machine | Current role |
|---|---|
| [[Centrifuge]] | Converts configured biological inputs into weighted outputs such as plasma, cell pellets, or marrow products. |
| [[Microscope]] | Calibrates and analyzes supported samples; reveals configured symptoms and identifies an unknown Gene Imprint. |
| [[Incubator]] | Runs JSON-defined biological recipes for generating or cloning samples and cultures. Recipes appear in JEI. |
| [[Vaccine Maker]] | Programs CRISPR guides, records or loads notes, evaluates quality, and synthesizes full, directed, random-mutation, or cloned vaccines. |

The Incubator and Microscope title/inventory text now use the same color language as the Centrifuge. Microscope and Vaccine Maker controls support dedicated button textures.

### Infection and world growth

Infections contain a pathogen type, strength, symptoms, transmission information, mutation set, persistence settings, and reproducible strain identity. World-facing infection blocks include the Petri Dish, Microbial Mat, Sporocarp, Necrotic Patch, Contaminated Substrate, Colony Core, Infested Block, and infected crops.

The existing pages under `Blocks/Infection Connected` describe the environmental pieces. The exact-strain research catalogue sits on top of that infection model; it does not replace world spread.

### Mutations

Mutations are live data-driven behaviors rather than passive labels. They can alter symptoms, add or remove infection types, apply potion or attribute effects, cause damage or healing, create particles and sounds, and interact with other mutations.

Runtime state refreshes after login, respawn, load, and data reload so continuous effects do not silently disappear. The mutation scrolling overlay is used when an actual mutation is selected or synthesis failure mutates a source strain.

Bundled examples include Bloodborne, Hypervirulence, Necrotic Fever, Neural Decay, Spore Cloud, Vaccine Defense, and Reinforced Vaccine Defense. See [[Mutations]].

### CRISPR research

The default guide profile uses `A`, `C`, `G`, `U`. A full program contains 15 cartridges, four bases per cartridge, for 60 bases divided into three five-cartridge guides:

1. Replication core
2. Clinical expression
3. Immune escape

The correct program derives from the exact strain and guide profile. The player edits cartridges instead of receiving the target sequence directly.

Cas modules have gameplay data: PAM pattern, efficiency, compatible guide profiles, compatible pathogen families, and a display name. Bundled definitions include SpCas9, Cas12a, and Cas13d. See [[CRISPR and Vaccine Maker]].

### Vaccines and immunity

| Family | Purpose |
|---|---|
| Full Strain Vaccine | Attempts to cure a matching or sufficiently similar infection and grants temporary exact-strain immunity after success. |
| Mutation Vaccine | Adds or removes/opposes a selected mutation according to its Gene Imprint and action. |
| Transmission Vaccine | Adds or removes/opposes a selected transmission route. |
| Symptom Vaccine | Adds, removes, or reduces a selected symptom parameter. |
| Random Mutation Vaccine | Adds one random compatible mutation to the active matching infection without immediately revealing it. |

Full treatment is intentionally probabilistic. Quality, strain similarity, infection strength, vaccine-defense mutations, ABO/Rh research data, and server balance participate. Immunity duration scales with quality and is visible from the inventory immunity readout and effect tooltip. See [[Vaccines and Immunity]].

### Strain discovery and naming

Every researchable strain has a fingerprint. When a strain is first recorded, the first researcher/host receives a naming GUI automatically. The server validates the request and allows the first public name only once. Administrators can list and rename catalogue entries for moderation.

Names are shown on catalogued Live Culture Vials, sufficiently complete Medical Reports, and immunity information. Vaccines, Gene Imprints, and CRISPR Notes do not reveal the strain name. The Live Culture Vial also hides raw pathogen/symptom details and instead points the player toward lab analysis. See [[Strain Catalogue]].

### JSON, modpacks, and addons

Current JSON-facing systems include:

- Mutations and mutation interactions
- CRISPR guide profiles, Cas modules, and assay settings
- Vaccine Maker recipes and vaccine actions
- Incubator recipes and catalyst mappings
- Microscope symptom layouts
- Centrifuge and decalcification recipes
- Entity and block behavior tags

The Vaccine Maker exposes a page definition and client rendering registry so another mod can add a top tab without replacing the base menu. See [[JSON and Addon Support]].

## Current content inventory

### Research items

- Full, Mutation, Transmission, Symptom, and Random Mutation vaccines
- CRISPR Cartridge, Cas Module, Gene Imprint, and CRISPR Notes
- Catalyst Vial, Nutrient Medium, Virus Sample, Live Culture Vial, and Dirty Culture Vial

### Medical and laboratory items

- Wooden, Iron, and Hardened Needles
- Syringe, Test Tube, Blood Slide, Plasma Sample, and Cell Pellet
- Anti-A, Anti-B, and Anti-D Reagent Vials
- Thermometer, Stethoscope, Otoscope, Mirror, Reflex Hammer, and Pulse Oximeter
- Clipboard, Medical Report, Swab, and Petri Dish
- Bone Saw, split-bone variants, marrow variants, and Decalcification Fluid
- Ethanol and Wipes

### Blocks

- Centrifuge, Microscope, Incubator, and Vaccine Maker
- Microbial Mat, Petri Dish, Sporocarp, Necrotic Patch, Contaminated Substrate, Colony Core, Infested Block, and infected crops

## Presentation and visual state

- Vaccines use a syringe model with a tint layer. A strain produces stable color variation; vaccine families use different base palettes.
- Gene Imprints have unknown, category, and symptom-specific model routes.
- Vaccine Maker pages use separate textures, optional textured buttons, and an `18x19` slot texture with the lower shadow while preserving the normal item area.
- Dense explanations moved from permanent GUI text into contextual tooltips.
- CRISPR quality appears numerically while editing.
- The upgraded mutation scroll is connected to real outcomes.

## Validation status

At the time this page was written:

- All 225 Java source files passed a direct Java 17 compilation check.
- Bundled JSON resources passed syntax validation.
- Gradle was intentionally not used for the last validation pass.
- A full in-game single-player and dedicated-server smoke test is still required.

Compilation proves that the code links at build time; it does not prove every GUI, recipe, network packet, resource texture, or persistence path behaves correctly in Minecraft. Use [[Testing Checklist]] before calling the test version release-ready.

## Related pages

- [[Integrated Gameplay Loop]]
- [[Test Version Changelog]]
- [[Testing Checklist]]
- [[Research Systems]]
- [[BioForge Command Reference]]

