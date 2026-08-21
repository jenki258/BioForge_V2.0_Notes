# Air Vent

#BioForge #BioForge_V2_0 #Build_V0_54T #Block #Containment #Airborne #PlayerGuide #ModpackGuide #AddonDevelopment

> Registry ID: `bioforge:air_vent`.

## Purpose

The Air Vent is a passive clean-air block. Once placed, it registers itself with the server and removes `AIR_BORNE` contamination once per second within a spherical radius of 10 blocks.

## Behavior

- No fuel, filter inventory, GUI, or redstone pulse is required in V0.54T.
- Positions inside the radius are treated as protected from new airborne reservoirs while the vent remains loaded and valid.
- Existing airborne contamination is repeatedly cleaned; contact or environmental contamination is not removed.
- The active-vent cache is rebuilt through block placement/ticks and cleared safely when the block or server is removed.

## Gameplay

Use a vent in laboratories, wards, entrances, and other rooms where persistent airborne exposure would make research impossible. It complements a Medical Mask and HazCure suit but does not clean tools, surfaces, food, water, or infected entities.

## Obtaining

Its shaped recipe combines Black Steel Plates, a Sterile Filter, and an Electronic Control Unit. The exact tag-compatible layout is visible in JEI and the Research Tablet.

## Pack notes

The current radius is the implementation constant `10`. Addons that need another type of passive field should register their own behavior rather than changing stored contamination data from the client.

Related: [[Airborne Rooms and Reservoirs]], [[Surface Contamination]], [[Decontamination Flask]].

