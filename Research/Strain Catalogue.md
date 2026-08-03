# Strain Catalogue

The catalogue gives an infection a stable research identity and optional public name without exposing every internal parameter.

## Fingerprint versus name

- Fingerprint: deterministic identity used for reports, vaccines, cultures, and immunity.
- Public name: readable player-submitted catalogue label.

Renaming does not change the fingerprint. Two strains do not become identical because players give them the same label.

## First discovery

When an uncatalogued strain enters the eligible discovery path, the naming GUI opens automatically for the first researcher/host. The player can submit a name or choose Later.

The server validates that the player still owns the pending discovery, the fingerprint is valid and unnamed, the name follows rules, and no other player already won the first-name race. Only the first accepted submission becomes the initial name.

## Moderation

Operators can inspect the current strain, list catalogue entries, and rename by fingerprint. This is necessary because public player names may be inappropriate. Admin renaming changes presentation, not biological identity. See [[BioForge Command Reference]].

## Disclosure policy

Names may appear on:

- Catalogued Live Culture Vials
- Sufficiently complete Medical Reports
- Inventory immunity entries and effect tooltip
- Administrative output

Names stay absent from:

- Vaccine tooltips
- Gene Imprints
- CRISPR Notes
- Incomplete raw samples

The Live Culture Vial tooltip communicates filled/catalogued status and directs the player to lab analysis. It does not dump raw pathogen, transmission, symptom, and mutation data.

## Persistence and security

- Catalogue data is server/world-owned.
- Naming packets are untrusted requests.
- Fingerprints remain the matching authority.
- Relog preserves catalogue entries and intended pending-prompt behavior.

## Related pages

- [[Integrated Gameplay Loop]]
- [[Vaccines and Immunity]]
- [[Testing Checklist]]

