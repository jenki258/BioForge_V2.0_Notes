#Tools
The Clipboard is a data‑logging tool that records diagnostic findings from other BioForge instruments (Thermometer, Stethoscope, Pulse Oximeter, Otoscope, Reflex Hammer, Blood Reagents). The Medical Report is a printable summary of all recorded data for a patient.

### How to use the Clipboard

| Action                                                | Result                                                                       |
| ----------------------------------------------------- | ---------------------------------------------------------------------------- |
| Right‑click on a living entity                        | Assigns that entity as the current patient. Clears previous data.            |
| Right‑click on air (no target)                        | Assigns yourself as the patient.                                             |
| Right‑click while holding Paper in the other hand     | Prints a Medical Report containing all recorded findings. Paper is consumed. |
| Shift + Right‑click                                   | Clears the clipboard (resets patient and all stored data).                   |
| Right‑click on a clipboard that already contains data | Reactivates the session - resumes working with that stored patient.          |

- The clipboard stores data per patient, identified by name and UUID.
- Data is automatically recorded when you use diagnostic tools on the assigned patient (temperature, heart/lung sounds, oxygen, visual symptoms, reflexes, blood type).
- All stored data is obfuscated (NBT is not human‑readable via `/data` command).

### What data it records

| Category          | Entries                                                                                                 |
| ----------------- | ------------------------------------------------------------------------------------------------------- |
| Vital Signs       | Temperature (°C with fever/hypothermia status), Heart Rate (Normal/Tachy/Brady), SpO₂ + Perfusion Index |
| Respiratory       | Lung Sounds (Normal/Crackle)                                                                            |
| Neurological      | Reflex Delay, Reflex Strength (High/Moderate/Low/None)                                                  |
| Visual Inspection | Redness, Lesions, Secretion, Swelling (High/Moderate/Low/None)                                          |
| Blood Analysis    | Blood Type (A+/A-/B+/B-/AB+/AB-/O+/O- or Animal) and individual Anti‑A, Anti‑B, Anti‑D results          |

- Unstable readings (e.g., due to movement) are marked with “(?)” in tooltips.

### [[Medical Report]] item

- Created by holding Paper in off‑hand and right‑clicking the Clipboard.
- The Paper is consumed; you receive a Medical Report item.

### Visual & text feedback

- **Clipboard tooltip** - Shows patient name, then each section (Vital, Respiratory, Neurological, Visual, Blood). Missing data appears as “-No data-”. Incomplete blood tests show “Incomplete - test all reagents”.
- **Message feedback** - “Now inspecting: Patient”, “Clipboard cleared”, “X observations recorded”.