# CRISPR and Vaccine Maker

#BioForge #BioForge_V2_0 #Build_V0_54T #Research #LegacyUpdated

#Blocks 

The Vaccine Maker combines editable CRISPR guides, a sample, functional Cas/PAM module, vaccine carrier, clinical evidence, and recipe-defined synthesis.

## One shared inventory

| Slots | Purpose |
|---|---|
| 0-14 | Fifteen CRISPR Cartridges |
| 15 | Cas Module |
| 16 | Infection Sample |
| 17 | Vaccine Carrier |
| 18 | Reagent or Gene Imprint |
| 19 | Output |
| 20 | Medical Report, CRISPR Notes, Paper, or Book and Quill |

Every machine slot currently has a limit of one. Pages change visibility, not inventory ownership.

## Pages

### CRISPR

Programming view with 15 cartridge positions, four editable bases per cartridge, guide grouping, numeric quality, Cas/PAM feedback, Gene Imprint access, the document slot, and write/load actions. Physical crafting slots are not all rendered here because this page is for research.

### Journal

Summarizes research, report evidence, and contextual explanations. Dense text uses hover tooltips to remain readable in translated GUIs.

### Synthesis

Shows every physical slot, output, processing state, quality, and Synthesize control.

Built-in page IDs are `bioforge:crispr`, `bioforge:journal`, and `bioforge:craft`. The registry supports up to 64 pages. Addons can register a definition with ID, order, title, icon, and visible slots, plus an optional client renderer. Custom rendering does not grant server authority over items or recipes.

## Sequence model

The default guide profile defines:

- Alphabet: `ACGU`
- Cartridge size: 4
- Cartridges per guide: 5
- Guide count: 3
- Total cartridges: 15
- Total bases: 60

Default guides:

1. `replication_core` derives from pathogen/core data.
2. `clinical_expression` derives from pathogen, transmission, and symptoms.
3. `immune_escape` derives from pathogen, mutations, and symptoms.

The same exact strain/profile produces the same target program, so templates are useful but not universal. Clicking one of four base positions cycles through the profile alphabet; corrected hitboxes keep the edited position aligned with the visual letter.

## Cas/PAM modules

A Cas Module definition provides:

- `display_name`
- `pam`
- `efficiency`
- `compatible_guide_profiles`
- `compatible_pathogens`

Bundled modules are SpCas9, Cas12a, and Cas13d. A module may be correct for one pathogen/profile and unsuitable for another. Its efficiency contributes according to the active recipe.

## Gene Imprints

A Gene Imprint represents one Mutation, Transmission, or Symptom target. It can begin unknown. Extraction/placement does not expose the target; Microscope analysis identifies it and assigns the localized name.

Visual routing supports unknown, category-level, and symptom-specific models. Raw IDs are not intended as player-facing labels.

## Medical evidence

The Report slot is separate from the reagent slot. A Medical Report contributes only when bound to the exact infection being synthesized.

Recipes can define:

- Base quality cap without research
- Bonus per finding
- Complete blood-analysis bonus
- Identified-imprint bonus
- Whether the report is consumed

The bundled documented full recipe begins with a reduced cap, making diagnostics and blood testing part of vaccine research.

## CRISPR Notes

CRISPR Notes are separate from Medical Reports.

Writing:

- All 15 cartridges must be installed and complete.
- Paper or a Book and Quill occupies the document slot.
- Write records the current program.
- Notes can be cloned with paper without destroying the source.

Loading:

- All 15 cartridge destinations must be installed.
- A template loads even if the current sample or Cas differs.
- A mismatch may produce poor quality but does not make the template unusable.
- Notes do not reveal the public strain name.

## Carrier safety and recipe families

- Blank full carrier -> Full Strain Vaccine
- Mutation carrier -> Mutation Vaccine
- Transmission carrier -> Transmission Vaccine
- Symptom carrier -> Symptom Vaccine
- Random mutation carrier -> Random Mutation Vaccine

Directed carrier family must match the Gene Imprint category. Clone output must match the source family. These rules prevent a shared recipe shape from converting one vaccine family into another.

## Quality

A recipe can weight the three guide scores, Cas module, sample, carrier, and reagent. It then applies the research cap and eligible evidence bonuses, and may require a minimum quality.

The GUI recalculates a numerical estimate when the program or relevant inputs change, without exposing every hidden strain value.

## Starting and failure

Processing starts through the Synthesize button or a rising redstone signal. Continuous power does not intentionally retrigger every tick. Output must be free and all server-side recipe checks must pass.

Recipes control processing time, input consumption, output uses, defense risk, mutation threshold, mutation chance, and whether reagent is consumed on mutation. A low-quality failure can mutate the source and play the mutation scroll.

## JEI and textures

Vaccine Maker recipes appear in JEI. Supported GUI resources include page backgrounds, tabs, buttons, and an `18x19` slot frame whose lower pixel is the shadow around a normal item area. Optional resources retain a readable fallback.

## Related pages

- [[Vaccines and Immunity]]
- [[Strain Catalogue]]
- [[JSON and Addon Support]]

