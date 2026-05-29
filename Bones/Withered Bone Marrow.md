#Bones

Withered Bone Marrow is a refined blood sample obtained by decalcifying a **Withered Split Bone** using Decalcification Fluid. It contains the blood data (type, amount, source) of the original wither skeleton (or other withered source). Like normal Bone Marrow, Withered Bone Marrow **can be used directly with reagents** to determine the blood type.

## Obtaining

- **Process required**: Decalcification
- **Input**: Withered Split Bone (containing blood data)
- **Tool**: Decalcification Fluid (held in main hand)
- **How to use**: Hold Withered Split Bone in off‑hand, Decalcification Fluid in main hand, then right‑click.
- **Result**: Withered Bone Marrow item with the same blood data as the original Withered Split Bone.
- **Consumption**: Both the Withered Split Bone and the Decalcification Fluid are consumed.

## Properties

- **Stacks to**: 1.
- **Contains**: Obfuscated NBT data storing:
  - Blood amount
  - Blood type (e.g., A+, O-, Animal)
  - Source name (entity’s display name)
  - Source UUID

## Tooltip

- **If containing blood**:  
  - `Contains marrow sample` (dark gray).
  - `Decalcified` (dark gray).
  - Source name (e.g., `Name: Wither Skeleton`)  
  - (After all three reagents are tested, the blood type is also shown: `Blood type: A+`)
- **If empty** :  
  - `No sample` (dark gray)

## Usage with Reagents

Withered Bone Marrow can be used **exactly like a bloody needle or normal Bone Marrow** to test blood type with reagents:

1. Hold the **Withered Bone Marrow** in your **off‑hand**.
2. Hold a **reagent vial** (Anti‑A, Anti‑B, or Anti‑D) in your **main hand**.
3. Right‑click. The reagent will react based on the blood type stored in the marrow.
4. The result is recorded in your blood knowledge.
5. The Withered Bone Marrow is **consumed** after use.

## Relation to Bone Marrow

- **Bone Marrow** is obtained from normal Split Bone via Centrifuge.
- **Withered Bone Marrow** is obtained from Withered Split Bone via Decalcification Fluid.
- Both serve the same purpose: they allow blood typing without a needle.
- The only difference is the processing method.