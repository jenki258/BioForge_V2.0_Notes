# Integrated Gameplay Loop

BioForge V2 is one connected investigation loop. Machines and tools solve different parts of the same case instead of acting as isolated crafting tables.

`Patient -> diagnostics -> sample -> separation/culture -> microscope -> exact-strain evidence -> CRISPR program -> vaccine -> treatment/immunity -> changed strain or new case`

## 1. Encounter and name a case

A player or mob becomes infected through the infection and world-spread systems. The infection has an exact fingerprint before players know its public name or internal parameters. The first eligible discovery can open the strain-naming GUI. Naming is a catalogue action, not a way to reveal the entire strain.

## 2. Build a medical record

The researcher assigns the patient with a Clipboard and uses the Thermometer, Stethoscope, Pulse Oximeter, Otoscope, Reflex Hammer, and Anti-A/B/D blood reagents. The Clipboard combines those measurements into one patient session.

It can print a Medical Report or append a readable summary to a Book and Quill. Copying does not delete the source data. A report bound to the exact infection can later raise Vaccine Maker quality; complete blood analysis can provide an additional bonus. A report from the wrong strain does not count.

## 3. Collect and prepare material

Needles, syringes, tubes, slides, swabs, marrow, and culture items bridge the patient and the laboratory.

Typical paths:

- Blood -> Test Tube -> Centrifuge -> Plasma Sample or Cell Pellet
- Infection sample -> Incubator -> Virus Sample or cloned culture
- Culture/sample -> Microscope -> biological findings
- Test Tube -> compatible Syringe when blood must be moved back into an injection tool

Donor identity and infection data follow the sample where supported. Explosions and unrelated damage cannot create a blood sample.

## 4. Grow or clone the strain

The Incubator is a JSON-driven biological crafting station. Bundled recipes generate a Virus Sample from a charged Catalyst Vial and Nutrient Medium and clone supported infected material. JEI exposes these recipe structures while supported operations preserve exact strain data.

## 5. Analyze without receiving every answer

The Microscope controls disclosure through calibration and configured visibility. A Gene Imprint can begin unidentified: the Vaccine Maker holds/extracts it, but the Microscope identifies its category and target. The extraction action therefore does not immediately reveal the answer.

Live Culture Vials follow the same principle. Their tooltip confirms culture/catalogue status and points toward laboratory analysis instead of dumping raw pathogen, symptoms, and mutations.

## 6. Program CRISPR

The researcher installs all 15 cartridges and edits four bases on each. The default 60-base `A/C/G/U` program is divided into three guides. The Cas module must fit the selected profile and pathogen; PAM and efficiency affect suitability and quality.

The CRISPR page shows the editable program, document slot, Gene Imprint access, and numerical quality. A complete 15-cartridge set can load a template even if the current sample or Cas differs, making notes reusable for experimentation.

## 7. Record or reuse research

With all 15 cartridges complete, paper or a Book and Quill in the document slot can create CRISPR Notes. Notes can later load the program back into 15 installed cartridges and can be cloned with paper.

- Medical Report: clinical and blood evidence for an exact infection.
- CRISPR Notes: reusable sequence template.

The two documents are intentionally separate.

## 8. Assemble the Vaccine Maker

The Synthesis page displays one shared machine inventory:

- 15 CRISPR Cartridges
- 1 Cas Module
- 1 Sample
- 1 Carrier
- 1 Reagent or Gene Imprint
- 1 dedicated Report/Document
- 1 Output

Full, Mutation, Transmission, Symptom, and Random Mutation carriers select their own families. Directed carrier family must match the Gene Imprint category. Clone recipes preserve the source family.

## 9. Evaluate quality and risk

Quality is assembled from guide accuracy, Cas suitability, sample/carrier/reagent contributions, the recipe's base quality cap, exact-strain report findings, complete blood evidence, and identified-imprint evidence.

The GUI displays a numeric estimate without revealing every hidden strain fact. Modpack authors can change weights, caps, bonuses, and minimum quality through JSON.

## 10. Synthesize

Processing starts from the Synthesize button or a rising redstone signal. The output must be free and the recipe valid. Processing time and input consumption are recipe-defined.

A bad program can mutate the source instead of simply doing nothing. Recipes define the failure threshold, chance, and consumption behavior. When a mutation is selected, the real mutation scrolling presentation plays.

## 11. Treat the patient

Full-vaccine success considers quality, strain similarity, infection strength, vaccine-defense mutations, host and researched ABO/Rh compatibility, and server balance. Even an exact vaccine is not guaranteed to cure.

Directed vaccines manipulate one selected mutation, transmission route, or symptom through their JSON action. If the parameter is absent, the default opposite behavior can introduce it, preserving the dangerous engineering style of BioForge V1.

The Random Mutation Vaccine chooses one compatible mutation without immediately identifying it. The researcher must analyze the result.

## 12. Immunity and follow-up

A successful Full Strain Vaccine grants temporary immunity to that exact fingerprint. Quality scales the server-configured base duration from approximately 50% to 150%. Inventory and effect tooltips show the catalogued infection name and remaining time without exposing unrelated strains.

Immunity expires and strains can change. The loop returns to diagnosis rather than permanently ending after one syringe.

## What each system contributes

| System | Unique contribution |
|---|---|
| Diagnostic tools | Observable patient state |
| Clipboard | Shared patient session |
| Medical Report | Exact-strain clinical and blood evidence |
| Centrifuge | Physical sample separation |
| Incubator | Culture generation and cloning |
| Microscope | Controlled biological identification |
| Gene Imprint | Directed target |
| CRISPR Notes | Reusable program template |
| Vaccine Maker | Quality evaluation and synthesis |
| Mutations | Evolving behavior, resistance, and combinations |
| Strain Catalogue | Shared identity and moderated naming |
| Immunity | Temporary exact-strain reward |

## Design guardrails

- Do not expose raw internal IDs as the primary player answer.
- Do not let a generic report satisfy exact-strain evidence.
- Do not clear source notes merely because they were copied.
- Do not let page switching create separate hidden inventories.
- Do not make every full-strain treatment guaranteed.
- Make failure understandable while leaving enough uncertainty to require research.

## Related pages

- [[CRISPR and Vaccine Maker]]
- [[Vaccines and Immunity]]
- [[Mutations]]
- [[Strain Catalogue]]

