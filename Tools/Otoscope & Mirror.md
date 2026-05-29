#Tools
The Otoscope is a visual diagnostic tool that examines a living entity for surface abnormalities like redness, lesions, secretion, and swelling. The Mirror allows you to use the Otoscope on yourself.

### How to use it

| Action | Result |
|--------|--------|
| Hold right‑click with Otoscope in main hand | Starts examining the entity you are looking at. |
| Hold right‑click with Mirror in off‑hand + Otoscope in main hand | Starts examining yourself instead of a target. |
| Keep holding for ~3 seconds | After a short delay, the otoscope activates and locks your view. |
| Move the selector (WASD / arrow keys) | Moves a crosshair over the examination area. |
| Hover over glowing particles | Tooltip shows the symptom type (Redness, Lesion, Secretion, Swelling). |
| Release right‑click | Stops the examination and closes the overlay. |

- Requires at least 60 ticks (3 seconds) of holding before the overlay appears.
- The Mirror has no function on its own - only as an off‑hand companion to the Otoscope for self‑examination.

### What it measures (visual symptoms)

| Finding       | What it indicates           |
| ------------- | --------------------------- |
| **Redness**   | Inflammation or infection   |
| **Lesions**   | Tissue damage or ulceration |
| **Secretion** | Discharge or exudate        |
| **Swelling**  | Oedema or mass effect       |

Each symptom has a severity value (0‑1) read from the target’s `InfectionData` (symptoms: `OTOSCOPE_REDNESS`, `OTOSCOPE_LESIONS`, `OTOSCOPE_SECRETION`, `OTOSCOPE_SWELLING`).

### Visual feedback

- **Overlay** - The screen is darkened except for a circular viewing area (like a scope).
- **Particles** - Floating icons (redness, lesion, secretion, swelling) appear inside the circle. Their number and size reflect severity.
- **Particle motion** - Each particle moves organically (orbiting, bouncing, drifting) to feel alive.
- **Selector crosshair** - Use WASD/arrows to move a cyan crosshair over particles. Hovering shows a tooltip naming the symptom.
- **Name label** - Displays the target’s name above the scope.
- **Tutorial panel** - Bottom‑right corner shows basic controls (move, select, exit).
- **Ring & vignette** - A glowing scope ring pulses, and a reddish tint may overlay the view if redness is high.

### Interaction with other systems

- **Clipboard integration** - If you have a patient assigned with the Clipboard, the otoscope automatically records all four visual findings after the overlay appears.
- **Tags** - Entities with the `no_otoscope` or `no_diagnostics` tag cannot be examined (e.g., skeletons, non‑living things).