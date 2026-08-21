# Pharma Mixer

#BioForge #BioForge_V2_0 #Build_V0_54T #Block #Machine #Pharmaceutical #PlayerGuide #ModpackGuide #AddonDevelopment

> Registry ID: `bioforge:pharma_mixer`. Station ID: `pharma_mixer`.

## Purpose

The Pharma Mixer handles biological and pharmaceutical formulations that require more ingredients and produce residue. It has a distinct GUI and is the late production station for clean growth media and diagnostic reagents.

## Inventory

- Five input slots.
- One primary result slot.
- One separate waste slot.

The waste slot is not interchangeable with the result. A recipe waits if either required output cannot fit. Bundled operations produce Agar Powder, Nutrient Medium, Pathogen Reagent, and Visibility Reagent, normally returning [[Laboratory Waste]].

## Recipes and extension

Use one JSON file per operation under `data/<namespace>/laboratory_processing/` with `"station": "pharma_mixer"`, an output, optional waste, processing time, and up to five ingredient objects.

Related: [[Nutrient Medium]], [[Pathogen Reagent]], [[Visibility Reagent]], [[Laboratory Recipe API]].

