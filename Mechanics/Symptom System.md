# Symptom System

#BioForge #BioForge_V0_54T #Mechanic #Symptom #Diagnosis #PlayerGuide #ModpackGuide #AddonDevelopment

BioForge symptoms are typed clinical parameters with executable server behavior and instrument-specific visibility. They are not all ordinary Minecraft effects.

## Value types

- Boolean values such as fever/hypothermia.
- Enums such as heart rhythm, lung sound, and microscope visibility.
- Percent/normalized floats such as oxygen, perfusion, redness, lesions, secretion, swelling, neural damage, and reflex strength.
- Large numeric values such as reflex delay, infection strength, colony radius, and infestation capacity.

The Vaccine Maker correction screen uses True/False for booleans, 101 states for percentages, and direct numeric entry for large values instead of forcing everything into sixteen steps.

## Gameplay consequences

Heart/lung problems restrict exertion, low oxygen reduces underwater breathing, poor perfusion reduces healing, neural/reflex problems impair control, lesions consume blood, secretion contaminates surfaces, and temperature extremes can cause fire/freeze-style damage. Mutation-defined coughing, sneezing, diet restrictions, panic, poison, or other effects add further behavior.

## Diagnosis

No one tool reveals everything. Clipboard-bound Thermometer, Stethoscope, Pulse Oximeter, Otoscope, Mirror, Reflex Hammer, blood reagents, and Microscope cover different channels.

## Extension

Typed definitions live in `bioforge_definitions/symptoms`; executable custom effects are registered in Java. See [[Symptom Catalogue]] and [[Definition API]].

