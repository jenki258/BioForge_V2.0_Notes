#Extra 
`BloodSampleUtil` is a utility class that simplifies reading and writing blood sample data to items (needles, bone marrow, split bones, etc.). It wraps the lower‑level `NbtObfuscator` to handle the specific format required for blood: amount, type, source name, and source UUID.

You do not need to use this class directly unless you are developing add‑ons or modifying the mod. The standard BioForge items already use it internally.

## When Is It Used?

- **Needles** - when drawing blood from an entity.
- **Bone Saw** - when extracting a Split Bone.
- **Centrifuge & Decalcification Fluid** - when copying blood data from input to output.
- **Reagent Vials** - when reading blood data to determine the reaction.

## API Methods

### Check for blood data

```java
boolean hasBlood = BloodSampleUtil.hasBlood(itemStack);
```

Returns `true` if the item contains any blood data (obfuscated).

### Read blood data

```java
ObfuscatedData data = BloodSampleUtil.getData(itemStack);
```

Returns an `ObfuscatedData` record with the following fields:

| Field         | Type     | Description                                |
| ------------- | -------- | ------------------------------------------ |
| `amount`      | `int`    | Blood amount (0-100).                      |
| `typeName`    | `String` | Blood type name (e.g., `"A_POSITIVE"`).    |
| `sourceName`  | `String` | Display name of the source entity.         |
| `subjectUUID` | `UUID`   | UUID of the source entity (may be `null`). |

If no data is present, returns `null`.

### Write blood data

```java
BloodSampleUtil.setData(itemStack, amount, bloodType, sourceName, subjectUUID);
```

- `amount` - blood amount to store.
- `bloodType` - a `BloodType` enum value.
- `sourceName` - the name of the entity the blood came from.
- `subjectUUID` - the entity’s UUID (can be `null`).

The data is obfuscated using `NbtObfuscator.write(...)`.

### Clear blood data

```java
BloodSampleUtil.clear(itemStack);
```

Removes any blood data from the item.

### Copy blood data

```java
BloodSampleUtil.copy(fromStack, toStack);
```

Copies the blood data (amount, type, source name, UUID) from one item stack to another. If the source has no data, the target is cleared.

### Tooltip helper

```java
BloodSampleUtil.appendSampleTooltip(itemStack, tooltipList,
    emptyKey, filledKey, sourceKey, extraKey);
```

Used by items like needles and bone marrow to add consistent tooltips:

- `emptyKey` - translation key when no blood.
- `filledKey` - translation key when blood is present.
- `sourceKey` - translation key for the source name line (e.g., `"item.bioforge.needle.tooltip.source"`).
- `extraKey` - optional extra line (e.g., `"item.bioforge.bone_marrow.tooltip.processed"`).

It also automatically appends reagent knowledge (Anti‑A, Anti‑B, Anti‑D results) if the player has tested that subject.

## Example Usage (from NeedleItem)

```java
// Store blood after a successful draw
BloodSampleUtil.setData(stack, newBlood, bloodType,
                        sourceName, subjectUUID);

// Read back for tooltip
ObfuscatedData data = BloodSampleUtil.getData(stack);
if (data != null) {
    int amount = data.amount();
    BloodType type = BloodType.fromName(data.typeName());
    String source = data.sourceName();
}
```

## Relation to NbtObfuscator

`BloodSampleUtil` is a **convenience layer** on top of `NbtObfuscator`. The underlying NBT structure is still obfuscated - you cannot read the blood data with `/data get` or external inventory viewers.

- `NbtObfuscator.write(tag, amount, typeName, sourceName, subjectUUID)` is used internally.
- `NbtObfuscator.read(tag)` returns an `ObfuscatedData` record that `BloodSampleUtil` simply returns as‑is.

## Developer Notes

- If you add a new item that should carry blood data, use `BloodSampleUtil` to handle reading/writing.
- Do not store blood data in plain NBT - always use the obfuscated methods.
- The `ObfuscatedData` record is immutable and safe to pass around.