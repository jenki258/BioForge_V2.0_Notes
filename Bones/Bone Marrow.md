#Bones 
Bone Marrow is a refined blood sample obtained by processing a **Split Bone** in a Centrifuge. It contains the blood data (type, amount, source) of the original entity. Unlike Split Bone, Bone Marrow **can be used directly with reagents** to determine the blood type.

## Obtaining

- **Machine required**: Centrifuge
- **Input**: Split Bone (containing blood data)
- **Processing time**: 120 ticks (6 seconds)
- **Result**: Bone Marrow item with the same blood data as the original Split Bone.

## Properties

- **Stacks to**: 1.
- **Contains**: Obfuscated NBT data storing:
  - Blood amount
  - Blood type (e.g., A+, O-, Animal)
  - Source name (entity’s display name)
  - Source UUID

## Tooltip

- **If containing blood**:  
  - `Refined marrow sample` (dark gray)  
  - Source name (e.g., `Name: Skeleton`)  
  - (After all three reagents are tested, the blood type is also shown: `Blood type: A+`)
- **If empty**:  
  - `No marrow data` (dark gray)

## Usage with Reagents

Bone Marrow can be used **exactly like a bloody needle** to test blood type with reagents:

1. Hold the **Bone Marrow** in your **off‑hand**.
2. Hold a **reagent vial** (Anti‑A, Anti‑B, or Anti‑D) in your **main hand**.
3. Right‑click. The reagent will react based on the blood type stored in the marrow.
4. The result is recorded in your blood knowledge.
5. The Bone Marrow is **consumed** after use.

## Relation to Withered Bone Marrow

- **Withered Bone Marrow** is obtained from Withered Split Bone via Decalcification Fluid (not the Centrifuge). It also works with reagents, but its processing path is different.
- Both types of marrow serve the same purpose: they allow blood typing without a needle.