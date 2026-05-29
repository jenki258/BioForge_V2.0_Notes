#Tools 
The Medical Report is a printable document that contains all diagnostic data recorded for a patient using the Clipboard. It serves as a permanent record of a patient’s vital signs, respiratory status, neurological reflexes, visual symptoms, and blood type.

### How to obtain it

- Hold a **Clipboard** with a patient assigned (and data recorded) in one hand.
- Hold **Paper** in the other hand.
- Right‑click with the Clipboard - the Paper is consumed and you receive a **Medical Report** item.
- The Clipboard is cleared (ready for a new patient) after printing.

### What the report shows

The report’s tooltip displays the same sections as the Clipboard:

| Section | Content |
|---------|---------|
| **Vital Signs** | Temperature (°C with fever/hypothermia/normal status), Heart Rate (Normal/Tachy/Brady), SpO₂ (%) and Perfusion Index (Strong/Moderate/Weak) |
| **Respiratory** | Lung Sounds (Normal/Crackle) |
| **Neurological** | Reflex Delay and Strength (High/Moderate/Low/None) |
| **Visual Inspection** | Redness, Lesions, Secretion, Swelling (High/Moderate/Low/None) |
| **Blood Analysis** | Blood Type (e.g., A+) and individual Anti‑A, Anti‑B, Anti‑D results (+ or -) |

- If a measurement was never taken, the report shows “- No data -”.
- Incomplete blood tests show “Incomplete - test all reagents”.
- Unstable readings (from movement, etc.) are marked with “(?)”.

### Visual & storage details

- The report’s tooltip is the only way to read it - there is no interactive GUI.
- All patient data is **obfuscated** in NBT using `NbtObfuscator`, so it cannot be read with `/data` or other mods.
- The report stacks to 1 and cannot be copied or edited.