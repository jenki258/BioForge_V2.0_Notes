# BioForge Command Reference

#BioForge #BioForge_V2_0 #Build_V0_54T #Command #LegacyUpdated

#Commands 

This is the current test-build command map. Most development/research operations require permission level 2. Use Brigadier suggestions for exact optional branches and loaded resource IDs.

## Infection

- `/bioforge infect <targets> <infected> ...` — configures infection state with pathogen, persistence, infection type, symptom pairs, or mutation IDs through its branches.
- `/bioforge cure <targets>` — removes the active BioForge infection.

See [[Infect & Cure]] for older detailed examples; current in-game suggestions are authoritative where the page differs.

## Mutations

Root: `/bioforge mutate`

- `info <mutation_id>`
- `definitions [pathogen]`
- `<targets> apply <mutation_id> [force]`
- `<targets> add <mutation_id>`
- `<targets> remove <mutation_id>`
- `<targets> random [count]`
- `<targets> list`
- `<targets> clear`
- `<targets> refresh`

`force` is a development escape hatch and can bypass normal compatibility.

## Vaccine development

`/bioforge vaccinemake <source> [quality] [uses] [defense_risk]`

Creates a development Full Strain Vaccine from a source entity. Normal gameplay uses the Vaccine Maker.

## CRISPR development

Root: `/bioforge crispr`

- `definitions` — loaded research definitions.
- `cartridge <slot 1..15> <sequence> [profile]` — creates/programs a cartridge.
- `casmake <module>` — creates a loaded Cas Module.
- `directedmake <source> <category> <target> <action> ...` — creates a directed development profile/vaccine; follow suggestions for optional quality/result values.

## Strain catalogue

- `/bioforge strain current` — current player's active strain identity state.
- `/bioforge strain list` — operator list of catalogue entries.
- `/bioforge strain rename <fingerprint> <name>` — operator moderation rename.

Players use the automatic first-discovery naming GUI; there is no normal player naming command.

## Blood

- `/bioforge get_blood <entity>`
- `/bioforge set_blood amount <entities> <amount>`
- `/bioforge set_blood type <entities> <type>`
- `/bioforge reset_blood <entities>`

See [[Blood command]].

## Blood knowledge

- `/bioforge bloodknowledge_list <player>`
- `/bioforge bloodknowledge_get <player> <entities>`
- `/bioforge bloodknowledge_clearall <player>`
- `/bioforge bloodknowledge_clear <player> <entry>`

See [[Blood Knowledge command]].

## Safety

- Commands are server-authoritative.
- Forced mutation/direct vaccine creation bypass intended progression and should remain operator-only.
- Use suggested resource IDs after `/reload`.
- Back up worlds before bulk mutation or catalogue operations.

