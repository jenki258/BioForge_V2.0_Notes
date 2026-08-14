# Chemical Synthesizer

#BioForge #BioForge_V0_54T #Block #Machine #Chemistry #PlayerGuide #ModpackGuide #AddonDevelopment

> Registry ID: `bioforge:chemical_synthesizer`. Station ID: `chemical_synthesizer`.

## Purpose

The Chemical Synthesizer performs controlled reagent production. It is not a reskinned Pharma Mixer: its GUI, slot layout, recipes, station identity, JEI display, texture, and progression role are separate.

## Inventory

- Three input slots.
- One result slot.
- No waste slot.

When a matching JSON recipe is present, all required inputs are validated, progress advances server-side, and the result is placed in the output only when it can fit. Bundled processes include Sulfuric Acid, Ethanol, Sterilizing Solution, Polymer Resin, Neutralizing Agent, Decalcification Fluid, Surfactant Concentrate, and Thermal Gel.

## Recipes and extension

Each operation is one file under `data/<namespace>/laboratory_processing/` with `"station": "chemical_synthesizer"`. Inputs may use tags. Recipe files are independently replaceable and appear in JEI and the Research Tablet.

Related: [[Chemicals]], [[Laboratory Recipe API]], [[Recipe and Tag Compatibility]].

