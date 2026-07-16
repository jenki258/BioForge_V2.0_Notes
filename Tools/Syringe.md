#Tools 
[[Test Tube]]
# Syringe

The **Syringe** is a reusable medical tool that can draw, store, and inject blood.  
It also carries an **infection memory** – if the syringe becomes contaminated with a blood‑borne disease, it can transmit that infection to any future target.

---

## Obtaining

- Crafted (recipe to be defined; currently available in the Creative inventory).  
- The syringe has **durability in the form of uses** – a fresh syringe can hold up to 4 doses of blood. Once all doses are consumed, the syringe is emptied but not destroyed.

---

## How to Use

The syringe has different actions depending on what you target and whether it is full or empty.  
You can **right‑click air**, **right‑click a mob**, or **left‑click a mob** to perform different tasks.

| Action | Syringe State | Target | Result |
|--------|---------------|--------|--------|
| **Right‑click air** (not looking at a mob) | Empty | Yourself | Draw 10 blood from yourself |
| **Right‑click air** (not looking at a mob) | Filled | Yourself | Inject yourself (+2 blood, apply stored infection) |
| **Right‑click a mob** | Filled | Mob | Inject the mob (+2 blood, apply stored infection) |
| **Left‑click a mob** (attack) | Empty | Mob | Draw 10 blood from the mob and capture its infection (if any) |

- The syringe will **never** self‑inject if you are looking directly at a living entity. This prevents accidentally injecting yourself while trying to inject a mob.  
- Each injection consumes **one use** (one dose). The syringe shows the remaining uses in its tooltip.

---

## Blood Data

When you draw blood, the syringe stores:
- **Blood type** (e.g. `A_POSITIVE`)
- **Source name** (your name or the mob’s name)
- **Subject UUID**
- **Blood amount** (reflected as uses left; each use represents a dose)

You can view this information by hovering over the syringe in your inventory.

---

## Infection Transmission

If the blood donor had a **Blood‑borne infection** (an infection with the `BLOOD` transmission type), the syringe will **capture** that strain and store it as an **infection memory**.  
The strain is stored separately from the blood data, using dedicated obfuscated NBT keys.

- When you inject yourself or a mob with a contaminated syringe, the stored strain is applied to the target.  
- The infection memory **persists** even after the blood is used up. An empty syringe can still transmit the last strain it carried.  
- To remove the infection memory, you must **clean the syringe** with **Ethanol** or **Wipes** (only when the syringe is completely empty of blood).

---

## Tooltips

The syringe’s tooltip changes depending on its state.

### Empty Syringe
- “Empty” (grey text)  
- “Right‑click air to draw your own blood”  
- “Left‑click a mob to collect its blood”  
- “⚠ Drawing blood from a mob with a Blood‑borne infection will contaminate the syringe.”

### Filled Syringe
- “Contains blood” (red text)  
- “Source: \<name>”  
- “Uses left: \<number>” (gold text)  
- If the blood donor has been tested with reagents, the tooltip will show:
  - Blood type (if all three reagents tested)  
  - Anti‑A, Anti‑B, Anti‑D results  

- “Right‑click air to inject yourself”  
- “Right‑click a mob to inject it”  
- Blood contamination warning (same as above)

---

## Cleaning the Syringe

The syringe’s infection memory can be removed using **Ethanol** or **Wipes**.  
Requirements:
- The syringe must be **completely empty of blood** (0 uses left).  
- Hold the cleaning item in your main hand and the empty syringe in your off‑hand, then right‑click.  

This will delete the stored infection strain, making the syringe safe to reuse without risk of cross‑contamination.

---

## Technical Notes

- `SyringeItem` uses `BloodSampleUtil` for blood data storage and `NbtObfuscator.writeInfection()` / `readInfection()` for the infection memory.  
- The `consumeUse()` method decrements the uses count and clears blood data when uses reach 0.  
- A per‑player timestamp map (`lastMobInjectionTick`) prevents a rare double‑consumption bug when both `use` and `interactLivingEntity` fire in the same tick.  
- The `isLookingAtLivingEntity()` check ensures that right‑clicking a mob will never trigger self‑injection.  
- The infection competition logic (`StrainData.compete()`) is applied when loading a new strain into an already‑contaminated syringe via a Live Culture Vial.  