# Mutations

Mutations are reloadable definitions that change how an active infection behaves. They are stored on the infection, evaluated on the server, and can produce compound behavior when several coexist.

## Player-facing behavior

- Mutations can come from random selection, commands, vaccine failure, a Random Mutation Vaccine, or another mutation interaction.
- A mutation may immediately change strain data, keep applying effects while infected, and/or run cleanup behavior when removed.
- Random selection respects pathogen compatibility, prerequisites, conflicts, enabled state, and weight.
- The mutation scrolling overlay presents a real selected result.
- Hidden definitions can avoid normal disclosure while remaining usable by rules.

## Bundled set

| Mutation | Intended role |
|---|---|
| Bloodborne | Blood-oriented transmission behavior. |
| Hypervirulence | Higher infection pressure and stronger combinations. |
| Necrotic Fever | Persistent fever/weakness behavior. |
| Neural Decay | Neurological disease behavior. |
| Spore Cloud | Spore/transmission behavior. |
| Vaccine Defense | Immune escape and treatment resistance. |
| Reinforced Vaccine Defense | Compound mutation requiring Vaccine Defense and Hypervirulence. |

The JSON files are examples, not a hard-coded maximum.

## Definition fields

A file under `data/<namespace>/mutations/*.json` can contain:

| Field | Meaning |
|---|---|
| `id` | Stable internal mutation ID. |
| `name`, `description` | Readable metadata. |
| `pathogens` | Compatible pathogen families or `UNIVERSAL`. |
| `rarity`, `weight` | Metadata and random-selection weight. |
| `enabled`, `hidden` | Availability and disclosure. |
| `icon` | Optional visual resource. |
| `requires` | Mutations that must already exist. |
| `conflicts` | Mutations that prevent normal addition. |
| `tags` | Semantic flags used by treatment/addon logic. |
| `effects` | Mutation behaviors. |
| `interactions` | Combination behaviors. |

## Lifecycle

| Trigger | Use |
|---|---|
| `apply` | Runs when introduced or reconstructed; useful for strain-data changes. |
| `continuous` | Evaluated while infected with optional interval/chance/conditions. |
| `remove` | Runs when removed and can reverse or finish behavior. |

Aliases such as `once`, `on_apply`, `tick`, `while_infected`, and `on_remove` are accepted. Runtime behavior refreshes after login, respawn, load, and data reload.

## Supported effect types

| Type | Purpose |
|---|---|
| `modify_symptom` | Modify and clamp a numeric symptom such as infection strength. |
| `set_symptom` | Set a boolean, enum, or numeric symptom value. |
| `add_infection_type` | Add an infection/transmission route. |
| `remove_infection_type` | Remove an infection/transmission route. |
| `potion_effect` | Apply a Minecraft mob effect. |
| `spawn_particle` | Spawn particles around the host. |
| `attribute_modifier` | Add/multiply an entity attribute with cleanup. |
| `damage` | Deal generic, magic, wither, fire, or drowning-style damage. |
| `heal` | Heal the host. |
| `exhaustion` | Add player exhaustion. |
| `ignite` | Set the host on fire. |
| `play_sound` | Play a configured sound. |

Effects can use interval, chance, duration/amplifier, clamps, particle values, attribute operations, and health conditions. Invalid definitions are rejected during reload rather than becoming arbitrary behavior.

## Interactions

An interaction activates when any or all configured partner mutations are present. It can:

- Add extra effects.
- Modify a numeric parameter on a matching continuous effect.
- Suppress a matching effect.
- Grant another mutation.
- Remove an existing mutation.
- Force a grant when explicitly configured.

Example concept:

```json
{
  "id": "hypervirulent_fever",
  "with": "hypervirulence",
  "effect_modifiers": [
    {
      "match": {
        "type": "potion_effect",
        "target": "minecraft:weakness",
        "trigger": "continuous"
      },
      "parameter": "amplifier",
      "add": 1,
      "min": 0,
      "max": 4
    }
  ]
}
```

Necrotic Fever still owns the weakness effect, while Hypervirulence amplifies it. This avoids a Java branch for every possible pair.

## Vaccine interaction

- Full-vaccine cure chance is reduced by defense/immune-escape behavior.
- Failed treatment can preferentially select the configured defense mutation.
- Directed Mutation Vaccines can add or remove a known target.
- Random Mutation Vaccines select a compatible definition without revealing it immediately.
- Tags can encode special treatment requirements, including Rh-related requirements.

## Data-pack guidance

- Keep IDs stable after worlds store them.
- Prefer semantic tags for cross-system meaning.
- Use `weight: 0` for compound-only mutations.
- Use `requires` and `conflicts` to constrain random pools.
- Use interactions for synergy instead of duplicating every pair.
- Test attribute cleanup, reload behavior, and multiplayer visuals.

The `/bioforge mutate` tree supports inspection, apply/add, remove, random, list, clear, refresh, and forced development operations. See [[BioForge Command Reference]].

