# Performance and Persistence

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #Performance #Persistence #Server #ModpackGuide

BioForge's expensive systems are server-side, bounded, indexed, and event-driven where possible.

Airborne room scans use configured radius/volume limits and connectivity caches. Surface contamination stores only active positions with expiry and per-chunk lookup. Scanners tick every 10 ticks, Air Vents every 20, mutation effects use explicit intervals/chances, and natural infection checks do not scan the whole world each tick.

Entity infection, lifecycle, blood, immunity, resistance, knowledge, catalogue, and Research Tablet progress persist across save/relog. World caches are cleared on server stop and rebuild from valid loaded state.

Pack authors should avoid extreme colony radius/capacity, one-tick addon effects, unbounded room scans, or thousands of always-loaded scanners. Use the stress-test commands before shipping a pack.
