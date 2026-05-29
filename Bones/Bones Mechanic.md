#Bones
[[Bone Saw]]

The bones mechanic allows you to extract **Split Bones** from skeletons using a Bone Saw. These bones contain blood data from the entity. Split bones can be further processed into **Bone Marrow** (via Centrifuge) or **Withered Bone Marrow** (via Decalcification Fluid). Bone marrow can then be used with reagents to determine the blood type of the source entity.

All bone items store the blood data (type, amount, source UUID) of the entity they were taken from.

## Tags for Bone Sources

You can add or remove entities from the bone sources via datapack tags in `data/bioforge/tags/entity_types/`.

### `skeleton_blood_sources.json`
Entities that drop **normal Split Bone**:

```json
{
  "replace": false,
  "values": [
    "minecraft:skeleton",
    "minecraft:stray",
    "minecraft:skeleton_horse"
  ]
}
```

### `withered_skeleton_blood_sources.json`
Entities that drop **withered Split Bone**:

```json
{
  "replace": false,
  "values": [
    "minecraft:wither_skeleton"
  ]
}
```

> Note: The bone saw also takes 10 blood from the target.
