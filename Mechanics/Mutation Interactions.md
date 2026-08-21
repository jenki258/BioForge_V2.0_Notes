# Mutation Interactions

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #Mutation #Interaction #EmergentGameplay #AddonDevelopment

Mutations can modify one another so a strain is more than a list of independent potion effects.

## Interaction actions

- Add extra effects when all/any partners are present.
- Modify parameters on a matching continuous effect.
- Suppress an owned effect.
- Grant a compound mutation.
- Remove or replace an incompatible/lower-tier mutation.

## Bundled examples

- Hypervirulence amplifies Necrotic Fever's weakness.
- Respiratory Shedding plus Spore Cloud increases strain strength.
- Hypervirulence plus Vaccine Defense grants Reinforced Vaccine Defense.
- Grass Eater removes Grass Dependency.
- Self Respiration removes Amphibious Fatigue.
- Poison/Honey resistance removes Poison.
- Tier II/III simple effects replace their lower tier.
- Zoonotic Adaptation strengthens Gastrointestinal Shedding's food chain.

Interactions belong in JSON definitions rather than an ever-growing set of hard-coded pair checks. Addon IDs must stay stable because saved strains may already contain them.

Related: [[Mutation Catalogue]], [[Mutation API]], [[Adaptive Vaccine Defense]].

