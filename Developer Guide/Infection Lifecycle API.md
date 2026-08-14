# Infection Lifecycle API

#BioForge #BioForge_V0_54T #JavaAPI #JSONAPI #Lifecycle #NaturalInfection #AddonDevelopment

Lifecycle definitions control incubation ticks, climate rates, adaptation points/thresholds/mutations, lifespan, infectivity, cure resistance, and incubation contagiousness.

Natural-strain definitions combine pathogen, routes, symptoms, mutations, rare mutations, and a lifecycle profile. Natural rules bind weighted strains to entity lists and spawn chance.

Use JSON under `infection_lifecycle` and `natural_infections`, or register Java definitions before the manager finalizes reload. Saved entities retain lifecycle profile IDs and progress; renaming an ID breaks that relationship.
