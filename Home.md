# BioForge V2.0 Wiki

#BioForge #BioForge_V2_0 #Build_V0_54T #Wiki #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation snapshot: BioForge V2.0, test build V0.54T. Gameplay values described here are defaults and may be changed by server configuration or datapacks.

BioForge is a biomedical progression mod for Minecraft 1.20.1 Forge. Its central loop joins field diagnosis, blood handling, infection research, cultivation, microscopy, CRISPR programming, pharmaceutical production, vaccination, containment, and environmental cleanup. The same systems are exposed to modpack authors through JSON and to addon developers through Java APIs.

## Start here

- [[Getting Started]] — installation, first equipment, and the shortest route into the laboratory.
- [[Player Guide]] — the complete survival progression and connected gameplay loop.
- [[Contents]] — the maintained map of this wiki.
- [[FAQ]] and [[Glossary]] — quick answers and consistent terminology.
- [[Compatibility and Requirements]] — supported runtime, optional integrations, and multiplayer expectations.

## Complete catalogues

- [[Item Catalogue]] — every registered item family, with one page per content item.
- [[Block and Machine Catalogue]] — laboratory machines, scanners, containment, and environmental biology.
- [[Mechanics Index]] — every gameplay system and the links between them.
- [[Mutation Catalogue]] — all 81 bundled mutation definitions and their interactions.
- [[Symptom Catalogue]] — all 17 typed clinical parameters and their consequences.
- [[Transmission Catalogue]] — all eight executable transmission routes.
- [[Command Catalogue]] — administration, validation, testing, research, and infection commands.

## Configuration and extension

- [[Modpack Maker Guide]] — server configuration, datapacks, tags, balance, and compatibility.
- [[Addon Developer Guide]] — supported JSON and Java extension surfaces.
- [[BioForge addon creation guide]] — the exhaustive, copy-ready addon tutorial.
- [[Localization and Translation]] — language-file rules and the current localization boundary.
- [[Release Checklist]] — the remaining verification and polish required before a public release.

## The connected gameplay loop

1. Detect illness through symptoms, field tools, medical records, scanners, and environmental evidence.
2. Collect blood or environmental samples while preventing cross-contamination.
3. Separate, cultivate, and inspect samples in the Centrifuge, Incubator, and Microscope.
4. Record strain evidence, prepare 15 CRISPR cartridges, and select a compatible Cas/PAM module.
5. Reconstruct the observed strain in the Vaccine Maker correction matrix.
6. Produce a full-strain vaccine, directed treatment, resistance pill, or symptom suppressant.
7. Test uncertain treatment quality through a vaccinated-blood assay rather than receiving perfect information for free.
8. Protect personnel, clean contaminated rooms, and monitor entrances while the infection incubates and adapts.

## Verified content snapshot

The bundled V0.54T data contains 106 registered item IDs, 21 block IDs, 81 mutation definitions, six pathogen classes, 17 symptom definitions, eight transmission definitions, 21 advancements, and 35 Research Tablet data files. JEI is optional but strongly recommended; the in-game Research Tablet provides progression-aware recipes and explanations.

## Knowledge and safety

BioForge deliberately hides some biological detail until the player performs the correct research. A Live Culture Vial, Virus Sample, vaccine, or unknown Gene Imprint should not reveal the complete strain by tooltip alone. Stored biological data uses stable IDs and obfuscated NBT, but worlds should still be backed up before replacing definitions, changing addon namespaces, or installing a new test build.

