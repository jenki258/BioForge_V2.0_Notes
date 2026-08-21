# Infection Lifecycle

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #Infection #Lifecycle #ModpackGuide #AddonDevelopment

Every strain can point to an infection lifecycle profile. The profile governs time-dependent behavior that should not be encoded as a symptom or one-off mutation.

## Lifecycle phases and values

- **Incubation:** delays symptom and mutation runtime until enough lifecycle progress has accumulated.
- **Climate rate:** hostile temperatures can slow or alter incubation according to the profile.
- **Adaptation points:** exposure to hot/cold climates accumulates independent selection pressure.
- **Adaptation thresholds:** grant heat, cold, or dual thermal mutations when reached.
- **Lifespan:** removes a finite strain after its time-to-live, or remains infinite at `-1`.
- **Infectivity:** scales establishment pressure.
- **Cure resistance:** reduces treatment reliability.
- **Contagious during incubation:** optionally allows spread before symptoms activate.

## Bundled default

The default profile uses 6000 ticks of incubation, 0.35 adaptation speed, 0.35 hostile-climate incubation rate, 100 points per thermal adaptation threshold, infinite lifespan, infectivity 1.0, cure resistance 0.05, and no contagiousness during incubation. These are data defaults, not promises that every custom strain uses them.

## Storage

Lifecycle progress is saved with the infection and survives relogging. Reloadable definitions should keep profile IDs stable so saved strains continue resolving.

Related: [[Incubation Period]], [[Climate Adaptation]], [[Pathogen Lifespan and Self-Destruction]], [[Infection Lifecycle API]].

