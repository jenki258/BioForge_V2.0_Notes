# Symptom Catalogue

#BioForge #BioForge_V0_54T #Symptom #Catalogue #Diagnosis #ModpackGuide #AddonDevelopment

V0.54T contains **17 typed built-in clinical parameters**. Mutation-defined coughing, sneezing, diet restrictions, and potion-like penalties are documented as mutations because they are not entries in this typed symptom registry.

| Parameter | ID | Type | Default | Allowed/range |
|---|---|---|---|---|
| [[Heart Rate]] | `bioforge:heart_rate` | enum | `NORMAL` | NORMAL, TACHY, BRADY |
| [[Lung Sound]] | `bioforge:lung_sound` | enum | `NORMAL` | NORMAL, CRACKLE |
| [[High Temperature]] | `bioforge:temperature_plus` | boolean | `false` | undefined–undefined |
| [[Low Temperature]] | `bioforge:temperature_minus` | boolean | `false` | undefined–undefined |
| [[Tissue Redness]] | `bioforge:otoscope_redness` | float | `0` | 0–1 |
| [[Tissue Lesions]] | `bioforge:otoscope_lesions` | float | `0` | 0–1 |
| [[Tissue Secretion]] | `bioforge:otoscope_secretion` | float | `0` | 0–1 |
| [[Tissue Swelling]] | `bioforge:otoscope_swelling` | float | `0` | 0–1 |
| [[Reflex Delay]] | `bioforge:reflex_delay` | float | `0` | 0–10000 |
| [[Reflex Strength]] | `bioforge:reflex_strength` | float | `0.5` | 0–1 |
| [[Neural Damage]] | `bioforge:neural_damage` | float | `0` | 0–1 |
| [[Oxygen Saturation]] | `bioforge:oxygen_saturation` | float | `0.95` | 0–1 |
| [[Perfusion Index]] | `bioforge:perfusion_index` | float | `0.7` | 0–1 |
| [[Infection Strength]] | `bioforge:infection_strength` | float | `0.5` | 0–10000 |
| [[Colony Radius]] | `bioforge:colony_radius` | float | `20` | 0–10000 |
| [[Infestation Capacity]] | `bioforge:max_infested_blocks` | float | `100` | 0–10000 |
| [[Microscope Visibility]] | `bioforge:microscope_visibility` | enum | `NONE` | NONE, VERY_LOW, LOW, MEDIUM, HIGH, EXTREME |

See [[Symptom System]], [[Diagnosis and Medical Records]], and [[Definition API]].
