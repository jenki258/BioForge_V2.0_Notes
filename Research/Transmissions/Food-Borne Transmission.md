# Food-Borne Transmission

#BioForge #BioForge_V0_54T #Transmission #food_borne #PlayerGuide #ModpackGuide #AddonDevelopment

> Definition ID: `bioforge:food_borne`. Behaviors: `bioforge:food_borne`.

## How it spreads

Strain data persists in edible crops, animal products, and compatible crafted foods and exposes the consumer.

## Prevention

Sterilize through explicit recipes; ordinary crafting does not guarantee safety.

## Combined behavior

- Routes can coexist. Air + environmental settles room contamination onto surfaces; animal + food carries it through products; attack + blood strengthens injury transfer.
- Infectivity, incubation contagion, source state, immunity, resistance, PPE, and server route switches are checked before infection.

## Pack and addon notes

- Disable the built-in route through server config when it should not exist in a pack.
- JSON defines the route and references behavior IDs; Java addons register genuinely new executable behavior.

Related: [[Transmission System]], [[Containment and PPE]], [[Definition API]].

