# KubeJS Recipe Support

BioForge exposes every processing station as a real Minecraft recipe type. KubeJS is optional: BioForge does not require it to launch, but a modpack can add recipes through `ServerEvents.recipes` when KubeJS is installed.

The supported recipe types are:

- `bioforge:centrifuge`
- `bioforge:decalcification`
- `bioforge:incubator`
- `bioforge:laboratory_processing`
- `bioforge:vaccine_maker`

`bioforge:laboratory_processing` covers Barrel Press, Chemical Synthesizer, Pharma Mixer and Sterilization Chamber through its `station` field.

## Script location

Place server recipe scripts in `kubejs/server_scripts/`. After changing a script, run `/reload` or restart the world. Added recipes are synchronized to clients and are used by the machines, JEI and the Research Tablet.

## Centrifuge

```js
ServerEvents.recipes(event => {
  event.custom({
    type: 'bioforge:centrifuge',
    input: '#forge:dusts/redstone',
    output: 'minecraft:redstone',
    copy_blood_data: false,
    copy_nbt: false,
    copy_infection: false,
    processing_time: 100
  }).id('kubejs:bioforge/centrifuge/redstone')
})
```

Weighted results use `outputs` instead of `output`:

```js
ServerEvents.recipes(event => {
  event.custom({
    type: 'bioforge:centrifuge',
    input: 'minecraft:gravel',
    outputs: [
      { item: 'minecraft:flint', weight: 3 },
      { item: 'minecraft:iron_nugget', weight: 1 }
    ],
    processing_time: 140
  }).id('kubejs:bioforge/centrifuge/gravel_separation')
})
```

## Decalcification

```js
ServerEvents.recipes(event => {
  event.custom({
    type: 'bioforge:decalcification',
    input: 'minecraft:bone',
    output: 'minecraft:bone_meal',
    copy_blood_data: false,
    copy_nbt: false,
    copy_nbt_keys: []
  }).id('kubejs:bioforge/decalcification/bone')
})
```

Inputs and outputs may be item IDs or tag IDs beginning with `#`.

## Laboratory processing

Valid station names are `barrel_press`, `chemical_synthesizer`, `pharma_mixer` and `sterilization_chamber`.

### Chemical Synthesizer

```js
ServerEvents.recipes(event => {
  event.custom({
    type: 'bioforge:laboratory_processing',
    station: 'chemical_synthesizer',
    ingredients: [
      { item: 'minecraft:slime_ball' },
      { tag: 'forge:dusts/redstone' }
    ],
    output: 'minecraft:magma_cream',
    count: 1,
    processing_time: 160
  }).id('kubejs:bioforge/chemical/magma_compound')
})
```

### Pharma Mixer

Pharma Mixer recipes must define both the main output and a waste output.

```js
ServerEvents.recipes(event => {
  event.custom({
    type: 'bioforge:laboratory_processing',
    station: 'pharma_mixer',
    ingredients: [
      { item: 'minecraft:sugar' },
      { item: 'minecraft:spider_eye' }
    ],
    output: 'bioforge:symptom_tablet',
    waste: 'minecraft:charcoal',
    waste_count: 1,
    processing_time: 220
  }).id('kubejs:bioforge/pharma/example_tablet')
})
```

### Sterilization Chamber

Sterilization recipes accept exactly one ingredient and replace the processed stack in its original slot.

```js
ServerEvents.recipes(event => {
  event.custom({
    type: 'bioforge:laboratory_processing',
    station: 'sterilization_chamber',
    ingredients: [{ item: 'minecraft:rotten_flesh' }],
    output: 'minecraft:leather',
    copy_nbt: false,
    processing_time: 180
  }).id('kubejs:bioforge/sterilization/treated_leather')
})
```

## Incubator

```js
ServerEvents.recipes(event => {
  event.custom({
    type: 'bioforge:incubator',
    primary_input: 'minecraft:spider_eye',
    secondary_input: 'bioforge:nutrient_medium',
    output: 'bioforge:virus_sample',
    output_count: 1,
    operation: 'craft',
    processing_time: 200,
    primary_item_cost: 1,
    primary_cost_mode: 'per_batch',
    catalyst_charge_cost: 0
  }).id('kubejs:bioforge/incubator/example_sample')
})
```

Available operations are `craft`, `generate_strain`, `copy_sample_strain` and `copy_blood_strain`. `generate_strain` requires a positive `catalyst_charge_cost`. A wildcard primary input requires a concrete `jei_input`.

## Vaccine Maker

Vaccine Maker scripts use the same structure as BioForge vaccine datapack recipes.

```js
ServerEvents.recipes(event => {
  event.custom({
    type: 'bioforge:vaccine_maker',
    operation: 'full',
    guide_profile: 'bioforge:default',
    processing_time: 240,
    requires_program: false,
    consume_sample: true,
    inputs: {
      sample: { tag: 'bioforge:ingredients/bioforge/virus_sample' },
      carrier: { tag: 'bioforge:ingredients/bioforge/vaccine' },
      reagent: { tag: 'bioforge:ingredients/bioforge/nutrient_medium' }
    },
    result: {
      item: 'bioforge:vaccine',
      uses: 1,
      defense_risk: 0.18
    }
  }).id('kubejs:bioforge/vaccine_maker/basic_full_vaccine')
})
```

Advanced recipes may also define CRISPR cartridges, Cas/PAM modules, reports, quality weights, research bonuses, directed results and mutation failure parameters. Their field layout is identical to the JSON vaccine recipe format.

## Removing scripted recipes

KubeJS-created recipes can be removed by ID or recipe type:

```js
ServerEvents.recipes(event => {
  event.remove({ id: 'kubejs:bioforge/centrifuge/redstone' })
  event.remove({ type: 'bioforge:vaccine_maker' })
})
```

Give every scripted recipe a stable `.id(...)`. This prevents accidental duplicates and allows other scripts to replace it predictably.

## Flesh Cravings food compatibility

The `flesh_cravings` mutation accepts every edible item in the `bioforge:foods/meat` item tag. Modpacks can add modded meat, fish, meals or unusual flesh foods without changing BioForge code:

```js
ServerEvents.tags('item', event => {
  event.add('bioforge:foods/meat', [
    'examplemod:raw_venison',
    'examplemod:cooked_venison',
    '#examplemod:foods/meat_dishes'
  ])
})
```

Forge common meat and fish tags and NeoForge `c:foods/raw_meat`, `c:foods/cooked_meat`, `c:foods/raw_fish` and `c:foods/cooked_fish` are included automatically when present.

## Version notes

The same BioForge recipe type IDs and field names are used on Forge 1.20.1 and NeoForge 1.21.1. Minecraft ingredient component syntax differs between versions, so prefer normal item and tag ingredients when one script pack must support both versions.
# 2.1 update

The 2.1 recipe layer also exposes Vaccine Maker operations, including `random_mutation_upgrade`, alongside chemical, pharmaceutical, sterilization, centrifuge, incubator, and decontamination recipes. Keep recipe inputs tag-friendly and preserve NBT predicates when a recipe intentionally requires a researched sample or report.
