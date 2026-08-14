# Microscope Visibility

#BioForge #BioForge_V0_54T #Symptom #ClinicalParameter #enum #PlayerGuide #ModpackGuide #AddonDevelopment

> Definition ID: `bioforge:microscope_visibility`. Value type: `enum`.

## Meaning

NONE, VERY_LOW, LOW, MEDIUM, HIGH, or EXTREME; it controls diagnostic reagent success.

## Measurement

Primary instrument/workflow: **Microscope**. A Clipboard assigned to the same patient records compatible readings and can print them into an exact-subject Medical Report.

## Values

- Default: `NONE`.
- Allowed values: NONE, VERY_LOW, LOW, MEDIUM, HIGH, EXTREME.
- The Vaccine Maker correction page uses meaningful enum labels, True/False for booleans, 0–100 for percentages, and direct entry for large numeric channels.

## Treatment and configuration

- A directed Symptom Vaccine may add/remove/correct this channel when the target action supports it.
- A Symptom Suppressant Tablet can temporarily disable an identified penalty without curing the infection.
- Packs may tune/replace the definition and register Java behavior, but saved IDs must remain stable.

Related: [[Symptom System]], [[Symptom Vaccine]], [[Vaccine Correction Matrix]].

