#Blocks

The Centrifuge is a machine block that processes items according to JSON recipes. It can transform one item into another, optionally copying blood data or specific NBT tags. Each recipe has a processing time, and multiple slots can run simultaneously (8 slots).

## GUI & Interface

When you right‑click the Centrifuge, you see a screen with:

- **8 input/output slots** arranged in a circle around a central animated spinner.
- A **progress indicator** - a ring that fills as the current active recipe progresses. The GUI shows the most advanced progress among all slots (the highest ratio).

The slots are bidirectional: you can place items into any slot, and the Centrifuge will process them independently.

## How It Works

1. Place a **valid input item** into any of the 8 slots.
2. If a recipe exists for that item, the Centrifuge starts processing.
3. The progress bar fills over `processing_time` ticks.
4. When complete, the input is replaced by the recipe’s output item.
5. If multiple slots contain valid inputs, they process in parallel (each slot has its own progress timer).

## Recipe Format

Recipes are loaded from datapacks: `data/bioforge/centrifuge/*.json`

### Example (`split_bone_to_bone_marrow.json`)
[[Bone Marrow]]

```json
{
  "input": "bioforge:split_bone",
  "output": "bioforge:bone_marrow",
  "copy_blood_data": true,
  "copy_nbt": false,
  "copy_nbt_keys": [],
  "processing_time": 120
}
```

### Fields

| Field            | Type          | Description                                                                 |
|------------------|---------------|-----------------------------------------------------------------------------|
| `input`          | string        | Item ID (e.g., `minecraft:iron_ingot`) or tag (e.g., `#forge:ingots/iron`). |
| `output`         | string        | Item ID or tag of the result. If a tag, a random item from the tag is chosen. |
| `copy_blood_data`| boolean       | If true, copies blood data (type, amount, source) from input to output (for mod blood items). |
| `copy_nbt`       | boolean       | If true, copies **all** NBT from input to output.                           |
| `copy_nbt_keys`  | list of strings | If `copy_nbt` is false, copies only the specified NBT keys (e.g., `["display", "lore"]`). |
| `processing_time`| integer (≥1)  | How many ticks the recipe takes (20 ticks = 1 second).                      |

## Blood Data & NBT Handling

- **Blood data** refers to the mod’s internal obfuscated blood sample information (type, amount, source). When `copy_blood_data: true`, the output item becomes a blood‑containing item (like Bone Marrow) with the same blood properties as the input.
- **NBT copying** works on any item. Use `copy_nbt: true` to copy everything, or list specific keys in `copy_nbt_keys` for selective copying.

## Processing Speed

- Each slot progresses independently. The overall GUI progress ring reflects the slot with the highest completion percentage.

## JEI Integration

The Centrifuge recipes are visible in JEI (Just Enough Items) under the **Centrifuge** category. Clicking a recipe will show the input, output, and processing time (tooltip on the spinner).

## Adding Custom Recipes

1. Create a `.json` file in `data/bioforge/centrifuge/` (e.g., `dirt_to_grass.json`).
2. Define the recipe as above.
3. Run `/reload` or restart the server to load the recipe.

Example custom recipe that turns dirt into grass (for testing):

```json
{
  "input": "minecraft:dirt",
  "output": "minecraft:grass_block",
  "copy_blood_data": false,
  "copy_nbt": false,
  "copy_nbt_keys": [],
  "processing_time": 100
}
```
