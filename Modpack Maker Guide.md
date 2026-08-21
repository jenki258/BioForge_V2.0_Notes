# Modpack Maker Guide

#BioForge #BioForge_V2_0 #Build_V0_54T #ModpackGuide #Configuration #Datapack #Compatibility

BioForge can act as a standalone progression mod or as a configurable disease platform. Packs can replace recipes, tune server balance, disable built-in routes/symptoms/mutations, add data-driven strains, and integrate other mods through tags.

## Safe customization order

1. Start with `serverconfig/bioforge-server.toml` for world-specific balance.
2. Override crafting and machine recipes through a datapack.
3. Extend BioForge ingredient, equipment, entity, food, crop, and block tags for compatibility.
4. Add or replace pathogens, transmissions, symptoms, mutations, lifecycles, natural infections, microscope mappings, and Research Tablet pages.
5. Use a Java addon only when new executable behavior is required.

## Pack-facing systems

- [[Server Configuration]] documents route switches, symptom and mutation switches, contamination values, vaccines, blood compatibility, and room scanning.
- [[Recipe and Tag Compatibility]] explains why BioForge recipes use tags and how another mod can provide equivalent inputs.
- [[Datapack Definitions]] lists every reloadable data directory and stable-ID rule.
- [[Natural Infections and Wild Hosts]] controls which entities can begin with which strains.
- [[Research Tablet Progression]] supports JSON pages and recipe references for addon content.
- [[Testing and Validation]] covers `/reload`, validation, stress tests, and test sample commands.
- [[Localization and Translation]] documents bundled locales and the language resources expected from addon content.

## Balance philosophy

The default progression is intentionally long but should remain readable: basic diagnosis comes before heavy industry, chemistry unlocks sterile research, research unlocks vaccines, and containment reduces the cost of mistakes. Avoid making every failure lethal; BioForge is most interesting when players can diagnose, respond, and learn from an outbreak.

## Compatibility rules

- Preserve registry and definition IDs after a world has stored them.
- Prefer tags over hard-coded external item IDs.
- Disable a built-in feature through its supported switch instead of leaving broken references in custom strains.
- Test both single-player and dedicated-server reloads.
- Back up worlds before replacing lifecycle or mutation definitions.

For complete schemas, continue with [[BioForge addon creation guide]] or [[Addon Developer Guide]].
