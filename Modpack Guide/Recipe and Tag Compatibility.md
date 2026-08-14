# Recipe and Tag Compatibility

#BioForge #BioForge_V0_54T #Recipe #Tag #Compatibility #ModpackGuide #AddonDevelopment

BioForge recipe inputs use tags so equivalent materials from other mods can participate without direct dependencies.

Important groups cover every BioForge progression ingredient, vanilla ingredient aliases, pressable fruits, meat foods, infectable crops, organic substrate, scanner frames/controllers/optics, HazCure pieces, and route/PPE behavior.

A pack may append values with `"replace": false`, replace a tag deliberately, or replace entire recipes. Keep output registry IDs stable and remember that contaminated ingredients can propagate infection through crafting independently of recipe compatibility.

Machine recipes are one JSON file per operation. Do not merge Chemical Synthesizer, Pharma Mixer, Sterilization, and Barrel Press into one content file just because they share a loader.
