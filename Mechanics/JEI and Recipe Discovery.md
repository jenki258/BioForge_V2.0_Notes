# JEI and Recipe Discovery

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #JEI #Recipe #PlayerGuide #AddonDevelopment

BioForge registers distinct JEI categories for crafting stations instead of hiding all operations behind ingredient lookup.

JEI covers Centrifuge, Incubator, Vaccine Maker treatments/pills/tablets, Chemical Synthesizer, Pharma Mixer, Sterilization Chamber, and Barrel Press. Each category uses the relevant machine GUI/background/slot visuals and recipe data rather than separate AI-generated textures.

The Research Tablet provides the in-mod alternative: station name, visual slot layout, icons, counts, and compatible alternatives. It includes crafting, chemical, pharma, sterilization, Centrifuge, Incubator, and Vaccine Maker references.

Reloadable recipes update through their managers; malformed files should be reported by validation rather than displayed as valid operations.

Related: [[Research Tablet Progression]], [[Laboratory Recipe API]], [[Recipe and Tag Compatibility]].
