# Datapack Definitions

#BioForge #BioForge_V2_0 #Build_V0_54T #Datapack #JSONAPI #ModpackGuide #AddonDevelopment

Reloadable directories include core definitions, mutations, lifecycles, natural infections, CRISPR guide/Cas/assay data, vaccine actions/correction/recipes, laboratory processing, Centrifuge, Incubator catalyst mappings, Microscope mappings, Research Tablet pages, recipes, and tags.

Use namespaced stable IDs, priorities, replace/enable fields where supported, finite values inside schema ranges, and language/resource entries for player-facing content. Run `/reload` followed by `/bioforge validate`.

JSON composes existing behavior. If a new definition needs executable logic unavailable in BioForge, register a Java behavior first and reference its ID from JSON.

Complete examples: [[BioForge addon creation guide]], [[Definition API]], [[Mutation API]].
