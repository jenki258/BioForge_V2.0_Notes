# Pathogen Lifespan and Self-Destruction

#BioForge #BioForge_V0_54T #Mechanic #Lifecycle #Mutation #Cure #ModpackGuide

BioForge distinguishes a general strain lifespan from conditional self-destruction.

## Lifespan

A lifecycle profile may define a finite number of ticks. When that time expires the infection removes itself. A value of `-1` means no time-based expiry. This supports short-lived engineered strains, temporary outbreaks, or permanent diseases without inventing a fake symptom.

## Self-destruction mutation

[[Pyrolytic Self-Destruction]] is a mutation-level environmental reaction. While the host is on fire, it periodically rolls a configured chance to destroy the infection. Other addons can implement different condition-based self-destruction through registered mutation effect behavior.

## Design difference

- Lifespan is predictable profile state.
- Self-destruction is a conditional mutation behavior.
- Neither should be confused with a vaccine cure, immunity, or admin removal.

Related: [[Infection Lifecycle]], [[Mutation System]], [[Vaccines and Immunity]].

