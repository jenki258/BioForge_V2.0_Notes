#Commands 

These commands allow operators to manage a player’s stored blood knowledge - the record of which reagents (Anti‑A, Anti‑B, Anti‑D) have been tested on blood from each subject (mob or player). The knowledge system enables the mod to reveal the full blood type on items only after all three reagents have been tested on that subject.

All commands are under `/bioforge` and require **permission level 2** (operator)

---

## Commands

### 1. List all entries for a player

```
/bioforge bloodknowledge_list <player>
```

- **Description**: Shows all blood knowledge entries stored for the specified player.
- **Arguments**:
  - `<player>` - The player whose knowledge to list.
- **Output**: For each entry, displays:
  - Subject name
  - Subject type (entity registry name)
  - Subject UUID
  - Anti‑A result (`+`, `-`, or `?` if not tested)
  - Anti‑B result
  - Anti‑D result

**Example**:
```
/bioforge bloodknowledge_list Steve
```
Output:
```
[BioForge] Blood knowledge for Steve (2 entries):
- Zombie [minecraft:zombie] UUID=1234... A=+ B=- D=?
- Skeleton [minecraft:skeleton] UUID=5678... A=? B=? D=+
```

---

### 2. Copy knowledge from entities to a player

```
/bioforge bloodknowledge_get <player> <entities>
```

- **Description**: Forces the specified player’s knowledge to be updated with blood data from the given entities. For each entity, the command records **all three reagent results** (Anti‑A, Anti‑B, Anti‑D) based on the entity’s actual blood type.
- **Arguments**:
  - `<player>` - The player who will receive the knowledge.
  - `<entities>` - One or more entities (use selectors like `@e`, `@p`, or UUIDs).
- **Use case**: Useful for testing or migrating old save data - instantly unlocks blood types without needing to test reagents manually.

**Example**:
```
/bioforge bloodknowledge_get Steve @e[type=zombie,limit=1]
```
This adds full knowledge of that zombie’s blood type to Steve’s storage.

---

### 3. Clear a specific entry from a player

```
/bioforge bloodknowledge_clear <player> <entry>
```

- **Description**: Removes a single blood knowledge entry (a specific subject) from the player’s storage.
- **Arguments**:
  - `<player>` - The player whose knowledge to modify.
  - `<entry>` - The entry identifier, formatted as `subject name | subject UUID`.  
    The command suggests existing entries when you press Tab.
- **Output**: Confirmation message if removed, or error if not found.

**Example**:
```
/bioforge bloodknowledge_clear Steve "Zombie | 12345678-1234-1234-1234-123456789abc"
```

---

### 4. Clear all entries for a player

```
/bioforge bloodknowledge_clearall <player>
```

- **Description**: Deletes **all** blood knowledge entries for the specified player.
- **Output**: Number of entries removed.

**Example**:
```
/bioforge bloodknowledge_clearall Steve
```

---

## Understanding the Output

When listing entries, the results are shown as:

- `+` - Reaction detected (the reagent reacted with the blood).
- `-` - No reaction.
- `?` - Not yet tested (null).

Once all three reagents are non‑null, the blood type is fully determined. Future items containing blood from that subject will display the full blood type in their tooltip.

---

## Storage Limits

- Each player can store up to **2000 entries** (subjects). When the limit is reached, the oldest entry (by `lastUpdated`) is automatically removed to make room for new ones.
- See [[Blood Info Storage]] for technical details.