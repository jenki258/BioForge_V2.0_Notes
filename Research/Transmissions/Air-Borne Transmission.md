# Air-Borne Transmission

#BioForge #BioForge_V0_54T #Transmission #air_borne #PlayerGuide #ModpackGuide #AddonDevelopment

> Definition ID: `bioforge:air_borne`. Behaviors: `bioforge:air_borne`.

## How it spreads

Infected hosts shed into connected room air. Walls and closed passages block connectivity; reservoirs accumulate and decay.

## Prevention

Medical Mask blocks outward and reduces inward exposure; HazCure blocks both; Air Vent and decontamination clean reservoirs.

## Combined behavior

- Routes can coexist. Air + environmental settles room contamination onto surfaces; animal + food carries it through products; attack + blood strengthens injury transfer.
- Infectivity, incubation contagion, source state, immunity, resistance, PPE, and server route switches are checked before infection.

## Pack and addon notes

- Disable the built-in route through server config when it should not exist in a pack.
- JSON defines the route and references behavior IDs; Java addons register genuinely new executable behavior.

Related: [[Transmission System]], [[Containment and PPE]], [[Definition API]].

