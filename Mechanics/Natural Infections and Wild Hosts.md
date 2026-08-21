# Natural Infections and Wild Hosts

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #NaturalInfection #Worldgen #Datapack #ModpackGuide #AddonDevelopment

Natural infection rules allow mobs to enter the world with believable reservoir strains. The system is data-driven and does not require every infection to originate from a player command.

## Bundled reservoirs

- Pigs and hoglins can carry a porcine respiratory virus.
- Cows and mooshrooms can carry a bovine enteric bacterium.
- Chickens and parrots can carry an avian surface virus.
- Zombies, husks, drowned, and zombie villagers carry the Zombie Necrotic Virus.

Wild rules define entity IDs, chance, weighted strain list, pathogen, routes, symptoms, base mutations, rare blood-only mutations, and lifecycle profile.

## Rare wild mutations

Porcine Receptor Shift, Bovine Serum Stability, and Avian Egg Tropism are intended to be recovered from infected host blood rather than ordinary weighted mutation selection. This makes wildlife sampling a research route instead of decorative ambience.

## Persistence and products

Animal/food routes can transfer the strain into drops such as meat or eggs and into compatible crafted results. A natural host therefore matters after death unless the product is sterilized or otherwise cleaned by supported gameplay.

## Extension

Use `data/<namespace>/natural_infections/*.json` or the public Java lifecycle/natural-infection registration API. Keep strain IDs stable.

Related: [[Zombie Necrotic Virus]], [[Contaminated Food, Water, and Animal Products]], [[Infection Lifecycle API]].

