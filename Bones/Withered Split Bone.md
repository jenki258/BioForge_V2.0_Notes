#Bones

Withered Split Bone is a calcified bone fragment obtained from wither skeletons (and other entities tagged as `withered_skeleton_blood_sources`) using the Bone Saw. It contains the **blood data** (type, amount, source) of the entity it was taken from. Unlike normal Split Bone, Withered Split Bone cannot be processed in a Centrifuge; it requires **Decalcification Fluid** to become usable Withered Bone Marrow.

## Obtaining

- **Tool required**: Bone Saw
- **Source entities**: Any entity in the `withered_skeleton_blood_sources` tag (default: `minecraft:wither_skeleton`).
- **Process**: Attack the entity with a Bone Saw. On successful hit:
  - The target loses 10 blood points.
  - A Withered Split Bone item is added to your inventory (or dropped on the ground if full).
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
  - `Contains withered marrow sample` (dark gray)  
  - `Requires decalcification before use` (dark purple)  
  - (No blood type shown - requires processing to Withered Bone Marrow first)
- **If empty** (no blood data):  
  - `Empty withered bone fragment` (dark gray)

## Processing

Withered Split Bone must be **decalcified** using **[[Decalcification Fluid]]** to become usable with reagents. It cannot be used in a Centrifuge.

Once decalcified into Withered Bone Marrow, you can use it with reagents to determine the blood type.
## Relation to Split Bone

- **Split Bone** (normal) is obtained from regular skeletons and processed in a **Centrifuge** into Bone Marrow.
- **Withered Split Bone** requires **Decalcification Fluid** instead of a Centrifuge, because the bone is calcified and must be softened chemically.

## Notes

- Withered Split Bone cannot be used directly with reagents (the code in `ReagentVialItem` only accepts `NeedleItem`, `BoneMarrowItem`, and `WitheredBoneMarrowItem` - not `WitheredSplitBoneItem`).
- The blood data is obfuscated using `NbtObfuscator`.
- If you have a Withered Split Bone, you must decalcify it before you can test its blood type.