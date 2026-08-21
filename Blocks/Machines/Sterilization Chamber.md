# Sterilization Chamber

#BioForge #BioForge_V2_0 #Build_V0_54T #Block #Machine #Sterilization #Containment #PlayerGuide #ModpackGuide #AddonDevelopment

> Registry ID: `bioforge:sterilization_chamber`. Station ID: `sterilization_chamber`.

## Purpose

The Sterilization Chamber cleans or transforms items in place. Unlike the Chemical Synthesizer and Pharma Mixer, it has no separate result inventory.

## Inventory and operation

- Eight independent processing slots.
- Each valid stack runs its own recipe and progress.
- On completion the input slot becomes the sterile output.
- Contaminated compatible items can have their infection data removed without being moved to a separate result slot.

Bundled transformations include ordinary bottles into Laboratory Glassware, Polymer Resin into Sterile Polymer Sheets, slime-based material into Sterile Rubber, Activated Carbon into Sterile Filters, and Dirty Culture Vials back into reusable Live Culture Vials.

## Extension

JSON recipes use `"station": "sterilization_chamber"`. Keep outputs stack-compatible with the in-place inventory model and use BioForge data-copy/cleaning helpers when Java behavior carries biological NBT.

Related: [[Dirty Culture Vial]], [[Laboratory Glassware]], [[Sterile Polymer Sheet]], [[Laboratory Recipe API]].

