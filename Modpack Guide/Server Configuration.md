# Server Configuration

#BioForge #BioForge_V2_0 #Build_V0_54T #ServerConfig #Balance #ModpackGuide

World balance lives in `serverconfig/bioforge-server.toml`, so different saves can use different disease rules.

Config groups cover master/per-route spreading, master/per-symptom behavior, master/per-built-in-mutation enablement, airborne room limits, exposure chances, contamination lifetime, cleaning radius, blood compatibility, vaccine cure/quality/immunity scaling, pill/suppression duration, infection strength, and related balance.

Disabling a built-in feature filters it from generated strains, commands, runtime, machines, serialization, and microscope output where applicable. Addon definitions retain their own enabled state unless the relevant global master is disabled.

Edit while the server is stopped where Forge requires it, retain backups, and test changes with validation/regression commands.
