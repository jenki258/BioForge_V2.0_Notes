#InformationItems
# Blood Slide

The **Blood Slide** is a thin glass slide that permanently stores a blood sample and its associated infection strain.  
It is the primary item used in the **Microscope** to visualise a patient’s symptoms.

---

## Obtaining

1. Fill a **Syringe** or **Needle** with blood (right‑click air to draw from yourself, or left‑click a mob).  
2. Hold the filled tool in your off‑hand and an **empty Blood Slide** in your main hand.  
3. Right‑click – the blood and any infection are transferred to the slide. The tool loses its blood but keeps its contamination memory.  

---

## Properties

- The slide stores:  
  - **Blood type** (e.g. A_POSITIVE, O_NEGATIVE)  
  - **Source name** (the creature the blood came from)  
  - **Subject UUID**  
  - **Infection strain** (if the source had a blood‑borne infection)  
  - **Reagent knowledge** (if you have previously tested this subject with Anti‑A/B/D reagents)  

- The slide has two textures: **empty** (clean glass) and **filled** (red smear). The texture switches automatically when the slide contains blood.

---

## Usage

### Microscope
Place the filled Blood Slide into the **Microscope**. After calibrating (if required), the microscope will display symptoms such as heart rate, temperature, and infection strength, based on the strain stored on the slide.

### Viewing Data
Hover over the slide in your inventory to see:  
- Source name  
- Blood type  
- Reagent results (Anti‑A, Anti‑B, Anti‑D) if previously tested  

---

## Notes

- Once a sample is on a slide, it **cannot be removed**. The slide is a permanent record.  
- The slide can be infected if the original blood donor had a **Blood‑borne** (BLOOD) infection type.  
- Slides are accepted by the **Microscope** because they are listed in `data/bioforge/microscope/symptoms.json`.

---
## Comparison: Slide vs. Pellet vs. Plasma

| Property | Blood Slide | Cell Pellet | Plasma Sample |
|----------|-------------|-------------|---------------|
| **How to obtain** | Syringe/Needle + slide | Centrifuge (blood tube) | Centrifuge (blood tube) |
| **Infection data** | Yes | Yes | Yes |
| **Microscope symptoms** | Heart rate, temp, infection strength | Infection strength, reflex delay | Infection strength, oxygen saturation |
| **Calibration required** | 4 sliders | 5 sliders | 2 sliders |
| **Reusable** | Permanent record | Consumed when read? No, stays | Same as Cell Pellet |
