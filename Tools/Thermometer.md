#Tools
The Thermometer measures the body temperature of players and mobs. It detects fever (high temp) or hypothermia (low temp), which are symptoms of infections in the mod.

### How to use it

| Action                              | Result                                             |
| ----------------------------------- | -------------------------------------------------- |
| **Left‑click (empty air or block)** | *Shakes* the thermometer - makes it ready for use. |
| **Right‑click on air**              | Measures your own temperature.                     |
| **Shift + Right‑click on a mob**    | Measures that mob’s temperature.                   |

- After each measurement, the thermometer enters a **3‑second cooldown** and becomes *unready* (needs shaking again).
- You can see the last reading in the item’s tooltip, displayed in **°C, °F, and K**.

### Temperature logic

- **Normal**: ~36.6 °C → tooltip shows green text.
- **High fever** (≥38.5 °C) → red text → indicates `TEMPERATURE_PLUS` symptom.
- **Low temp** (≤35.5 °C) → blue/cyan text → indicates `TEMPERATURE_MINUS` symptom.

These temperature extremes come from the target’s `InfectionData` (symptoms like fever or chills).

### Cooldown & internal NBT

- The thermometer stores the last reading, target name.
- After use, it enters a **3000 ms cooldown**.
- You must **shake it again** before taking a new reading.

### Interaction with other systems

- **Clipboard integration** - If you have a patient assigned with the Clipboard, the temperature is automatically recorded.
- **Tags** - Entities with the `no_thermometer` or `no_diagnostics` tag cannot be measured (e.g., skeletons, armour stands, non‑living things).

### Visual feedback (lang keys)

- `item.bioforge.thermometer.status_ready` - “✔ Ready to use”
- `item.bioforge.thermometer.status_used` - “✘ Needs shaking”
- Tooltip explains: shake, use on self, use on mob (shift+right‑click).
