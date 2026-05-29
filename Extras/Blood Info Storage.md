#Extra
The mod stores **blood knowledge** per player - a record of which reagents (Anti‑A, Anti‑B, Anti‑D) have been tested on blood from each subject (mob or player). This allows the mod to reveal the blood type on items (needles, bone marrow) only after all three reagents have been tested on that subject.

## Storage Limits

- Each player can store up to **2000 entries** (subjects) in their knowledge base.
- When the limit is reached, the **oldest entry** (based on `lastUpdated` timestamp) is automatically removed to make space for new ones.

## What Is Stored

For each entry (player + subject pair), the following data is saved:

| Field         | Description                                                                                  |
| ------------- | -------------------------------------------------------------------------------------------- |
| `subjectUUID` | Unique identifier of the subject (mob or player).                                            |
| `subjectName` | Display name of the subject at the time of first test.                                       |
| `subjectType` | Entity type registry name (e.g., `minecraft:zombie`).                                        |
| `isPlayer`    | Whether the subject is a player.                                                             |
| `antiA`       | `Boolean` - result of Anti‑A test (true = reaction, false = no reaction, null = not tested). |
| `antiB`       | `Boolean` - result of Anti‑B test.                                                           |
| `antiD`       | `Boolean` - result of Anti‑D (Rh) test.                                                      |
| `lastUpdated` | Timestamp (milliseconds) of the last update to this entry.                                   |

## How Knowledge Is Gained

1. You use a **reagent vial** (Anti‑A, Anti‑B, or Anti‑D) on a blood sample (needle, bone marrow, etc.).
2. The mod records the reaction result for that specific reagent against that subject.
3. If all three reagents have been tested (Anti‑A, Anti‑B, and Anti‑D are non‑null), the **blood type** is considered “unlocked”. Future items containing blood from the same subject will display the full blood type in their tooltip.

## Persistence

- Blood knowledge is saved to the **world’s `SavedData`** - it persists across server restarts, player logouts, and even player death.
- Data is stored under the key `bioforge_blood_knowledge` in the `data` folder of the world.

## Example Workflow

1. You draw blood from a zombie with a needle.
2. Test the needle with Anti‑A → positive. Now the knowledge for that zombie has `antiA = true`.
3. Test the same zombie’s blood again with Anti‑B → negative. Now `antiB = false`.
4. Test with Anti‑D → positive. Now `antiD = true`.
5. Since all three are known, the game determines the blood type (A+ in this case). Any future needles or bone marrow from that zombie will show “Blood type: A+” in the tooltip.

## Technical Notes

- The storage is implemented as `BloodKnowledgeStore`, which extends `SavedData`.
- Each player’s entries are stored in a `LinkedHashMap<UUID, BloodKnowledge>` to preserve insertion order and easily find the oldest.
- The `enforceLimit()` method trims the map when it exceeds `MAX_ENTRIES = 2000`.
- Reagent results are recorded via `recordReagent()` in `BloodKnowledgeStore`, which updates the entry and marks the data as dirty (`setDirty()`).
