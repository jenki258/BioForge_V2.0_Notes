#Commands

These commands allow operators (and, for `get_blood`, any player) to inspect and modify the blood data of entities. You can view current blood levels and phases, set blood amount or type, and reset blood to full with a random type.

Requires **permission level 2** (operator).

---

## Commands

### 1. Get blood information

```
/bioforge get_blood <entity>
```

- **Description**: Displays the current blood amount, maximum, blood type, and phase for the target entity.
- **Arguments**:
  - `<entity>` - A single entity (player, mob, etc.).
- **Output**: Example:  
  `[BioForge] Zombie - Blood: 85/100  Type: A+  Phase: NORMAL`

---

### 2. Set blood amount

```
/bioforge set_blood amount <entities> <amount>
```

- **Description**: Sets the blood amount of the target entities to the specified value.
- **Arguments**:
  - `<entities>` - One or more entities (selectors allowed).
  - `<amount>` - Integer between 0 and 100 (inclusive).
- **Behaviour**:
  - Clamps the value to 0-100 automatically.
  - Syncs the new blood data to the client for players.
  - Sends a confirmation message to the command source.

**Example**:
```
/bioforge set_blood amount @e[type=zombie,limit=5] 50
```
Sets all zombies (up to 5) to 50 blood points.

---

### 3. Set blood type

```
/bioforge set_blood type <entities> <type>
```

- **Description**: Sets the blood type of the target entities to the specified type.
- **Arguments**:
  - `<entities>` - One or more entities.
  - `<type>` - Valid blood type name (case‑insensitive). Options:
    - `a_positive`, `a_negative`
    - `b_positive`, `b_negative`
    - `ab_positive`, `ab_negative`
    - `o_positive`, `o_negative`
    - `animal_blood`
- **Tab completion** suggests all valid types.
- **Behaviour**:
  - If an invalid type is provided, the command fails with a list of valid types.
  - Syncs the new blood type to the client for players.

**Example**:
```
/bioforge set_blood type @p o_negative
```
Sets the nearest player to O‑negative.

---

### 4. Reset blood

```
/bioforge reset_blood <entities>
```

- **Description**: Resets the target entities to full blood (100 points) and randomises their blood type.
- **Arguments**:
  - `<entities>` - One or more entities.
- **Behaviour**:
  - Blood amount set to `100`.
  - Blood type set randomly:
    - For players and entities in the `player_blood_give` tag: random human type.
    - For other entities: `animal_blood`.
  - Syncs changes to client for players.

**Example**:
```
/bioforge reset_blood @e[type=zombie]
```
Resets all zombies to full health with a random human blood type (since zombies are in `player_blood_give` by default).

---

## Blood Phase Reference

The command output shows the phase based on current blood amount:

| Blood level | Phase    |
| ----------- | -------- |
| ≥70         | NORMAL   |
| 40-69       | WEAKNESS |
| 20-39       | SEVERE   |
| <20         | CRITICAL |

These phases affect status effects and regeneration rate.

---

## Examples in Practice

### Diagnose a player
```
/bioforge get_blood Steve
```
Output: `[BioForge] Steve - Blood: 30/100  Type: AB+  Phase: SEVERE`

### Cure blood loss instantly
```
/bioforge set_blood amount Steve 100
```

### Change a zombie’s blood type for testing
```
/bioforge set_blood type @e[type=zombie,limit=1] o_positive
```

### Reset all zombies to default (full blood, random human type)
```
/bioforge reset_blood @e[type=zombie]
```

## Notes

- Blood amount is clamped to 0-100 automatically; you cannot set it higher than 100.
- The reset command does **not** affect any other infection or status effects - only blood data.