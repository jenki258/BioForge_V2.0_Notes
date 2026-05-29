#Commands

The **infection commands** allow operators (players with permission level 2 or higher) to manually control infections on living entities. You can infect or cure targets, choose the pathogen type, transmission methods, and even fine‑tune individual symptoms.

### Base syntax

```
/bioforge infect <targets> <infected> [pathogen] [persistent] [infectionType] [symptoms...]
/bioforge cure <targets>
```

- `<targets>` - one or more entities (use selectors like `@e`, `@p`, `@r`, or a player name).
- `<infected>` - `true` (infect) or `false` (clear infection).
- `[pathogen]` - optional pathogen type (default: `universal`).
- `[persistent]` - `true` to save infection across player death/logout (default: `false`).
- `[infectionType]` - comma‑separated list of transmission types (must be allowed for the pathogen; default: `contact_based`; As also you can use multiple by making them in "" and using "," to separate them example  `"environmental,food_borne"` ).

### Pathogen types

| Pathogen | Allowed transmission types | Environmental? |
|----------|---------------------------|----------------|
| `virus` | airborne, contact_based, attack_based, blood, food_borne, water_borne | No |
| `bacteria` | food_borne, water_borne, contact_based, attack_based, environmental, animals | **Yes** |
| `fungi` | airborne, contact_based, food_borne, environmental | **Yes** |
| `parasite` | food_borne, water_borne, animals, attack_based, blood | No |
| `prion` | food_borne, blood, contact_based | No |
| `universal` | all types | No |

- **Environmental** pathogens (`fungi`, `bacteria`) can form underground colonies via Contaminated Substrate.
- If you specify an `infectionType` that the pathogen does not allow, the command fails with an incompatibility message.

### Transmission types

| Type | Meaning                                                          |
| --------------- | ---------------------------------------------------------------- |
| `airborne` | Spread through air (not fully implemented - reserved for future) |
| `food_borne` | Can be caught by eating contaminated food                        |
| `water_borne` | Can be caught by drinking contaminated water (future)            |
| `contact_based` | Spread by touching infected entities/blocks                      |
| `attack_based` | Spread when an infected entity attacks another                   |
| `animals` | Carried by animals                                               |
| `blood` | Spread via blood (needle, transfusion)                           |
| `environmental` | Can form colonies underground (fungi/bacteria only)              |

### Persistent infection

- When `persistent` is `true`, the infection is saved to `InfectionStore` (persistent data across player death, logout, and world reload).
- Without persistence, the infection only exists on the entity while it is alive and loaded.
- For players, persistent infections are restored after death (via `PlayerEvent.Clone`).

### Symptom fine‑tuning (optional)

After specifying the basic parameters, you can add a `symptoms` subcommand to set **exact symptom values** instead of using the defaults. The full syntax is:

```
/bioforge infect <targets> true <pathogen> <persistent> <infectionType> symptoms
    <heartRate> <lungSound> <tempPlus> <tempMinus>
    <redness> <lesions> <secretion> <swelling>
    <reflexDelay> <reflexStrength> <neuralDamage>
    <oxygenSaturation> <perfusionIndex>
    <infectionStrength> <colonyRadius> <maxInfestedBlocks>
```

| Argument            | Type    | Range / Values             | Description                                                        |
| ------------------- | ------- | -------------------------- | ------------------------------------------------------------------ |
| `heartRate`         | enum    | `normal`, `tachy`, `brady` | Heart rate status                                                  |
| `lungSound`         | enum    | `normal`, `crackle`        | Lung sound status                                                  |
| `tempPlus`          | boolean | `true`/`false`             | Has fever                                                          |
| `tempMinus`         | boolean | `true`/`false`             | Has hypothermia                                                    |
| `redness`           | float   | 0.0 - 1.0                  | Otoscope redness severity                                          |
| `lesions`           | float   | 0.0 - 1.0                  | Otoscope lesions severity                                          |
| `secretion`         | float   | 0.0 - 1.0                  | Otoscope secretion severity                                        |
| `swelling`          | float   | 0.0 - 1.0                  | Otoscope swelling severity                                         |
| `reflexDelay`       | float   | 0.0 - 2.0                  | Reflex delay (higher = worse)                                      |
| `reflexStrength`    | float   | 0.0 - 1.0                  | Reflex strength (lower = worse)                                    |
| `neuralDamage`      | float   | 0.0 - 1.0                  | Neural damage level                                                |
| `oxygenSaturation`  | float   | 0.0 - 1.0                  | SpO₂ (1.0 = 100%)                                                  |
| `perfusionIndex`    | float   | 0.0 - 1.0                  | Blood flow strength                                                |
| `infectionStrength` | float   | 0.0 - 1.0                  | General infection severity (affects crop drop contamination, etc.) |
| `colonyRadius`      | float   | 1.0 - 5000.0               | How far colony can spread (if environmental)                       |
| `maxInfestedBlocks` | float   | 1.0 - 10000.0              | Max number of Infested Blocks for colony                           |

> **Note:** All float values are clamped to their allowed ranges by the command argument definitions.

### Cure command

```
/bioforge cure <targets>
```

- Removes all infection data from the target entities.
- Clears persistent storage for players.
- Syncs the cleared state to the client.

### Examples

```mcfunction
# Infect the nearest player with a basic universal infection (contact_based)
/bioforge infect @p true

# Infect all zombies with fungi, persistent, environmental spread
/bioforge infect @e[type=zombie] true fungi true environmental

# Infect yourself with a custom prion strain (food_borne), low oxygen, high neural damage
/bioforge infect @s true prion true food_borne symptoms normal normal false true 0 0 0 0 0.1 0.2 0.8 0.70 0.3 0.2 30 80

# Cure all players
/bioforge cure @a
```

### Default symptoms

If you do **not** specify custom symptoms, the command calls `InfectionEventHandler.applyDefaultSymptoms()`, which generates random symptom values appropriate for the pathogen type (e.g., Bacteria cause higher redness/secretion; Prions cause high neural damage, low reflexes). This creates varied, realistic infections without manual tweaking.

### Compatibility checks

- The command checks that every specified `infectionType` is allowed by the chosen `pathogen`. If not, it fails with a clear error message.
- It also checks that the target is a `LivingEntity` (players, mobs - not items, projectiles, etc.).