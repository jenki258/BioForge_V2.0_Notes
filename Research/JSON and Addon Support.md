# JSON and Addon Support

#BioForge #BioForge_V2_0 #Build_V0_54T #Research #LegacyUpdated

#Extra 

BioForge V2 exposes research and laboratory content through server data packs so modpacks can change recipes, balance, mutation behavior, and supported analysis without editing BioForge Java.

## Data folders

| Folder | Purpose |
|---|---|
| `data/<namespace>/mutations/` | Mutation definitions/interactions |
| `data/<namespace>/crispr/guide_profiles/` | Alphabet, cartridge grouping, and guide sources |
| `data/<namespace>/crispr/cas_modules/` | Cas/PAM names, efficiency, and compatibility |
| `data/<namespace>/crispr/assays/` | Assay growth cost and score display |
| `data/<namespace>/vaccine_maker/` | Full, directed, random, and clone recipes |
| `data/<namespace>/vaccine_actions/` | Directed target actions |
| `data/<namespace>/recipes/` using `bioforge:incubator` | Incubator recipes |
| `data/<namespace>/incubator/catalyst_mappings/` | Catalyst mappings |
| `data/<namespace>/microscope/` | Samples, calibration, entries, and visibility |
| `data/<namespace>/centrifuge/` | Centrifuge inputs and weighted outputs |
| `data/<namespace>/decalcification/` | Decalcification conversions |
| `data/<namespace>/tags/entity_types/` | Blood/diagnostic/infection rules |
| `data/<namespace>/tags/blocks/` | Infectable crops/substrate categories |

Keep reloadable IDs stable after worlds store them.

## Vaccine Maker recipes

### Core fields

- `operation`: `full`, `directed`, `random_mutation`, or `clone`
- `guide_profile`
- `processing_time`
- `requires_program`
- `minimum_quality`

### Inputs

- `sample`
- `carrier`
- `reagent`
- optional `report`
- optional `cartridge`
- optional `cas_module`

Inputs use Minecraft Ingredient JSON, allowing an item, tag, or supported list.

### Quality and research

- `quality.guides`: exactly three weights for the current three-guide score
- `quality.cas_module`, `sample`, `carrier`, `reagent`
- `research.base_quality_cap`
- `research.finding_bonus`
- `research.complete_blood_bonus`
- `research.identified_imprint_bonus`

### Consumption and failure

- `consume_sample`, `consume_reagent`, `consume_report`
- `failure.mutation_chance`
- `failure.mutation_below_quality`
- `failure.consume_reagent`

### Result

Full/random recipes use `result.item`. Directed recipes use category maps under `result.items` and `result.actions`. Common fields include `uses` and `defense_risk`.

Example shape:

```json
{
  "operation": "directed",
  "guide_profile": "bioforge:default",
  "processing_time": 200,
  "requires_program": true,
  "minimum_quality": 0.35,
  "inputs": {
    "sample": { "item": "bioforge:virus_sample" },
    "carrier": { "item": "bioforge:mutation_vaccine" },
    "reagent": { "item": "bioforge:gene_imprint" },
    "cartridge": { "item": "bioforge:crispr_cartridge" },
    "cas_module": { "item": "bioforge:cas_module" }
  },
  "research": {
    "base_quality_cap": 0.85,
    "identified_imprint_bonus": 0.15
  },
  "failure": {
    "mutation_chance": 0.95,
    "mutation_below_quality": 0.95
  },
  "result": {
    "items": { "mutation": "bioforge:mutation_vaccine" },
    "actions": { "mutation": "bioforge:mutation_auto_opposite" },
    "uses": 1
  }
}
```

## Guide profiles

The bundled default profile uses alphabet `ACGU`, cartridge size 4, five cartridges per guide, and three guides. Each guide has a name, deterministic salt, and source lists such as pathogen/core, pathogen/transmission/symptoms, or pathogen/mutations/symptoms.

Changing alphabet, grouping, salt, or sources changes derived target programs. Coordinate recipes, GUI assumptions, and saved templates before altering an established world's default profile.

## Cas modules

```json
{
  "display_name": "SpCas9 Precision Module",
  "pam": "NGG",
  "efficiency": 0.92,
  "compatible_guide_profiles": ["bioforge:default"],
  "compatible_pathogens": ["bacteria", "parasite"]
}
```

Compatibility should create a real choice. One universal best module removes this part of the loop.

## Mutations and actions

See [[Mutations]] for effect/interaction fields. Use weights and prerequisites for random pools, `weight: 0` for compound-only results, semantic tags for cross-system meaning, and stable IDs. Validate interaction grant chains for loops.

Directed vaccine actions are separate JSON resources. Bundled auto-opposite actions cover mutation, transmission, and symptom targets.

## Incubator, Microscope, and JEI

Incubator recipes use the registered `bioforge:incubator` type with primary/secondary inputs, output, operation, processing time, and item/charge costs. JEI reads the recipe set so pack-added work can be discoverable.

Microscope JSON maps items to calibration and entries. Entries can read strain or NBT sources, use boolean/float/enum display, require visibility levels, and select icons/states. This is the route for making another mod's sample analyzable.

## Per-world serverconfig

World-specific balance includes the full-vaccine similarity curve/cap, infection-strength resistance, defense mutation scales, immunity duration, ABO/Rh multipliers, and preferred post-failure defense mutation. It also includes master and per-built-in switches for spreading routes, symptoms, and mutations, plus room/surface/exposure balance. Disabled built-ins are filtered from generation, storage, machines, commands, microscope output, and runtime behavior. Addon mutations remain JSON-controlled unless the global mutation switch is disabled. See [[Vaccines and Immunity]] and [[Transmission, PPE and Symptom Gameplay]] for defaults and behavior.

## Addon pages

- `VaccineMakerPageDefinition`: ID, order, title, icon, visible slots.
- `VaccineMakerPageRegistry`: shared definition registry, up to 64 pages.
- `VaccineMakerPageRenderer`: optional client rendering.

A renderer alone never decides inventory results. New server behavior still requires validated recipes, menu operations, or networking.

## Reload policy

- Use `/reload` for supported data-pack changes.
- Back up worlds before changing stable mutation/profile/action IDs.
- Test dedicated-server reload and malformed JSON behavior.
- Confirm BioForge starts without JEI when JEI is optional.
