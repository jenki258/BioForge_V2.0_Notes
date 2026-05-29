#Chemicals
[[Withered Bone Marrow]]
Decalcification Fluid is a chemical reagent used to **soften calcified biological samples** (e.g., Withered Split Bone) and transform them into a usable form (e.g., Withered Bone Marrow). It works via JSON‑defined recipes and is consumed on use.

## How to Use

1. Hold the **Decalcification Fluid** in your **main hand**.
2. Hold the **calcified item** (e.g., Withered Split Bone) in your **off‑hand**.
3. Right‑click (use the fluid).
4. If a valid recipe exists for the input item, the input is consumed, the fluid is consumed, and the output item is produced (added to your inventory or dropped if full).
5. The output inherits blood data and NBT according to the recipe settings.

> The fluid only works when held in the main hand. If you hold it in the off‑hand, you receive an error message: “Hold the fluid in your main hand.”

## Recipe Format

Decalcification recipes are loaded from datapacks: `data/bioforge/decalcification/*.json`

### Example (`withered_split_bone_to_marrow.json`)

```json
{
  "input": "bioforge:withered_split_bone",
  "output": "bioforge:withered_bone_marrow",
  "copy_blood_data": true,
  "copy_nbt": false,
  "copy_nbt_keys": []
}
```

### Fields

| Field            | Type          | Description                                                                 |
|------------------|---------------|-----------------------------------------------------------------------------|
| `input`          | string        | Item ID (e.g., `bioforge:withered_split_bone`) or tag (e.g., `#forge:bone`). |
| `output`         | string        | Item ID or tag of the result. If a tag, a random item from the tag is chosen. |
| `copy_blood_data`| boolean       | If true, copies blood data (type, amount, source) from input to output.     |
| `copy_nbt`       | boolean       | If true, copies **all** NBT from input to output.                           |
| `copy_nbt_keys`  | list of strings | If `copy_nbt` is false, copies only the specified NBT keys (e.g., `["display", "lore"]`). |

## Validation

- If the input item has no blood data and the recipe requires `copy_blood_data: true`, the operation fails with the message: “The calcified item contains no blood sample.”
- If no recipe matches the input item, you receive: “No calcified item in offhand” (or a hint if the fluid is in the wrong hand).

## Supported Items

- By default, the mod includes a recipe for `withered_split_bone` → `withered_bone_marrow`.
- You can add your own recipes via datapacks for any item or tag.

## Adding Custom Recipes

Create a `.json` file in `data/bioforge/decalcification/`:

```json
{
  "input": "#bioforge:calcified_bones",
  "output": "bioforge:bone_marrow",
  "copy_blood_data": true,
  "copy_nbt": false,
  "copy_nbt_keys": []
}
```

Then define the tag `data/bioforge/tags/items/calcified_bones.json` listing all items that should be decalcified to bone marrow.