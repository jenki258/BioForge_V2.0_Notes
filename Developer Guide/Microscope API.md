# Microscope API

#BioForge #BioForge_V0_54T #JavaAPI #JSONAPI #Microscope #AddonDevelopment

Microscope mappings assign sample/input items to displayed symptom/pathogen evidence, textures/icons, calibration targets, visibility rules, and research outputs.

The machine saves knob positions when the GUI closes; each assay/sample receives deterministic target positions on first insertion. Scanning requires calibration and can write Gene Imprints or combined vaccine-assay results.

JSON covers normal mappings; Java addons register custom sample/research behavior when existing fields are insufficient. Do not reveal hidden full-strain data in a client tooltip merely because the server stores it.
