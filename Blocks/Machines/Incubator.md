#Blocks 
[[Live Culture Vial]]
[[Nutrient Medium]]
[[Catalyst Vial]]
[[Virus Sample]]

The **Incubator** is a laboratory block that allows players to grow and duplicate virus samples.  
It uses a brewing‑stand‑style interface with one top slot and three bottom slots, turning raw materials into infection‑carrying items.

---

## How to Use

1. **Place** the Incubator in the world.  
2. Right‑click it to open the GUI.  
3. Place a valid **catalyst** or **virus sample** in the **top slot**.  
4. Place one or more **consumable** items (Nutrient Medium or empty Live Culture Vials) in the **bottom three slots**.  
5. The **progress bar** (vertical, filling from top to bottom) will begin to fill.  
6. When the bar is full, all bottom slots are processed at once, consuming one charge or item from the top slot.

You can use **shift+click** to quickly move items between your inventory and the incubator.

---

## Processing Modes

The incubator automatically detects what you have placed in the top slot and chooses the appropriate mode.

| Mode | Top Slot | Bottom Slots | Output | Consumption |
|------|----------|--------------|--------|-------------|
| **Catalyst** | Catalyst Vial (set with a pathogen, has charges) | Nutrient Medium | Virus Samples (random strain for that pathogen) | 1 charge from vial, 1 nutrient per slot |
| **Culture** | Virus Sample (contains a strain) | Empty Live Culture Vials | Filled Live Culture Vials (exact same strain) | Virus sample consumed, vials filled |
| **Blood Duplication** | Any blood item that carries an infection (Syringe, Needle, Tube, Bone Marrow, etc.) | Empty Live Culture Vials | Filled Live Culture Vials (exact strain from the blood) | Blood item consumed, vials filled |

- **All bottom slots** are processed **simultaneously** each time the progress bar completes.  
- If the top item is a Catalyst Vial with `"RANDOM"`, the pathogen is randomly selected from all available mappings **per batch**.  
- If the top item is a blood sample, the infection must be a true infection strain (containing semicolon‑separated symptoms) – plain blood data will not start the process.

---

## Blood Duplication

If you already have a blood sample that carries an infection (e.g. bone marrow, blood tube), you can place it directly in the top slot of the Incubator along with empty Live Culture Vials in the bottom slots.

This will **duplicate the exact infection strain** from the blood sample into all the vials, consuming the original blood item.