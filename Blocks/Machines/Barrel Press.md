# Barrel Press

#BioForge #BioForge_V2_0 #Build_V0_54T #Block #Machine #BarrelPress #Chemistry #PlayerGuide #ModpackGuide #AddonDevelopment

> Registry ID: `bioforge:barrel_press`. Station ID: `barrel_press`.

## Purpose

The Barrel Press starts BioForge's alcohol chain by converting biological fruit inputs into [[Wine Must]]. It has its own wooden model, inventory model, GUI background, progress display, sound, JSON recipe type, JEI category, and Research Tablet recipe view.

## Inventory and operation

- Four input slots: three pressable fruit ingredients and one container.
- One result slot.
- The bundled recipe uses `#bioforge:ingredients/minecraft/pressable_fruits` three times plus a compatible glass bottle.
- The default process lasts 120 ticks and returns two Wine Must.
- The progress indicator is positioned independently from the input slots.

The block rotates to face its placer, uses a non-full collision shape, drops its stored contents when broken, and shows its placed model when carried in inventory.

## Data format

Recipes are separate JSON files under `data/<namespace>/laboratory_processing/` with `"station": "barrel_press"`. See [[Laboratory Recipe API]].

## Progression role

Wine Must feeds the Ethanol recipe, which then unlocks sterilizing solution, coatings, surfactants, cleaning, and higher laboratory equipment.

Related: [[Wine Must]], [[Ethanol]], [[Chemical Synthesizer]], [[JEI and Recipe Discovery]].

