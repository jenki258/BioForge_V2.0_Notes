# Vaccine Maker Pages and Inventory

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #VaccineMaker #GUI #Inventory #PlayerGuide #AddonDevelopment

The Vaccine Maker has one shared server inventory and multiple client pages. Switching pages never moves or duplicates stacks.

## Pages

1. **CRISPR:** fifteen cartridge positions, Cas/PAM selection, sequence controls, guide feedback, Gene Imprint evidence, and a documentation slot.
2. **Journal:** research notes, available evidence, and contextual explanations rather than the main crafting grid.
3. **Craft:** all synthesis/reagent inputs, an exact-strain Medical Report slot separated from reagent slots, result slot, progress, and start control.
4. **Correction:** every editable symptom, transmission, mutation, ecological, and lifecycle channel; reset/read/write controls and its document slot.

The screen remembers both selected tab and the page within a tab when closed and reopened. Long labels use smaller text and tooltips rather than unreadable overlap or trailing ellipses.

## Starting

A valid operation begins through the GUI button or a rising redstone signal. Missing/invalid ingredients, incomplete programs, blocked output, or recipe constraints prevent startup without consuming a successful result.

## Extensibility

Java addons can register additional page factories and operations. JSON controls recipes, actions, profiles, and correction definitions.

Related: [[Vaccine Maker]], [[CRISPR Programming]], [[Vaccine Correction Matrix]], [[Vaccine Maker API]].

