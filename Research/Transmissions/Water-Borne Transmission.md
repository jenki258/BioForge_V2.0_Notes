# Water-Borne Transmission

#BioForge #BioForge_V0_54T #Transmission #water_borne #PlayerGuide #ModpackGuide #AddonDevelopment

> Definition ID: `bioforge:water_borne`. Behaviors: `bioforge:water_borne`.

## How it spreads

Compatible drinks, filled water bottles, and brewed potions can carry the strain to a consumer.

## Prevention

Avoid contaminated sources and use explicit sterile processing.

## Combined behavior

- Routes can coexist. Air + environmental settles room contamination onto surfaces; animal + food carries it through products; attack + blood strengthens injury transfer.
- Infectivity, incubation contagion, source state, immunity, resistance, PPE, and server route switches are checked before infection.

## Pack and addon notes

- Disable the built-in route through server config when it should not exist in a pack.
- JSON defines the route and references behavior IDs; Java addons register genuinely new executable behavior.

Related: [[Transmission System]], [[Containment and PPE]], [[Definition API]].

