#Blood

Reagents are chemical vials used to determine the blood type of a blood sample. There are three reagents: **Anti‑A**, **Anti‑B**, and **Anti‑D (Rh)**. Each reacts with specific antigens present in human blood. Animal blood gives a distinct yellow reaction.

## Reagent Types

| Reagent | Detects                    | Positive reaction means                                      |
|---------|----------------------------|--------------------------------------------------------------|
| Anti‑A  | Antigen A                  | Blood type contains A (A+, A-, AB+, AB-)                     |
| Anti‑B  | Antigen B                  | Blood type contains B (B+, B-, AB+, AB-)                     |
| Anti‑D  | Rh factor (D antigen)      | Blood type is positive (A+, B+, AB+, O+)                     |

## How to Use

1. Obtain a **blood sample** from an entity using a Needle (filled), Bone Marrow, or Withered Bone Marrow.
2. Hold the **Reagent vial** in your main hand.
3. Hold the **blood sample item** in your **off‑hand**.
4. Right‑click (use the reagent vial).
5. The reagent vial will change colour and show a tooltip indicating the result.

## Reaction Results

| Sample type               | Vial colour          | Tooltip                                 |
| ------------------------- | -------------------- | --------------------------------------- |
| Animal blood              | Yellow (`#FCF74B`)   | “Non‑human blood sample”                |
| Human blood - positive    | Dark red (`#91160D`) | “⨁ Reaction detected”                   |
| Human blood - negative    | Pale red (`#F5A7A2`) | “⊖ No reaction”                         |
| Unused vial (no test yet) | Beige (`#D4C19F`)    | Description of what the reagent detects |

> The vial becomes **used** after testing and cannot be reused. It stacks to 64 when unused, but becomes a single used vial.

## Saving Results (Blood Knowledge)

- When you test a blood sample with a reagent, the result (positive or negative) is saved to your **personal blood knowledge database**.
- The knowledge is stored per player, per subject (the entity whose blood was tested).
- Once you have tested all three reagents on blood from the same subject, the **blood type** is revealed and will appear on future needles or bone marrow items from that subject.

## Using with Clipboard

- If you currently have a patient assigned to your Clipboard, and the blood sample belongs to that patient, the reagent result is automatically recorded in the Clipboard’s blood analysis section.
- Once all three reagents are recorded, the Clipboard will display the patient’s full blood type.

## Example (Testing a Needle)

1. Fill a Needle with blood from a zombie.
2. Hold Anti‑A vial in main hand, Needle in off‑hand.
3. Right‑click. If the vial turns dark red, the blood contains antigen A (so the zombie’s blood type is A+, A-, AB+, or AB-).
4. Repeat with Anti‑B and Anti‑D.
5. After all three tests, the Needle will show the exact blood type in its tooltip (e.g., “Blood type: A+”).

## Tags / Configuration

- None directly. Reagents work with any blood source item (Needle, Bone Marrow, Withered Bone Marrow).