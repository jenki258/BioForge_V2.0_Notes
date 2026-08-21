# Contact-Based Transmission

#BioForge #BioForge_V2_0 #Build_V0_54T #Transmission #contact_based #PlayerGuide #ModpackGuide #AddonDevelopment

> Definition ID: `bioforge:contact_based`. Behaviors: `bioforge:contact_based`.

## How it spreads

The host can contaminate interacted, stepped-on, or nearby compatible blocks; later interaction, walking, or mining can expose another entity.

## Prevention

Protective Gloves block outward contamination; full HazCure blocks inward and outward; clean surfaces explicitly.

## Combined behavior

- Routes can coexist. Air + environmental settles room contamination onto surfaces; animal + food carries it through products; attack + blood strengthens injury transfer.
- Infectivity, incubation contagion, source state, immunity, resistance, PPE, and server route switches are checked before infection.

## Pack and addon notes

- Disable the built-in route through server config when it should not exist in a pack.
- JSON defines the route and references behavior IDs; Java addons register genuinely new executable behavior.

Related: [[Transmission System]], [[Containment and PPE]], [[Definition API]].

