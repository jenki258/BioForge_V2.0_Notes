#Blood
[[Reagents]]
[[Bones Mechanic]]
[[Blood Info Storage]]

Every living entity (players and most mobs) has a **blood amount** (0-100) and a **blood type**. Blood level affects the entity with status effects (weakness, slowness, blindness). Blood naturally regenerates over time, and blood loss can be caused by needles, bone saws, or other mechanics.

## Blood Amount & Phases

| Blood level | Phase    | Effects                                                                                |
| ----------- | -------- | -------------------------------------------------------------------------------------- |
| ≥70         | Normal   | No effects. Regeneration: 1 point every 100 ticks (5 seconds).                         |
| 40-69       | Weakness | Weakness I. Regeneration: 1 point every 200 ticks (10 seconds).                        |
| 20-39       | Severe   | Weakness II + Slowness I. Regeneration: 1 point every 300 ticks (15 sec).              |
| <20         | Critical | Weakness II + Slowness II + Blindness. Regeneration: 1 point every 400 ticks (20 sec). |

> All entities start with 100 blood and regenerate towards full.

## Blood Types

### Human types (for players and certain mobs)
- A+ , A- , B+ , B- , AB+ , AB- , O+ , O-

### Non-human
- Animal Blood

**Random assignment:**  
- Players and mobs tagged with `player_blood_give` (see tags) receive a random human blood type.  
- Other mobs receive `animal_blood`.

## Compatibility (for transfusion - planned)
Human blood compatibility follows real‑world rules:
- O- is universal donor to all humans.
- AB+ is universal recipient.
- Rh factor matters: positive can receive positive or negative; negative can only receive negative.

Animal blood is only compatible with the same animal species (i.e., identical blood type).

## Blood Regeneration

Regeneration rate depends on the current phase (see table above). The mod automatically adds 1 blood point at the appropriate interval.

## Tag Configuration (datapacks)

You can control which entities give blood and which have human blood types using entity type tags in `data/bioforge/tags/entity_types/`.

### `player_blood_give.json`
Entities in this tag receive a random human blood type (instead of animal blood).

Default values (from code):
```json
{
  "replace": false,
  "values": [
    "minecraft:zombie", "minecraft:skeleton", "minecraft:stray",
    "minecraft:wither_skeleton", "minecraft:evoker", "minecraft:husk",
    "minecraft:piglin", "minecraft:piglin_brute", "minecraft:pillager",
    "minecraft:vindicator", "minecraft:witch", "minecraft:zombie_villager",
    "minecraft:zombified_piglin", "minecraft:villager", "minecraft:enderman",
    "minecraft:drowned", "minecraft:wandering_trader"
  ]
}
```

### `no_blood.json`
Entities in this tag **cannot** give blood via needle (and likely have no blood data). The list includes skeletons, golems, boats, minecarts, projectiles, and many non‑living entities.