# Surface Contamination

#BioForge #BioForge_V0_54T #Mechanic #Contact #Environmental #WorldData #PlayerGuide #ModpackGuide

Contact and environmental strains can persist on ordinary block positions without replacing their block state. The contamination is hidden server world data.

## Creation

An infected entity can contaminate blocks by interacting, walking, or shedding. Airborne/environmental combinations can settle concentrated air onto nearby surfaces; secretion and persistence mutations increase the effect.

## Exposure

Another living entity can be exposed when it steps on, interacts with, or breaks a contaminated block. PPE and route switches are checked before infection.

## Lifetime and cleanup

Contamination weakens through age, weather/contact logic, and explicit cleaning. Decontamination Flasks and the area command remove it; the Air Vent intentionally affects only airborne data.

## Performance

Only contaminated positions are stored. Expiry, bounded scans, per-chunk indexing, and cleanup keep the system from iterating every block in the world.

Related: [[Contact-Based Transmission]], [[Environmental Transmission]], [[Area Contamination Scanner]], [[Decontamination Flask]].

