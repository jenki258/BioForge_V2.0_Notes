# Animal Transmission

#BioForge #BioForge_V0_54T #Transmission #animals #PlayerGuide #ModpackGuide #AddonDevelopment

> Definition ID: `bioforge:animals`. Behaviors: `bioforge:animals`.

## How it spreads

Infected animals can transfer infection into relevant drops such as meat and eggs, enabling a zoonotic product chain.

## Prevention

Control reservoirs, use food-chain tags, and sterilize products where a pack supplies a method.

## Combined behavior

- Routes can coexist. Air + environmental settles room contamination onto surfaces; animal + food carries it through products; attack + blood strengthens injury transfer.
- Infectivity, incubation contagion, source state, immunity, resistance, PPE, and server route switches are checked before infection.

## Pack and addon notes

- Disable the built-in route through server config when it should not exist in a pack.
- JSON defines the route and references behavior IDs; Java addons register genuinely new executable behavior.

Related: [[Transmission System]], [[Containment and PPE]], [[Definition API]].

