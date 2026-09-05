# Research Tablet Progression

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #ResearchTablet #Progression #Recipe #PlayerGuide #ModpackGuide #AddonDevelopment

The Research Journal item opens a large tablet-style interface, not a vanilla book. Its dark-cyan panel elements, cyan text, scrollbars, line breaks, and structured recipe widgets are part of the V0.54T design.

## Unlocks

Once the player has crafted/activated a tablet, obtaining related items can permanently unlock pages and show a discovery toast. Pages remain per-player even when the physical tablet is moved.

## Content

The bundled tablet covers diagnosis, blood, sample handling, lifecycle, routes, mutations, CRISPR, vaccines, assays, pills, chemistry, machines, containment, HazCure, Air Vent, and scanner workflows. Recipes render with station labels, GUI-like slots, item icons, counts, and alternatives rather than as a plain ingredient list.

## Administration

`/bioforge researchtablet add|remove|addall|removeall` can manage selected players' pages.

## Extension

JSON pages live under `research_journal`; Java pages and recipe views register through the public API. Addon recipe references can target crafting, laboratory processors, Centrifuge, Incubator, or Vaccine Maker operations.

Related: [[Research Journal]], [[Research Tablet API]], [[JEI and Recipe Discovery]].
# 2.1 update

The tablet keeps its guide pages while omitting low-value component-only cards from the default item index. Recipe entries use structured ingredient/output slots, and acquisition text must match the real chain (bone marrow via centrifuge; withered bone marrow via decalcification fluid).
