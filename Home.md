# BioForge V0.54T Wiki

#BioForge #BioForge_V0_54T #Wiki #PlayerGuide #ModpackGuide #AddonDevelopment

> Documentation status: current for the V0.54T test build. This wiki separates player-facing knowledge from configuration and implementation details while keeping them connected through links.

BioForge is a biomedical progression mod built around examination, blood handling, infection research, cultivation, microscopy, CRISPR programming, pharmaceutical production, vaccination, containment, and extensibility. It can be played as a laboratory progression mod, configured as a modpack disease framework, or extended as a Java/JSON platform.

## Choose your route

- [[Player Guide]] — survival progression, equipment, laboratory workflows, protection, and treatment.
- [[Item Catalogue]] — one page for every registered item.
- [[Block and Machine Catalogue]] — one page for every block and workstation.
- [[Mechanics Index]] — every gameplay system and the connections between them.
- [[Mutation Catalogue]] — all bundled mutation definitions and their interactions.
- [[Symptom Catalogue]] — all editable clinical parameters and their consequences.
- [[Transmission Catalogue]] — every route by which infection can spread.
- [[Modpack Maker Guide]] — server configuration, tags, datapacks, balance, and compatibility.
- [[Addon Developer Guide]] — public Java API, JSON schemas, reload behavior, and validation.
- [[Command Catalogue]] — administration, testing, research, infection, and development commands.

## The core gameplay loop

1. Detect illness through symptoms, tools, reports, scanners, and environmental evidence.
2. Collect blood or environmental samples without contaminating the laboratory.
3. Separate, cultivate, and inspect samples in the Centrifuge, Incubator, and Microscope.
4. Record strain evidence and assemble a CRISPR program in the Vaccine Maker.
5. Produce a vaccine, directed treatment, resistance pill, or symptom suppressant.
6. Test treatment quality through a vaccinated-blood assay rather than receiving perfect information for free.
7. Protect personnel, clean contaminated rooms, and monitor entrances while the infection continues to adapt.

## Documentation conventions

- Every content page names its registry or data ID.
- `#PlayerGuide` marks survival-facing instructions.
- `#ModpackGuide` marks configurable or balance-sensitive behavior.
- `#AddonDevelopment` marks JSON or Java extension points.
- Exact recipes remain visible in JEI and the in-game Research Tablet; wiki pages explain their purpose, station, and dependency chain.
- Values described as defaults may be changed by server configuration or datapacks.

## Version note

V0.54T is a test build. Stored biological data uses stable IDs and obfuscated NBT, but worlds should still be backed up before replacing definitions or changing addon namespaces.
