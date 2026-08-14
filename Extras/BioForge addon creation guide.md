
#Addons
[[BioForge V2 — addon and datapack architecture]]
This guide explains the two supported ways to extend BioForge:

1. a JSON datapack for definitions, balance, recipes, research pages and content assembled from existing mechanics;
2. a compiled Forge addon for new executable behavior, custom machine operations and Java-registered content.

The recommended approach is hybrid: implement only genuinely new behavior in Java and keep the actual pathogens, mutations, recipes and balance in JSON. That lets modpack authors override your content without recompiling your addon.

## Supported environment

This document targets:

- Minecraft 1.20.1;
- Forge 47.4.10;
- Java 17;
- BioForge 2.0 test builds;
- `BioForgeAddonApi.API_VERSION == 3`.

BioForge is still under active test development. Check `BioForgeAddonApi.API_VERSION` when updating an addon and test against the exact BioForge build used by the pack.

## JSON or Java?

| Requirement | JSON datapack | Java addon |
|---|---:|---:|
| Add pathogens, symptoms and transmission definitions | Yes | Yes |
| Add mutations using existing effect types | Yes | Yes |
| Add lifecycle profiles and natural infections | Yes | Yes |
| Add CRISPR, vaccine and correction data | Yes | Yes |
| Add machine, Microscope and Research Tablet content | Yes | Yes |
| Change values with `/reload` | Yes | No |
| Add a completely new tick behavior | No | Yes |
| Add a new mutation effect implementation | No | Yes |
| Add a new Vaccine Maker operation | No | Yes |
| Add custom Vaccine Maker page logic/rendering | No | Yes |

JSON can compose built-in behavior. Java is required when the desired mechanic does not already exist.

## Rules that apply to both formats

- Give every definition a namespaced ID belonging to your project, such as `crystalmed:crystal_plague`.
- Never rename an ID after players have saved strains, templates, vaccines or infections containing it.
- Do not use the `bioforge` namespace for addon content.
- BioForge's legacy built-in mutation IDs, such as `climbing` and `weak_grip`, are intentionally unnamespaced; new addon mutation IDs should still be namespaced.
- Register Java behavior before loading a definition that references that behavior.
- Keep values finite and inside the documented range.
- Put display strings in language files when distributing a resource pack or Java addon.
- Treat server-side infection data as authoritative.
- Test both single-player and a dedicated server.
- Back up an existing world before changing saved biological IDs.

# Part I: JSON/datapack addons

## 1. Starter datapack structure

Create a folder or ZIP with this structure:

```text
CrystalMedicine/
├─ pack.mcmeta
└─ data/
   └─ crystalmed/
      ├─ bioforge_definitions/
      │  ├─ pathogens/
      │  ├─ symptoms/
      │  └─ transmissions/
      ├─ mutations/
      ├─ infection_lifecycle/
      ├─ natural_infections/
      ├─ crispr/
      │  ├─ guide_profiles/
      │  ├─ cas_modules/
      │  └─ assays/
      ├─ vaccine_actions/
      ├─ vaccine_correction_profiles/
      ├─ vaccine_maker/
      ├─ laboratory_processing/
      ├─ centrifuge/
      ├─ decalcification/
      ├─ incubator/
      │  └─ catalyst_mappings/
      ├─ microscope/
      ├─ research_journal/
      └─ recipes/
```

For Minecraft 1.20.1, a minimal `pack.mcmeta` is:

```json
{
  "pack": {
    "pack_format": 15,
    "description": "Crystal Medicine - BioForge addon data"
  }
}
```

Install the folder/ZIP into `saves/<world>/datapacks/`, enter the world, run `/reload`, then run `/bioforge validate`.

## 2. Core definition format

Pathogens, symptoms and transmissions live below `data/<namespace>/bioforge_definitions/`.

Common fields are:

| Field | Meaning |
|---|---|
| `schema_version` | Currently `1` |
| `id` | Stable namespaced definition ID |
| `priority` | Higher-priority entry wins when replacement is allowed |
| `replace` | Allows this entry to replace an existing definition |
| `enabled` | `false` disables the definition supplied by this entry |
| `aliases` | Old IDs that should resolve to this definition |

A file can contain one object or a `definitions` array. The directory determines whether entries are pathogens, symptoms or transmissions.

### Custom symptom

`data/crystalmed/bioforge_definitions/symptoms/crystal_load.json`

```json
{
  "schema_version": 1,
  "id": "crystalmed:crystal_load",
  "value_type": "float",
  "default": 0.0,
  "min": 0.0,
  "max": 1.0
}
```

Supported value types are `boolean`, `integer`, `float`, `string` and `enum`. Enum definitions also require `allowed_values`.

A JSON-only symptom is a typed piece of strain data. It can be displayed, corrected by a vaccine and modified by mutations. To make it execute a completely new mechanic every tick, connect it to a Java `SymptomBehavior`.

### Custom transmission definition

`data/crystalmed/bioforge_definitions/transmissions/crystal_contact.json`

```json
{
  "schema_version": 1,
  "id": "crystalmed:crystal_contact",
  "translation_key": "infection_type.crystalmed.crystal_contact",
  "behaviors": ["bioforge:contact_based"]
}
```

This creates a separate route ID while reusing BioForge contact behavior. Existing reusable behavior IDs include the built-in transmission IDs such as `bioforge:air_borne`, `bioforge:contact_based`, `bioforge:food_borne`, `bioforge:water_borne`, `bioforge:attack_based`, `bioforge:animals`, `bioforge:blood` and `bioforge:environmental`.

### Custom pathogen

`data/crystalmed/bioforge_definitions/pathogens/crystal_plague.json`

```json
{
  "schema_version": 1,
  "id": "crystalmed:crystal_plague",
  "translation_key": "pathogen.crystalmed.crystal_plague",
  "color": "#72d9ff",
  "environmental": true,
  "allowed_transmissions": [
    "bioforge:air_borne",
    "crystalmed:crystal_contact",
    "bioforge:blood"
  ],
  "default_symptoms": {
    "crystalmed:crystal_load": {"min": 0.15, "max": 0.55},
    "bioforge:infection_strength": {"min": 0.35, "max": 0.75},
    "bioforge:oxygen_saturation": {"min": 0.80, "max": 0.94},
    "bioforge:microscope_visibility": "MEDIUM"
  }
}
```

Fixed defaults can be a direct value. Randomized defaults use `{ "min": ..., "max": ... }`. Every referenced symptom and transmission must exist or BioForge rejects the complete core-definition reload and keeps the previous valid snapshot.

## 3. Mutations

Mutation files live in `data/<namespace>/mutations/`. A file can contain one definition or a `definitions` array.

`data/crystalmed/mutations/crystal_skin.json`

```json
{
  "id": "crystalmed:crystal_skin",
  "name": "Crystal Skin",
  "description": "Mineral growth reinforces tissue but slows movement",
  "pathogens": ["crystalmed:crystal_plague", "bioforge:universal"],
  "rarity": "rare",
  "weight": 14,
  "tags": ["beneficial", "physical", "vaccine_target"],
  "effects": [
    {
      "type": "attribute_modifier",
      "target": "minecraft:generic.armor",
      "operation": "add",
      "amount": 3.0,
      "trigger": "continuous",
      "interval": 80
    },
    {
      "type": "potion_effect",
      "target": "minecraft:slowness",
      "duration": 100,
      "amplifier": 0,
      "chance": 0.20,
      "trigger": "continuous",
      "interval": 100
    },
    {
      "type": "spawn_particle",
      "target": "minecraft:end_rod",
      "count": 3,
      "spread": 0.25,
      "chance": 0.15,
      "trigger": "continuous",
      "interval": 60
    }
  ]
}
```

Built-in effect types:

- `modify_symptom`;
- `set_symptom`;
- `add_infection_type`;
- `remove_infection_type`;
- `potion_effect`;
- `spawn_particle`;
- `attribute_modifier`;
- `damage`;
- `heal`;
- `exhaustion`;
- `ignite`;
- `play_sound`.

BioForge also supplies specialized namespaced effects including `bioforge:wall_climb`, `bioforge:grass_dependency`, `bioforge:respiration`, `bioforge:camouflage`, `bioforge:clear_effect`, `bioforge:light_reaction` and `bioforge:self_destruct`.

Triggers are `apply`, `continuous` and `remove`. Common effect parameters include `value`, `amount`, `chance`, `interval`, `duration`, `amplifier`, `count`, `spread`, `speed`, `volume`, `pitch` and `ticks`.

### Requirements, conflicts and tiers

```json
{
  "id": "crystalmed:crystal_skin_ii",
  "name": "Crystal Skin II",
  "pathogens": ["crystalmed:crystal_plague"],
  "rarity": "epic",
  "weight": 4,
  "requires": ["crystalmed:crystal_skin"],
  "conflicts": ["weak_grip"],
  "tags": ["beneficial", "tier_2"],
  "effects": [
    {
      "type": "attribute_modifier",
      "target": "minecraft:generic.armor",
      "operation": "add",
      "amount": 6.0,
      "trigger": "continuous"
    }
  ],
  "interactions": [
    {
      "id": "upgrade_crystal_skin",
      "with": "crystalmed:crystal_skin",
      "remove_mutations": ["crystalmed:crystal_skin"]
    }
  ]
}
```

Interactions support `with`, `mode` (`all` or `any`), additional `effects`, `grant_mutations`, `remove_mutations`, `force_grants` and effect modifiers. Use `weight: 0` for an interaction-only result that should never be selected randomly.

## 4. Infection lifecycle profiles

Lifecycle profiles live in `data/<namespace>/infection_lifecycle/`.

`data/crystalmed/infection_lifecycle/slow_crystal.json`

```json
{
  "id": "crystalmed:slow_crystal",
  "incubation_ticks": 12000,
  "adaptation_speed": 0.20,
  "hostile_climate_incubation_rate": 0.40,
  "adaptation_points_per_second": 0.25,
  "hot_adaptation_threshold": 140.0,
  "cold_adaptation_threshold": 140.0,
  "hot_adaptation_mutation": "heat_adaptation",
  "cold_adaptation_mutation": "cold_adaptation",
  "dual_adaptation_mutation": "thermal_homeostasis",
  "lifespan_ticks": 72000,
  "infectivity": 0.75,
  "cure_resistance": 0.20,
  "contagious_during_incubation": false
}
```

`lifespan_ticks: -1` means the infection does not expire naturally. Twenty ticks equal one second.

## 5. Natural strains and mob infection rules

Natural infection files live in `data/<namespace>/natural_infections/`.

```json
{
  "strains": [
    {
      "id": "crystalmed:underground_crystal_plague",
      "pathogen": "crystalmed:crystal_plague",
      "transmissions": ["bioforge:contact_based", "bioforge:attack_based"],
      "symptoms": {
        "bioforge:infection_strength": "0.62",
        "crystalmed:crystal_load": "0.45",
        "bioforge:microscope_visibility": "LOW"
      },
      "mutations": ["crystalmed:crystal_skin"],
      "rare_mutations": [
        {"mutation": "climbing", "chance": 0.03}
      ],
      "lifecycle_profile": "crystalmed:slow_crystal"
    }
  ],
  "rules": [
    {
      "id": "crystalmed:cave_spider_reservoir",
      "entities": ["minecraft:cave_spider"],
      "chance": 0.18,
      "strains": [
        {"strain": "crystalmed:underground_crystal_plague", "weight": 1}
      ]
    }
  ]
}
```

`chance` is from `0.0` to `1.0`. Weighted strain entries let one entity rule select from several natural strains.

## 6. Laboratory machine recipes

Files in `data/<namespace>/laboratory_processing/` support these station IDs:

- `barrel_press`: up to four inputs, one output;
- `chemical_synthesizer`: up to three inputs, one output;
- `pharma_mixer`: up to five inputs, product plus mandatory waste;
- `sterilization_chamber`: exactly one input and in-place processing.

```json
{
  "station": "chemical_synthesizer",
  "ingredients": [
    {"tag": "forge:gems/amethyst"},
    {"item": "minecraft:glowstone_dust"},
    {"tag": "forge:dusts/redstone"}
  ],
  "output": "crystalmed:crystal_reagent",
  "count": 2,
  "copy_nbt": false,
  "processing_time": 180
}
```

A Pharma Mixer recipe additionally uses `waste` and optional `waste_count`.

A datapack cannot register a brand-new Minecraft item or block. Outputs such as `crystalmed:crystal_reagent` must already be supplied by a companion Java mod; a pure datapack must use items that already exist.

## 7. Incubator recipes

Incubator recipes use the vanilla recipe directory because they have a registered recipe serializer.

`data/crystalmed/recipes/incubator/grow_crystal_sample.json`

```json
{
  "type": "bioforge:incubator",
  "primary_input": "#bioforge:ingredients/bioforge/catalyst_vial",
  "secondary_input": "#bioforge:ingredients/bioforge/nutrient_medium",
  "output": "bioforge:virus_sample",
  "operation": "generate_strain",
  "processing_time": 240,
  "primary_item_cost": 0,
  "catalyst_charge_cost": 1
}
```

Ingredient strings accept an item ID, `#tag` or `*` wildcard. A wildcard primary input requires a concrete `jei_input`. Supported operations are defined by BioForge's current `IncubatorOperation`; copy a bundled recipe matching the operation you need.

## 8. Centrifuge recipes

Files live in `data/<namespace>/centrifuge/`.

```json
{
  "input": "#crystalmed:centrifuge_inputs/crystal_blood",
  "outputs": [
    {"item": "crystalmed:crystal_plasma", "weight": 3},
    {"item": "bioforge:cell_pellet", "weight": 1}
  ],
  "copy_blood_data": true,
  "copy_infection": true,
  "copy_nbt": false,
  "processing_time": 140
}
```

Use either `output` for one deterministic output or `outputs` for weighted alternatives.

## 9. Microscope mappings

Microscope files live in `data/<namespace>/microscope/`. They map an item to calibration sliders and visible entries.

```json
{
  "items": {
    "crystalmed:crystal_plasma": {
      "calibration": {
        "sliders": [
          {
            "name": "microscope.calibration.brightness",
            "target": 0.65,
            "range_min": 0.1,
            "range_max": 0.9,
            "random_target": true
          },
          {
            "name": "microscope.calibration.focus",
            "target": 0.75,
            "random_target": true
          }
        ]
      },
      "entries": [
        {
          "symptom": "crystalmed:crystal_load",
          "type": "float",
          "icon": "crystalmed:textures/gui/microscope/crystal_load.png",
          "display_percentage": true
        }
      ]
    }
  }
}
```

Entry types include `boolean`, `float` and `enum`. Entries can read strain values or NBT using `source`, `nbt_key` and `condition`. Custom textures and translated slider/symptom names must be supplied to clients through the addon resources or a resource pack.

## 10. Research Tablet pages

Pages live in `data/<namespace>/research_journal/`. The file path becomes the page ID.

`data/crystalmed/research_journal/crystal_plague.json`

```json
{
  "order": 800,
  "unlock_items": ["crystalmed:crystal_reagent"],
  "unlock_mode": "any",
  "recipes": [
    {"type": "laboratory", "id": "crystalmed:crystal_reagent"}
  ],
  "title": {
    "translate": "research.crystalmed.crystal_plague.title",
    "color": "dark_aqua",
    "bold": true
  },
  "content": [
    {
      "component": {
        "translate": "research.crystalmed.crystal_plague.intro",
        "color": "black"
      },
      "line_breaks": 2
    },
    {
      "component": {
        "text": "[Return to contents]",
        "color": "dark_aqua",
        "underlined": true
      },
      "link": "bioforge:contents",
      "line_breaks": 0
    }
  ]
}
```

Unlock requirements accept item IDs or `#item_tag` IDs. `unlock_mode` is `any` or `all`. Recipe references may be plain crafting recipe IDs or typed objects. Supported typed references include `crafting`, `laboratory` and `vaccine_maker`.

## 11. Other JSON systems

The fastest reliable workflow for these systems is to copy the closest bundled BioForge file and change its namespace, IDs and values:

| Directory | Content |
|---|---|
| `crispr/guide_profiles/` | Alphabet, three guide roles, salts and strain sources |
| `crispr/cas_modules/` | PAM, efficiency and pathogen/profile compatibility |
| `crispr/assays/` | Growth requirement, culture cost and numeric feedback |
| `vaccine_actions/` | Directed mutation/transmission/symptom behavior |
| `vaccine_correction_profiles/` | Correction families, pages, weights and assay rules |
| `vaccine_maker/` | Full, directed, random, pill, tablet and clone recipes |
| `decalcification/` | Decalcification conversions |
| `incubator/catalyst_mappings/` | Item-to-pathogen catalyst mappings |

The current CRISPR GUI requires exactly three guide roles, five cartridges per guide and four bases per cartridge. The alphabet may contain two or more unique characters.

## 12. JSON validation and reload behavior

Recommended test loop:

1. start with only one new definition;
2. run `/reload`;
3. run `/bioforge validate`;
4. inspect `latest.log` for your namespace;
5. inspect the definition with the relevant `/bioforge` command;
6. add recipes and cross-references only after the base definition loads.

Core pathogen/transmission/symptom reload is atomic. If one of those definitions is invalid, BioForge rejects that new set and keeps the previous valid snapshot. Other content loaders report and skip invalid entries, so always check the log after `/reload`.

# Part II: compiled Java addons

## 13. Create the Forge addon project

Use a normal Forge 1.20.1 MDK project with Java 17 and Forge 47.4.10. Place the current BioForge development or release JAR in your addon's `libs/` directory.

Example dependency in `build.gradle`:

```groovy
dependencies {
    minecraft "net.minecraftforge:forge:1.20.1-47.4.10"
    compileOnly fg.deobf(files("libs/BioForge-2.0.jar"))
    runtimeOnly fg.deobf(files("libs/BioForge-2.0.jar"))
}
```

Do not invent a Maven repository for BioForge until an official repository is published. A local JAR dependency is the reliable development setup.

Declare BioForge as a mandatory dependency in `META-INF/mods.toml`:

```toml
[[dependencies.crystalmed]]
modId="bioforge"
mandatory=true
versionRange="[2.0,)"
ordering="AFTER"
side="BOTH"
```

Replace `crystalmed` with your actual `modId`.

## 14. Registration timing

BioForge Java registries are frozen when the server starts. Register definitions and behaviors from your addon constructor or common setup, never after a world is already running.

Recommended order:

1. register custom behavior handlers;
2. register symptoms and transmissions using those handlers;
3. register pathogens;
4. register mutations and lifecycle profiles;
5. register natural strains/rules;
6. register recipes, pages and item-dependent mappings during common setup after addon items exist.

Duplicate IDs throw an exception. Java registrations do not change on `/reload`, but JSON entries can override matching Java mutation/page content where that loader explicitly supports datapack precedence.

## 15. Minimal addon entry point

```java
package com.example.crystalmed;

import com.google.gson.JsonObject;
import com.google.gson.JsonPrimitive;
import net.jenkimods.bioforge.api.BioForgeAddonApi;
import net.jenkimods.bioforge.api.definition.PathogenDefinition;
import net.jenkimods.bioforge.api.definition.SymptomDefinition;
import net.jenkimods.bioforge.mutation.MutationDefinition;
import net.minecraft.core.particles.ParticleTypes;
import net.minecraft.resources.ResourceLocation;
import net.minecraft.server.level.ServerLevel;
import net.minecraftforge.eventbus.api.IEventBus;
import net.minecraftforge.fml.common.Mod;
import net.minecraftforge.fml.event.lifecycle.FMLCommonSetupEvent;
import net.minecraftforge.fml.javafmlmod.FMLJavaModLoadingContext;

@Mod(CrystalMedicine.MOD_ID)
public final class CrystalMedicine {
    public static final String MOD_ID = "crystalmed";

    public CrystalMedicine(FMLJavaModLoadingContext context) {
        if (BioForgeAddonApi.API_VERSION < 3) {
            throw new IllegalStateException("Crystal Medicine requires BioForge API 3+");
        }

        registerBioForgeBehavior();
        registerBioForgeDefinitions();

        IEventBus modBus = context.getModEventBus();
        modBus.addListener(this::commonSetup);
    }

    private static ResourceLocation id(String path) {
        return ResourceLocation.fromNamespaceAndPath(MOD_ID, path);
    }

    private static ResourceLocation bioforge(String path) {
        return ResourceLocation.fromNamespaceAndPath("bioforge", path);
    }

    private static void registerBioForgeBehavior() {
        BioForgeAddonApi.registerMutationEffect(id("crystal_burst"), context -> {
            if (context.entity().level() instanceof ServerLevel level) {
                level.sendParticles(
                        ParticleTypes.END_ROD,
                        context.entity().getX(),
                        context.entity().getY() + 1.0,
                        context.entity().getZ(),
                        4,
                        0.25,
                        0.40,
                        0.25,
                        0.01
                );
            }
        });
    }

    private static void registerBioForgeDefinitions() {
        ResourceLocation crystalLoad = id("crystal_load");
        ResourceLocation crystalPlague = id("crystal_plague");

        BioForgeAddonApi.registerSymptom(
                SymptomDefinition.builder(
                                crystalLoad,
                                SymptomDefinition.ValueType.FLOAT)
                        .translationKey("microscope.symptom.crystalmed.crystal_load")
                        .defaultValue(new JsonPrimitive(0.0F))
                        .range(0.0, 1.0)
                        .build()
        );

        BioForgeAddonApi.registerPathogen(
                PathogenDefinition.builder(crystalPlague)
                        .translationKey("pathogen.crystalmed.crystal_plague")
                        .color(0x72D9FF)
                        .environmental(true)
                        .transmission(bioforge("air_borne"))
                        .transmission(bioforge("contact_based"))
                        .defaultSymptom(
                                crystalLoad,
                                new PathogenDefinition.DefaultSymptomValue(
                                        new JsonPrimitive(0.15F),
                                        new JsonPrimitive(0.55F)))
                        .build()
        );

        JsonObject parameters = new JsonObject();
        parameters.addProperty("interval", 60);
        parameters.addProperty("chance", 0.25F);

        MutationDefinition.Effect crystalBurst = new MutationDefinition.Effect(
                id("crystal_burst").toString(),
                "",
                "set",
                MutationDefinition.Trigger.CONTINUOUS,
                parameters
        );

        BioForgeAddonApi.registerMutation(
                new MutationDefinition.Builder()
                        .id("crystalmed:resonant_crystals")
                        .name("Resonant Crystals")
                        .description("The infected host periodically releases crystal light")
                        .pathogenId(crystalPlague)
                        .rarity("rare")
                        .weight(12)
                        .effect(crystalBurst)
                        .build()
        );
    }

    private void commonSetup(FMLCommonSetupEvent event) {
        event.enqueueWork(() -> {
            registerItemDependentBioForgeContent();
        });
    }

    private static void registerItemDependentBioForgeContent() {
    }
}
```

The empty item-dependent method is where you register Microscope mappings, catalyst mappings and recipes that refer to your addon `RegistryObject<Item>` values.

## 16. Custom symptom behavior

Register a handler, then attach its ID to the symptom definition:

```java
BioForgeAddonApi.registerSymptomBehavior(
        id("crystal_fatigue"),
        (level, entity, infection, definition, value) -> {
            if (!(value instanceof Number number)) return;
            if (number.floatValue() < 0.65F) return;
            if (level.getGameTime() % 80L != 0L) return;

            entity.setTicksFrozen(Math.min(
                    entity.getTicksRequiredToFreeze() + 20,
                    entity.getTicksFrozen() + 20));
        }
);

BioForgeAddonApi.registerSymptom(
        SymptomDefinition.builder(
                        id("crystal_load"),
                        SymptomDefinition.ValueType.FLOAT)
                .defaultValue(new JsonPrimitive(0.0F))
                .range(0.0, 1.0)
                .behavior(id("crystal_fatigue"))
                .build()
);
```

`SymptomBehavior.tick` is server-side and receives the level, infected entity, infection data, symptom definition and typed value.

## 17. Custom transmission behavior

```java
BioForgeAddonApi.registerTransmissionBehavior(
        id("crystal_dust"),
        (level, host, infection, transmissionId, definition) ->
                CrystalDustTransmission.tick(level, host, infection)
);
```

Then attach `crystalmed:crystal_dust` to a `TransmissionDefinition`. The addon implementation is responsible for target selection, protection checks and applying exposure safely. Reuse BioForge behavior through JSON when possible; a new Java transmission should exist only when its spreading model is genuinely different.

## 18. Java lifecycle and natural infection registration

```java
BioForgeAddonApi.registerInfectionLifecycle(
        new InfectionLifecycleDefinition(
                id("slow_crystal"),
                12000,
                0.20F,
                0.40F,
                0.25F,
                140.0F,
                140.0F,
                "heat_adaptation",
                "cold_adaptation",
                "thermal_homeostasis",
                72000,
                0.75F,
                0.20F,
                false
        )
);

BioForgeAddonApi.registerPathogenLifecycle(
        id("crystal_plague"),
        id("slow_crystal")
);
```

Natural infections use `NaturalStrainDefinition` and `NaturalInfectionRule`. JSON is generally easier for these records, but Java registration exists for addons that generate their definitions programmatically.

## 19. Java Research Tablet page

```java
BioForgeAddonApi.registerResearchJournalPage(
        ResearchJournalPageDefinition.builder(
                        id("crystal_plague"),
                        Component.translatable(
                                "research.crystalmed.crystal_plague.title"))
                .order(800)
                .unlockWith(id("crystal_reagent"))
                .text(Component.translatable(
                        "research.crystalmed.crystal_plague.intro"), 2)
                .laboratoryRecipe(id("crystal_reagent"))
                .build()
);
```

Pages registered in Java are merged with JSON pages. JSON is still preferable for text-heavy pages because pack authors can edit them without rebuilding the addon.

## 20. Java machine recipe

Register item-dependent recipes during common setup:

```java
BioForgeAddonApi.registerLaboratoryProcessRecipe(
        new LaboratoryProcessRecipe(
                id("crystal_reagent"),
                LaboratoryStation.CHEMICAL_SYNTHESIZER,
                List.of(
                        Ingredient.of(Items.AMETHYST_SHARD),
                        Ingredient.of(Items.GLOWSTONE_DUST),
                        Ingredient.of(Items.REDSTONE)
                ),
                new ItemStack(MyItems.CRYSTAL_REAGENT.get(), 2),
                180
        )
);
```

`MyItems.CRYSTAL_REAGENT` is an addon-owned Forge item registration. Replace it with your actual item.

## 21. Java Microscope and catalyst registration

The public API provides:

```java
BioForgeAddonApi.registerMicroscopeItem(item, entries, calibration);
BioForgeAddonApi.registerCatalystMapping(item, pathogenId);
BioForgeAddonApi.setUniversalCatalystChance(chance);
```

Use `MicroscopeSymptomEntry` for displayed values and `CalibrationSlider` for the calibration puzzle. Register custom textures on both clients through normal addon resources.

## 22. Custom Vaccine Maker operations and pages

For a new operation ID:

```java
BioForgeAddonApi.registerVaccineMakerOperation(
        id("crystal_antiserum"),
        new CrystalAntiserumOperation()
);
```

`VaccineMakerOperationHandler` receives a `VaccineMakerOperationContext` containing the machine, parsed recipe and final quality. It validates additional requirements and returns the output `ItemStack`.

Register a server-side page definition with `BioForgeAddonApi.registerVaccineMakerPage`. Logical machine slots are `0` through `20`. A page controls visible slot positions and server button handling; it does not create extra inventory by itself.

Optional client rendering is registered separately through `VaccineMakerPageRenderRegistry.register(pageId, renderer)` using a `VaccineMakerPageRenderer`. Client renderers may draw and handle visual input, but every inventory or gameplay result must still be validated server-side.

## 23. Public Java API summary

`BioForgeAddonApi` currently exposes registration for:

- pathogens, transmissions and symptoms;
- aliases for those three core definition types;
- transmission and symptom behaviors;
- mutation definitions and custom mutation effects;
- infection lifecycle profiles and pathogen defaults;
- natural strains and natural infection rules;
- CRISPR guide profiles, Cas modules and assays;
- directed vaccine actions and correction profiles;
- Vaccine Maker recipes, operations and pages;
- Centrifuge and decalcification recipes;
- Microscope item mappings;
- Incubator catalyst mappings and Universal catalyst chance;
- laboratory process recipes;
- Research Tablet pages.

Prefer this facade over reaching directly into BioForge manager internals. Internal packages may change while the public facade remains compatible.

# Part III: hybrid addon design

## 24. Connect Java behavior to JSON content

A strong addon architecture looks like this:

1. Java registers `crystalmed:crystal_burst` as a custom mutation effect.
2. JSON mutation definitions use `"type": "crystalmed:crystal_burst"`.
3. Java registers `crystalmed:crystal_fatigue` as a symptom behavior.
4. JSON symptom definitions list `"behaviors": ["crystalmed:crystal_fatigue"]`.
5. JSON defines pathogens, natural hosts, recipes, weights and balance.
6. A resource pack or addon resources provide translations, icons and textures.

This separation lets a modpack disable, replace or rebalance content while the addon supplies only the executable mechanic.

## 25. Server/client boundaries

- Infection mutation and recipe decisions belong on the server.
- Custom Java addons should normally be installed on both server and client.
- JSON biological definitions are synchronized where BioForge supports runtime client views.
- Custom textures, models, icons and translations are never magically synchronized; ship them in the addon or a required resource pack.
- Never mutate an inventory only from a client renderer or screen click.
- Validate packet data and button IDs on the server.

## 26. Compatibility checklist

Before release:

- use your own namespace everywhere;
- require the correct BioForge version in `mods.toml`;
- check `BioForgeAddonApi.API_VERSION`;
- test with and without JEI installed;
- test `/reload` on a dedicated server;
- run `/bioforge validate`;
- ensure every Research Tablet recipe ID resolves;
- ensure every mutation partner/grant ID exists;
- ensure natural infection rules reference registered entities and strains;
- ensure custom pathogen defaults match symptom types/ranges;
- ensure custom client textures exist;
- ensure no client-only class is loaded by dedicated-server code;
- verify an old saved infection still loads after updating the addon;
- never silently reuse an old ID for different biological meaning.

## 27. Useful test commands

The current BioForge command set includes tools for:

- `/bioforge validate` for definition validation;
- `/bioforge mutate definitions` to list mutation definitions;
- `/bioforge mutate info <mutation>` to inspect one mutation;
- `/bioforge mutate add`, `remove`, `random`, `clear` and `refresh` for controlled tests;
- `/bioforge definition infect` for namespaced definition infections;
- `/bioforge test report` for a system report;
- `/bioforge test stress` for stress testing;
- `/bioforge test blood_tubes` for blood sample kits;
- `/bioforge researchtablet pages` for page progression tests;
- `/bioforge decontaminate` for contamination cleanup tests.

Command arguments can evolve during test releases. Use in-game command suggestions as the authoritative syntax for the installed build.

## 28. Debugging failures

| Symptom | Likely cause |
|---|---|
| Core definition reload rejected | Missing reference, wrong type/range, duplicate ID or alias cycle |
| Mutation is not selectable | Disabled, weight zero, incompatible pathogen, unmet requirement or conflict |
| Custom effect is unknown | Java handler was not registered before mutation loading, or ID differs |
| Java registry is frozen | Registration occurred after server start |
| Research page is locked forever | Unlock item/tag is wrong or progression was not triggered |
| Recipe does not appear in JEI | Wrong directory/type, unresolved ingredient or recipe failed parsing |
| Texture is missing | Client resource path or namespace is wrong |
| Dedicated server crashes | Common code referenced a client-only Minecraft class |

Always inspect `logs/latest.log`. BioForge includes the resource ID in most loader errors, which identifies the exact broken JSON file.

## 29. Recommended first addon milestone

Start with this small vertical slice:

1. one custom pathogen;
2. one numeric symptom;
3. one mutation using built-in effects;
4. one lifecycle profile;
5. one natural mob infection rule;
6. one Microscope mapping;
7. one laboratory recipe;
8. one Research Tablet page;
9. translations and one icon;
10. a dedicated-server `/reload` and `/bioforge validate` test.

Once that complete loop works, add custom Java behavior. This catches namespace, loading, synchronization and asset problems before the addon becomes large.
