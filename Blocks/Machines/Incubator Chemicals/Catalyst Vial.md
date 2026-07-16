#Incubation
## Creating a Catalyst Vial

A Catalyst Vial is the starting point for growing a completely new virus strain.

1. Obtain an empty **Catalyst Vial**.  
2. Hold it in your main hand, and the desired **reagent** in your off‑hand.  
3. Right‑click – the vial locks onto the corresponding pathogen (e.g. Red Mushroom → FUNGI, Spider Eye → VIRUS).  
4. The vial now shows the pathogen name and the number of charges (default 1).

Using a **Nether Star** as the reagent sets the vial to `"RANDOM"` – the pathogen will be chosen randomly when the incubator runs.

The valid reagent‑to‑pathogen mappings are displayed in the Catalyst Vial’s tooltip when it is empty.

You can also view all possible mappings in the JSON file `data/bioforge/incubator/catalyst_mappings.json`.

## Configuration (for pack makers)

The incubator’s catalyst mappings are defined in `data/bioforge/incubator/catalyst_mappings.json`.  
Example:

```json
{
  "mappings": [
    { "item": "minecraft:red_mushroom", "pathogen": "FUNGI" },
    { "item": "minecraft:brown_mushroom", "pathogen": "FUNGI" },
    { "item": "minecraft:rotten_flesh", "pathogen": "BACTERIA" },
    { "item": "minecraft:spider_eye", "pathogen": "VIRUS" }
  ]
}
```

The random symptom ranges for each pathogen are taken directly from `BioForgeSymptoms` (the `getDefaultRanges()` method), so adding a new symptom to the code automatically makes it appear on virus samples.