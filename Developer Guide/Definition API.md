# Definition API

#BioForge #BioForge_V0_54T #JavaAPI #JSONAPI #AddonDevelopment

The definition layer exposes pathogens, symptoms, and transmissions through stable ResourceLocation IDs. JSON supports schema version, ID, aliases, priority, replace, enabled state, typed symptom values, allowed ranges, and behavior references.

Java addons register executable SymptomBehavior or TransmissionBehavior with `BioForgeBehaviorRegistry` during addon registration, then JSON definitions reference those IDs. Definitions are reloaded server-side and validated before becoming active.

Never use the `bioforge` namespace for addon content. Keep IDs stable after saves contain them and register behavior before reload. See [[BioForge addon creation guide]] for complete Java examples.
