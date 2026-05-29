#Tools
The Swab collects a sample of infection data from a living entity *or* from certain infected blocks. It stores the full pathogen profile (pathogen type, transmission types, symptom values). This sample can then be used to inoculate a Petri dish or Contaminated Substrate.

### How to use it

| Action | Result |
|--------|--------|
| Right‑click on a living entity (mob or player) | Takes a sample from that entity. Swab becomes contaminated. |
| Right‑click on air (no target) | Takes a sample from yourself (requires you to be infected). |
| Right‑click on an **infected block** (see list below) | Takes a sample from that block. Swab becomes contaminated. |

- The swab starts clean and can only be used once - after contamination it cannot take another sample.
- The target (entity or block) must contain a valid infection strain. If not, you get a message (e.g., “Target not infected” or nothing happens).

### Which blocks can be swabbed

From the code, these blocks are swabbable (they call `SwabItem` interaction and store strain data):

| Block | What you get |
|-------|---------------|
| **Microbial Mat** | Sample of the mat's fungal/bacterial colony |
| **Infested Block** | Sample of the underground infestation |
| **Sporocarp** | Sample of the fruiting body (fungal) |
| **Colony Core** | Sample of the main colony strain |
| **Infected crop** (any block tagged `infectable_crops`) | Sample of the crop infection (via right‑click, not break) |

- For crops, you right‑click the crop block while holding a clean swab. If the crop is infected, the swab becomes contaminated.
- For the other blocks, right‑click them directly with the swab.

### What data it stores

When you take a sample, the swab’s NBT captures the entire infection state:

- Pathogen type (VIRUS, BACTERIA, FUNGI, PARASITE, PRION)
- Transmission types (AIRBORNE, FOODBORNE, CONTACT_BASED, etc.)
- All symptom values (heart rate, lung sounds, temperature, visual findings, reflexes, oxygen, perfusion, infection strength, colony radius, max infested blocks)

Data is obfuscated using `NbtObfuscator` - cannot be read with `/data` commands.

### Interaction with other systems

- **Petri Dish** - Right‑click a clean Petri dish while holding a contaminated swab in off‑hand to inoculate the dish.
- **Contaminated Substrate** - Use contaminated swab on a clean substrate item to inoculate it, then place it to start an underground colony.

### Visual & text feedback

- **Tooltip** - Clean: “Clean swab” + usage hint. Contaminated: “Contains a sample”.
- **Messages** -  
  - “Sample collected from entity”  
  - “Sample collected from yourself”  
  - “Swab contaminated with microbial mat strain.”  
  - “Swab contaminated with sporocarp strain.”  
  - “Swab contaminated with colony core strain.”  
  - “Swab contaminated with infected crop strain.”