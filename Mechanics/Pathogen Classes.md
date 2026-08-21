# Pathogen Classes

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #Pathogen #Datapack #PlayerGuide #ModpackGuide #AddonDevelopment

Pathogen class is the broad biological family of a strain. It influences compatible mutation selection, catalyst reactions, data-driven rules, and what the Pathogen Reagent can reveal.

## Bundled classes

- **Virus** — common airborne, blood, attack, and host-adapting strains.
- **Bacteria** — strong environmental, inflammatory, and chemical-resistance possibilities.
- **Fungi** — spores, surface growth, colonies, and environmental persistence.
- **Parasite** — metabolic, diet, animal, food-chain, and neurological possibilities.
- **Prion** — neural, visibility, and treatment-resistant possibilities.
- **Universal** — a compatibility class that can use every bundled mutation; it is not a statement that the strain naturally exists everywhere.

Classes do not hard-code one transmission route or symptom list. JSON definitions and mutation compatibility create the actual strain.

## Research disclosure

[[Pathogen Reagent]] can reveal this family without revealing the exact strain, mutations, sequence, or correction matrix. This preserves a useful early diagnosis while leaving microscope and CRISPR research meaningful.

## Extension

Definitions are loaded from `data/<namespace>/bioforge_definitions/pathogens/`. Stable namespaced IDs, aliases, priorities, enable/replace rules, and Java-registered behavior keep addon content interoperable.

Related: [[Definition API]], [[Datapack Definitions]], [[Catalyst Vial]].

