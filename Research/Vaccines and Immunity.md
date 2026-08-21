# Vaccines and Immunity

#BioForge #BioForge_V2_0 #Build_V0_54T #Research #LegacyUpdated

#Extra 

BioForge V2 separates complete-strain treatment from targeted genetic intervention. A vaccine stores a synthesized profile and quality; it is not a renamed potion.

## Families

### Full Strain Vaccine

Attempts to cure an active sufficiently similar infection. On success it grants temporary immunity to the exact fingerprint. Exact match is valuable but not an automatic 100% cure.

### Mutation Vaccine

Targets one mutation through a matching Gene Imprint and JSON action. The default auto-opposite behavior removes the mutation when present and can add it when absent.

### Transmission Vaccine

Targets an infection/transmission route and can remove an existing route or introduce the selected route when absent.

### Symptom Vaccine

Targets a symptom parameter. An action can remove, reduce, set, or introduce it, preserving the risky BioForge V1 idea that incorrect intervention can worsen disease.

### Random Mutation Vaccine

Requires a matching active infection and selects one compatible mutation while respecting pathogen, requirements, conflicts, enabled state, and available definitions. Immediate feedback does not identify the result; the player must analyze it.

## Full cure model

The full path checks vaccine profile/uses, active infection, similarity, quality, infection strength, defense mutations, ABO/Rh host compatibility, and the server cap.

Conceptually:

`chance = potency × quality × similarity curve × strength resistance × defense modifier × blood compatibility`

The implementation clamps/caps this probability. Equality is not a guaranteed cure.

## Default world serverconfig

### `vaccines`

| Key | Default | Meaning |
|---|---:|---|
| `minimumSimilarity` | 0.45 | Below this a full vaccine has no cure chance. |
| `similarityCurveFloor` | 0.40 | Bottom reference for the quadratic similarity curve. |
| `basePotency` | 0.95 | Potency before quality/resistance modifiers. |
| `maximumCureChance` | 0.85 | Hard final cap. |
| `strengthResistance` | 2.25 | How strongly infection strength reduces success. |
| `defenseMutationCureMultiplier` | 0.35 | Multiplier with vaccine-defense/immune-escape. |
| `defenseRiskStrengthScale` | 0.75 | Strength contribution to defense-mutation risk. |
| `defenseRiskMismatchScale` | 0.50 | Mismatch contribution to defense risk. |
| `strainImmunityDurationTicks` | 12000 | Base exact-strain immunity; ten loaded minutes. |

### `bloodCompatibility`

| Key | Default | Meaning |
|---|---:|---|
| `exactBloodTypeMultiplier` | 1.10 | Exact ABO and Rh research match. |
| `sameRhMultiplier` | 0.95 | Different ABO, same Rh sign. |
| `rhMismatchMultiplier` | 0.65 | Rh/category mismatch. |
| `unknownHostMultiplier` | 0.85 | Host or vaccine lacks verified blood data. |

### `mutations`

`defenseMutation` selects the preferred mutation after failed treatment when compatible.

## Rh and research

ABO/Rh evidence comes from diagnostics and exact-strain documentation. It influences treatment instead of being decorative. Mutation tags can add special treatment semantics, including Rh-specific requirements. Missing data is not always impossible, but defaults penalize unknown and mismatch cases.

## Failure and defense evolution

Failed full/directed treatment can raise vaccine-defense risk based on strength and mismatch. Low-quality machine synthesis can mutate the source before injection. These are separate stages: laboratory failure changes research material; treatment failure changes the patient's infection.

## Directed actions

Definitions under `data/<namespace>/vaccine_actions` implement target changes. Bundled auto-opposite actions cover mutation, transmission, and symptom. Recipes map a target category to an output family and action ID.

## Exact-strain immunity

- Keyed to fingerprint, not pathogen family or public name.
- Renaming does not invalidate it.
- Same visible name does not make a different strain immune.
- Quality scales duration from about 50% to 150% of configured base.
- Inventory/effect tooltips show catalogued name and remaining time.
- Persists through relog until expiration.

Vaccine tooltips intentionally do not reveal public strain names.

## Visual identity

All vaccines share a syringe model with a tintable liquid layer. The strain/profile creates stable color variation, while each family has a distinct base palette. This avoids one texture per possible strain.

## Related pages

- [[CRISPR and Vaccine Maker]]
- [[Mutations]]
- [[Strain Catalogue]]

