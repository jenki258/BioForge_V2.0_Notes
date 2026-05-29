#Tools
The Stethoscope listens to a player's or mob's heart rate and lung sounds. These are symptoms from infections (e.g., tachycardia, bradycardia, crackles).

### How to use it

| Action | Result |
|--------|--------|
| Hold right-click (charge) | Starts listening to the entity you are looking at (or yourself if no target). |
| Keep holding for ~5 seconds | After a short delay, the overlay shows live heart/lung waveforms and a diagnosis. |
| Release right-click | Stops listening and closes the overlay. |

- While listening, the stethoscope sends periodic requests to the server (every 40 ticks) to get updated vitals.
- It requires at least 20 ticks (1 second) of listening before it starts showing data.
- You can listen to a mob by aiming at it, or listen to yourself by looking away from any entity.

### What it measures

| Measurement | Possible values | Indication |
|-------------|----------------|-------------|
| **Heart rate** | NORMAL, TACHY (fast), BRADY (slow) | Tachycardia / bradycardia from infection |
| **Lung sounds** | NORMAL, CRACKLE | Crackles suggest respiratory infection |

The values come from the target's `InfectionData` symptoms.

### Visual & audio feedback

- **Overlay** - A dark panel appears near the hotbar.
  - First ~2.5 seconds: scanning lines animation ("Listening..." with dots).
  - After 5 seconds: waveforms appear (heart on left, lungs on right) with a reveal effect.
  - Labels show the diagnosed condition (e.g., "Tachycardia", "Crackles") and the target name.
- **Sounds** - Looping heartbeat and lung sounds play while listening (normal/fast/slow heart; normal/crackle lungs).
- The sounds stop immediately when you release right-click.

### Interaction with other systems

- **Clipboard integration** - If you have a patient assigned with the Clipboard, the stethoscope automatically records heart rate and lung sounds after at least 5 seconds of listening.
- **Tags** - Entities with the `no_stethoscope` or `no_diagnostics` tag cannot be examined (e.g., skeletons, non-living things).
