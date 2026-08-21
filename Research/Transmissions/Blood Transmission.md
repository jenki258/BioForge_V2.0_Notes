# Blood Transmission

#BioForge #BioForge_V2_0 #Build_V0_54T #Transmission #blood #PlayerGuide #ModpackGuide #AddonDevelopment

> Definition ID: `bioforge:blood`. Behaviors: `bioforge:blood`.

## How it spreads

Blood samples, contaminated needles/syringes, injection, and compatible wounds can carry the exact strain.

## Prevention

Use sterile tools, clean empty equipment, respect blood compatibility, and wear full HazCure against syringes.

## Combined behavior

- Routes can coexist. Air + environmental settles room contamination onto surfaces; animal + food carries it through products; attack + blood strengthens injury transfer.
- Infectivity, incubation contagion, source state, immunity, resistance, PPE, and server route switches are checked before infection.

## Pack and addon notes

- Disable the built-in route through server config when it should not exist in a pack.
- JSON defines the route and references behavior IDs; Java addons register genuinely new executable behavior.

Related: [[Transmission System]], [[Containment and PPE]], [[Definition API]].

