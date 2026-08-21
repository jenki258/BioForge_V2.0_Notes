# Heart Rate

#BioForge #BioForge_V2_0 #Build_V0_54T #Symptom #ClinicalParameter #enum #PlayerGuide #ModpackGuide #AddonDevelopment

> Definition ID: `bioforge:heart_rate`. Value type: `enum`.

## Meaning

NORMAL, TACHY, or BRADY; abnormal rates affect exertion and cardiovascular behavior.

## Measurement

Primary instrument/workflow: **Stethoscope**. A Clipboard assigned to the same patient records compatible readings and can print them into an exact-subject Medical Report.

## Values

- Default: `NORMAL`.
- Allowed values: NORMAL, TACHY, BRADY.
- The Vaccine Maker correction page uses meaningful enum labels, True/False for booleans, 0–100 for percentages, and direct entry for large numeric channels.

## Treatment and configuration

- A directed Symptom Vaccine may add/remove/correct this channel when the target action supports it.
- A Symptom Suppressant Tablet can temporarily disable an identified penalty without curing the infection.
- Packs may tune/replace the definition and register Java behavior, but saved IDs must remain stable.

Related: [[Symptom System]], [[Symptom Vaccine]], [[Vaccine Correction Matrix]].

