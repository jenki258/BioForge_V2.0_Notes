#Tools
The Pulse Oximeter measures blood oxygen saturation (SpO₂) and perfusion index (PI) of a player or mob. These values can be affected by infections or circulatory conditions.

### How to use it

| Action | Result |
|--------|--------|
| Hold right‑click (charge) | Starts measuring. Aim at an entity to target it; aim at nothing (or too far) to measure yourself. |
| Keep holding for ~2 seconds | Initial stabilisation period. After 2.5 seconds, a stable reading appears. |
| Release right‑click | Stops the measurement and closes the overlay. |

- While measuring, the device sends periodic requests to the server (every 20 ticks) to get updated oxygen and perfusion values.
- The displayed values stabilise over ~8 seconds. Movement by you or the target reduces reading quality temporarily.

### What it measures

| Measurement                  | Meaning                                                    | Normal range  |
| ---------------------------- | ---------------------------------------------------------- | ------------- |
| **SpO₂ (Oxygen Saturation)** | Percentage of oxygen‑carrying haemoglobin in blood         | 95%‑100%      |
| **PI (Perfusion Index)**     | Strength of blood flow at the measurement site (0‑1 scale) | 0.7+ (strong) |

- Low SpO₂ (below 95%) appears yellow (90‑94%) or red (below 90%) in the overlay.
- PI affects the waveform amplitude and the pulsing dot size.

### Visual feedback

- **Overlay** - Dark panel near the bottom of the screen.
  - Shows target name (if measuring a mob).
  - Displays “SpO₂” and the current percentage (or “--” while stabilising).
  - Shows a real‑time plethysmograph (waveform) that becomes clearer as stabilisation increases.
  - Shows a pulsing dot with size based on PI; the dot pulses at a rate of ~4 seconds per cycle.
- **Quality indicator** - Movement reduces reading quality, which affects waveform clarity and dot pulsing.
- The overlay hides the vanilla crosshair while active (since you are holding the item).

### Interaction with other systems

- **Clipboard integration** - If you have a patient assigned with the Clipboard, the oximeter automatically records SpO₂ and PI after at least 2.5 seconds of measuring.
- **Tags** - Entities with the `no_pulse_oximeter` or `no_diagnostics` tag cannot be measured (e.g., skeletons, non‑living things).