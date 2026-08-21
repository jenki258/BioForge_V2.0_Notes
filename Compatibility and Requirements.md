# Compatibility and Requirements

#BioForge #BioForge_V2_0 #Compatibility #Installation #Server

## Supported runtime

| Component | Supported target |
|---|---|
| Minecraft | 1.20.1 |
| Mod loader | Forge 47.4.10 |
| Java | 17 |
| BioForge addon API | 3 |
| Sides | Client and dedicated server |

BioForge V2.0 is not a drop-in NeoForge, Fabric, or Quilt mod. Ports require loader-specific source work and must not be described as compatible until they pass their own client/server regression.

## Optional integrations

- **JEI 15.2.x:** optional at runtime and recommended. BioForge registers categories for its custom stations when JEI is present.
- **Curios 5.x:** optional. Wearable integration is enabled when available; BioForge must continue to work without Curios.
- **Datapacks:** supported for definitions, recipes, research pages, lifecycle profiles, natural infections, CRISPR data, and vaccine data.
- **Resource packs/addon resources:** required for addon-owned translations, textures, models, and icons.

## Multiplayer rules

Install the same BioForge version and Java addons on both sides. Server configuration and biological decisions are server-authoritative. Test datapack reloads on a dedicated server because an integrated single-player server does not expose every classloading or synchronization error.

## Compatibility principles

- BioForge recipes prefer tags where interchangeability is meaningful.
- Addons must use their own namespaces and stable IDs.
- Client-only rendering classes must never be loaded by dedicated-server code.
- Removing definitions that already exist in saved infections, reports, templates, or vaccines is a save migration, not a cosmetic change.
- Optional integrations must be tested both installed and absent.

