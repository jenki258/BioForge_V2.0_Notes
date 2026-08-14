# Airborne Rooms and Reservoirs

#BioForge #BioForge_V0_54T #Mechanic #Airborne #RoomScan #Performance #PlayerGuide #ModpackGuide

Airborne exposure uses bounded room connectivity rather than spreading straight through walls.

## Room logic

- Solid walls and closed passages stop connectivity.
- Open doors and other open cells connect spaces.
- Sealed rooms retain concentration.
- Large open or outdoor spaces dilute infection pressure.
- Exposure accumulates over time instead of using one instant through-wall roll.

The scan is bounded by configured radius/volume limits and caches work where possible to protect server performance.

## Reservoir lifetime

Airborne reservoirs decay over time; the default design target is roughly 30 minutes when not replenished. An infected host, route interaction, or environmental mutation can renew them.

## Countermeasures

- Medical Mask: blocks outward spread and reduces incoming exposure by 80%.
- Full HazCure: blocks incoming and outgoing airborne infection.
- Air Vent: passively prevents/cleans airborne reservoirs within 10 blocks.
- Decontamination Flask and commands: active area cleanup.

Related: [[Air-Borne Transmission]], [[Air Vent]], [[Decontamination]], [[Performance and Persistence]].

