#Bones
[[Split Bone]]
[[Withered Split Bone]]

The **Bone Saw** is a tool used to extract split bones from skeletons.

### Stats
- **Durability**: 256
- **Cooldown**: 80 ticks (4 seconds) after a successful extraction
- **Blood drain**: Reduces the target’s blood by 10 points on hit (same as a needle)

### How to Use
1. Equip the Bone Saw in your main hand.
2. Attack a skeleton (or any entity in the `skeleton_blood_sources` or `withered_skeleton_blood_sources` tags).
3. On hit:
   - The target loses 10 blood.
   - A Split Bone (normal or withered) is added to your inventory (or dropped if full).
   - The saw loses 1 durability.
   - The saw enters a 4‑second cooldown.
4. If the target’s blood reaches 0, no bone is dropped.

### Extraction Chance
- Always succeeds if the target has blood and belongs to the correct tag. There is no random chance – the bone is guaranteed as long as the target has >0 blood.
