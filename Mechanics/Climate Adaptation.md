# Climate Adaptation

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #Climate #Mutation #Infection #ModpackGuide #AddonDevelopment

Climate adaptation lets an infection respond to sustained hot or cold environments instead of treating biome temperature as cosmetic.

## How it works

1. The lifecycle profile defines adaptation speed and points gained per second.
2. A host in a hostile hot or cold climate accumulates the corresponding points.
3. Reaching the hot threshold grants [[Heat Adaptation]]; reaching the cold threshold grants [[Cold Adaptation]].
4. A strain that obtains both can progress to [[Thermal Homeostasis]].
5. Adapted strains no longer suffer the same lifecycle instability at that extreme.

This selection pressure is separate from the host-facing fever/hypothermia symptoms and from the wearable Ice/Magma Bag protection.

## Data and addons

Profiles choose thresholds and mutation IDs. An addon may register another lifecycle definition or mutations with compatible tags, but it must keep server lifecycle state authoritative.

Related: [[Infection Lifecycle API]], [[Thermal Instability]], [[Ice Bag Harness]], [[Magma Bag Harness]].

