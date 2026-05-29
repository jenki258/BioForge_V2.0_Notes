#Bones
Split Bone is a bone fragment obtained from skeletons (and other entities tagged as `skeleton_blood_sources`) using the Bone Saw. It contains the **blood data** (type, amount, source) of the entity it was taken from. Split Bone cannot be used directly with reagents; it must first be processed into **Bone Marrow** via the Centrifuge.

## Obtaining

- **Tool required**: Bone Saw
- **Source entities**: Any entity in the `skeleton_blood_sources` tag (default: `minecraft:skeleton`, `minecraft:stray`, `minecraft:skeleton_horse`).
- **Process**: Attack the entity with a Bone Saw. On successful hit:
  - The target loses 10 blood points.
  - A Split Bone item is added to your inventory (or dropped on the ground if full).
  - The Bone Saw loses 1 durability and goes on cooldown (80 ticks / 4 seconds).

## Properties

- **Stacks to**: 1.
- **Contains**: Obfuscated NBT data storing:
  - Blood amount
  - Blood type (e.g., A+, O-, Animal)
  - Source name (entity’s display name)
  - Source UUID

## Tooltip

- **If containing blood**:  
  - `Contains raw split marrow` (dark gray)  
  - (No blood type shown - requires processing to Bone Marrow first)
- **If empty** (no blood data):  
  - `No marrow sample` (dark gray)

## Processing

Split Bone must be processed in a **[[Centrifuge]]** to become usable with reagents.

## Relation to Withered Split Bone

- **Withered Split Bone** is obtained from wither skeletons (and entities in `withered_skeleton_blood_sources`). It has a different processing path: it requires **Decalcification Fluid** to become Withered Bone Marrow, not the Centrifuge.

## Notes

- Split Bone cannot be used directly with reagents (the code in `ReagentVialItem` only accepts `NeedleItem`, `BoneMarrowItem`, and `WitheredBoneMarrowItem` - not `SplitBoneItem`).
- The blood data is obfuscated using `NbtObfuscator`.
- If you have a Split Bone, you must process it in a Centrifuge before you can test its blood type.