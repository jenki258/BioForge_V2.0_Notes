#Tools
The Reflex Hammer tests the neurological reflexes of a player or mob. It measures reflex delay, reflex strength, and neural damage - symptoms that can be affected by infections or other conditions.

### How to use it

| Action                            | Result                                                                                                                                 |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Hold right‑click                  | Starts the reflex test. Aiming at a living entity tests that mob; aiming at nothing (or too far) tests yourself.                       |
| Watch the slider                  | A bar appears with a moving slider and a coloured “hit zone” (cyan). You must press the strike key when the slider is inside the zone. |
| Press strike key (default: C key) | Attempts to hit the target. Accuracy depends on how close the slider was to the hit zone.                                              |
| Get 5 perfect strikes in a row    | A summary panel appears showing the diagnosis (delay, strength, neural damage).                                                        |

- The hit zone position changes randomly each time you reset (after a strike or a miss).
- If you miss the zone or let the slider reach the end, the counter resets to zero.
- A missed strike causes the screen to shake briefly.

### What it measures

| Measurement | Meaning | In‑game intensity levels |
|-------------|---------|--------------------------|
| **Reflex delay** | How long it takes for the reflex to fire | High / Moderate / Low / None |
| **Reflex strength** | How strong the reflex reaction is | High / Moderate / Low / None |
| **Neural damage** | Indicator of neurological impairment | High / Moderate / Low / None |

These values come from the target’s `InfectionData` (symptoms: `REFLEX_DELAY`, `REFLEX_STRENGTH`, `NEURAL_DAMAGE`).

### Visual & audio feedback

- **Overlay** - A dark panel with a slider bar, hit zone, target name, success counter (x/5), and a prompt showing the strike key.
- **Screen shake** - Briefly shakes the panel when you miss.
- **Particles & sounds** - On a successful strike, the target emits cloud particles; a “strong” hit lifts the target slightly and plays a strong attack sound; a weak hit plays a weak sound and gives a small upward nudge.
- **Summary panel** - After 5 perfect strikes, a panel appears for ~6 seconds displaying the three measured values as text (e.g., “Reflex Delay: High”).

### Interaction with other systems

- **Clipboard integration** - If you have a patient assigned with the Clipboard, the reflex results (delay and strength as text levels) are automatically recorded after the 5‑strike sequence.
- **Tags** - Entities with the `no_reflex_hammer` or `no_diagnostics` tag cannot be tested (e.g., skeletons, non‑living things).