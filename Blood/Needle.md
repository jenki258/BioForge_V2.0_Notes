#Tools #Blood
[[Reagents]]
The Needle is a tool used to extract blood from living entities (players and mobs). There are three tiers, each with different success rates, durability, and self‑damage. A needle can also be used to transfer blood into reagent vials for blood typing.

## Needle Tiers

| Tier      | Success Chance | Durability | Cooldown (ticks) | Self‑damage (hearts) |
|-----------|---------------|------------|------------------|----------------------|
| Wooden    | 25%           | 8          | 100              | 1.0                  |
| Iron      | 50%           | 16         | 100              | 1.0                  |
| Hardened  | 100%          | 32         | 100              | 1.0                  |

- Success chance determines whether you actually draw blood from the target.
- Each use (whether successful or not) damages the needle by 1 point and triggers a 100‑tick cooldown (5 seconds).
- Self‑damage is applied only when using the needle on yourself.

## How to Use

### Draw blood from yourself
1. Hold the needle in your **main hand**.
2. **Off‑hand must be empty**.
3. Ensure you are not wearing a chestplate (the code checks `EquipmentSlot.CHEST` - empty is allowed, chestplate blocks the action)
4. Right‑click while looking at nothing (or air). You will take 1 heart of damage, and on success you lose 10 blood points and the needle becomes filled.

### Draw blood from a mob
1. Hold the needle in your main hand.
2. Attack the mob (left‑click) while holding the needle.
3. On success, the mob loses 10 blood, and the needle becomes filled with the mob’s blood.
4. The needle’s durability decreases and cooldown starts.

### Cannot draw blood from:
- Entities tagged with `no_blood` (see [Blood Mechanic.md] for the list).
- Entities that are already dead or have no blood data.

## Needle States

- **Empty** - No blood inside.
- **Filled** - Contains blood from a specific source (mob or player). The needle holds exactly 10 blood points (drawn amount). The blood type and source name are stored.

When filled, the needle shows tooltips:

1. **Source name** - e.g., “Name: Zombie”.
2. **Blood type** - Only shown after you have tested all three reagents (Anti‑A, Anti‑B, Anti‑D) on this blood type and unlocked the knowledge. Otherwise hidden.
3. **Anti‑A** - Shows reaction result (+ or -) after testing with Anti‑A reagent.
4. **Anti‑B** - Shows reaction result after testing with Anti‑B reagent.
5. **Anti‑D (Rh)** - Shows reaction result after testing with Anti‑D reagent.

The reactions are stored in the player’s blood knowledge database.

## Transferring Blood to Reagent Vials

1. Have a **filled needle** in your main hand.
2. Have a **reagent vial** (Anti‑A, Anti‑B, or Anti‑D) in your off‑hand.
3. Right‑click (or use the reagent vial - the code checks for a needle in the other hand). The vial will react:
   - If the blood type contains the corresponding antigen, the vial turns dark red (positive reaction).
   - If not, it turns pale (negative reaction).
   - Animal blood turns the vial yellow.
4. The needle becomes empty (blood data cleared) and can be reused.
5. The reaction result is saved to your blood knowledge (per player, per subject).

## Durability 

- Each use (right‑click on self or attack) reduces durability by 1, regardless of success.

## Tags & Exclusions

- Mobs with the `no_blood` tag cannot give blood at all (they are immune to the needle).
- The needle also respects the `player_blood_give` tag for assigning human blood types.