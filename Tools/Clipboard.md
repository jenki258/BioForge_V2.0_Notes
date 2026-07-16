#Tools 

The **Clipboard** is a data‑logging tool that records diagnostic findings from other BioForge instruments (Thermometer, Stethoscope, Pulse Oximeter, Otoscope, Reflex Hammer, Blood Reagents).  
The **Medical Report** is a printable summary of all recorded data for a patient.  
A **Writable Book** can also be used to append the findings directly into a book for note‑keeping.


---

## How to Use the Clipboard

| Action | Result |
|--------|--------|
| **Right‑click on a living entity** | Assigns that entity as the current patient. Clears any previous session data. |
| **Right‑click on air (no target)** | Assigns yourself as the patient. |
| **Right‑click while holding Paper in the other hand** | Prints a **Medical Report** containing all recorded findings. The Paper is consumed. |
| **Right‑click while holding a Writable Book in the other hand** | Appends a plain‑text summary of the recorded findings to the book (one page). The clipboard is cleared afterward. |
| **Shift + Right‑click** | Clears the clipboard (resets patient and all stored data). |
| **Right‑click on a clipboard that already contains data** | Reactivates the session – resumes working with that stored patient. |

- The clipboard stores data per patient, identified by name and UUID.  
- Data is automatically recorded when you use diagnostic tools on the assigned patient (temperature, heart/lung sounds, oxygen, visual symptoms, reflexes, blood type).  
- All stored data is obfuscated (NBT is not human‑readable via `/data` command).

---

## What Data It Records

| Category | Entries |
|----------|---------|
| **Vital Signs** | Temperature (°C with fever/hypothermia status), Heart Rate (Normal/Tachy/Brady), SpO₂ + Perfusion Index |
| **Respiratory** | Lung Sounds (Normal/Crackle) |
| **Neurological** | Reflex Delay, Reflex Strength (High/Moderate/Low/None) |
| **Visual Inspection** | Redness, Lesions, Secretion, Swelling (High/Moderate/Low/None) |
| **Blood Analysis** | Blood Type (A+/A‑/B+/B‑/AB+/AB‑/O+/O‑ or Animal) and individual Anti‑A, Anti‑B, Anti‑D results |

- Unstable readings (e.g., due to movement) are marked with “(?)” in tooltips.  
- A “?” indicates the measurement was taken under unstable conditions (e.g., player moving).  
- Blood analysis is incomplete until all three reagents (Anti‑A, Anti‑B, Anti‑D) have been used on the same patient.

---

## Integration with Diagnostic Tools

When you use any of the following tools while the patient is assigned (via the clipboard), the reading is automatically recorded onto the clipboard:

- **Thermometer** – records temperature (fever/normal/hypothermia).  
- **Stethoscope** – records heart rate and lung sounds.  
- **Pulse Oximeter** – records oxygen saturation and perfusion index.  
- **Otoscope** – records visual inspection data (redness, lesions, secretion, swelling).  
- **Reflex Hammer** – records reflex delay and strength.  
- **Reagent Vials** (Anti‑A, Anti‑B, Anti‑D) – records blood type and individual reactions.

You do **not** need to manually write anything; simply use the tool on the assigned patient (or self) and the data appears on the clipboard.

---

## [[Medical Report]] Item

- Created by holding **Paper** in your off‑hand and right‑clicking the Clipboard.  
- The Paper is consumed; you receive a **Medical Report** item.  
- The report contains the same patient data as the clipboard, displayed in sections when you hover over it.  
- The report is a permanent item that can be stored, traded, or displayed.

---

## Appending to a Writable Book

If you hold a **Writable Book** in your off‑hand and right‑click the Clipboard, a plain‑text summary of all recorded findings is **appended** to the book (as a new page).  
The text is localised according to your game language and contains the same information as the Medical Report tooltip.  
The clipboard is cleared after the operation.

---

## Visual & Text Feedback

### Clipboard Tooltip
- Shows the **patient name** at the top.  
- Lists each diagnostic section with the recorded value; missing data shows **“‑‑ No data ‑‑”**.  
- Incomplete blood tests display **“Incomplete – test all reagents”**.  
- At the bottom, hints remind you how to resume, print, append to a book, or clear.

### Chat Messages
- “Now inspecting: *PatientName*” – when a patient is assigned.  
- “Clipboard cleared” – when you shift+right‑click.  
- When you print or append to a book, the operation happens silently (no additional chat message; the items are created).

---

## Session Persistence

- Each clipboard stores a unique **Session ID** (UUID) in its NBT.  
- When you right‑click a clipboard that already contains patient data, the session is **reactivated** – you continue where you left off with that same patient.  
- This allows you to put the clipboard away and pick it up later without losing any recorded data.

---

## Technical Notes (for developers)

- `ClipboardItem` handles the right‑click logic (assign patient, clear, print, append to book).  
- `ClipboardHelper` contains static methods for assigning subjects, reactivating sessions, recording findings, and clearing.  
- `ClipboardCreateReportHelper` creates a Medical Report item by reading the encrypted clipboard data and writing it to a new item stack.  
- `ClipboardAppendToBookHelper` reads the clipboard data and appends it as a plain‑text page into a Writable Book.  
- All recorded data is stored in the clipboard’s NBT under an encrypted string (using `NbtObfuscator`).  
- The session token (`SessionId`) is stored in plain UUID format for quick identification without decrypting the main payload.
