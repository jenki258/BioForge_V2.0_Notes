# Transmission System

#BioForge #BioForge_V0_54T #Mechanic #Transmission #Contamination #PlayerGuide #ModpackGuide #AddonDevelopment

Transmission routes are executable behaviors, not tooltip labels. A strain may carry several routes, and combinations can reinforce one another.

## Bundled routes

- [[Air-Borne Transmission]]
- [[Contact-Based Transmission]]
- [[Environmental Transmission]]
- [[Food-Borne Transmission]]
- [[Water-Borne Transmission]]
- [[Animal Transmission]]
- [[Blood Transmission]]
- [[Attack-Based Transmission]]

## Common validation

Before an exposure can infect a target, the server considers route enablement, incubation contagion, source/target state, infectivity, distance or item context, PPE, exact-strain immunity, resistance pills, full infection invulnerability, and any custom transmission behavior.

## Combined examples

- Air-borne plus environmental can settle a concentrated room onto surfaces.
- Contact plus environmental creates longer-lived contaminated blocks.
- Attack plus blood strengthens injury-based transfer.
- Animals plus food-borne carries infection through meat/eggs and later crafting.
- Secretion and respiratory mutations increase the relevant shedding behavior.

Definitions live in `bioforge_definitions/transmissions`; Java addons register new behavior IDs through the public behavior registry.

Related: [[Transmission Catalogue]], [[Containment and PPE]], [[Definition API]].

