# Infection Strength

#BioForge #BioForge_V0_54T #Symptom #ClinicalParameter #number #PlayerGuide #ModpackGuide #AddonDevelopment

> Definition ID: `bioforge:infection_strength`. Value type: `float`.

## Meaning

Host burden from 0 to 10000; it affects symptoms and treatment difficulty.

## Measurement

Primary instrument/workflow: **Microscope / Vaccine Maker**. A Clipboard assigned to the same patient records compatible readings and can print them into an exact-subject Medical Report.

## Values

- Default: `0.5`.
- Range: 0 to 10000.
- The Vaccine Maker correction page uses meaningful enum labels, True/False for booleans, 0–100 for percentages, and direct entry for large numeric channels.

## Treatment and configuration

- A directed Symptom Vaccine may add/remove/correct this channel when the target action supports it.
- A Symptom Suppressant Tablet can temporarily disable an identified penalty without curing the infection.
- Packs may tune/replace the definition and register Java behavior, but saved IDs must remain stable.

Related: [[Symptom System]], [[Symptom Vaccine]], [[Vaccine Correction Matrix]].

