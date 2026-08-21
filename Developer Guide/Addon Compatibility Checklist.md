# Addon Compatibility Checklist

#BioForge #BioForge_V2_0 #Build_V0_54T #AddonDevelopment #Compatibility #Testing

- Target Minecraft 1.20.1, Forge 47.4.10, Java 17, and BioForge API v3.
- Use your namespace and stable IDs.
- Register Java behavior before JSON reload.
- Keep server/client classes separated.
- Use tags for cross-mod ingredients/equipment/entities.
- Use biological-data helpers rather than private NBT.
- Validate every datapack and test dedicated server reload.
- Test persistence across relog/restart.
- Expose recipes to JEI and Research Tablet where supported.
- Provide language keys and resources without replacing BioForge assets unnecessarily.
- Avoid one-tick heavy scans and unbounded areas.
- Back up worlds before definition migrations.

The exhaustive guide is [[BioForge addon creation guide]].
