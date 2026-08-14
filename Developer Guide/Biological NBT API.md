# Biological NBT API

#BioForge #BioForge_V0_54T #JavaAPI #NBT #Data #AddonDevelopment

Use `BloodSampleUtil`, NBT obfuscation helpers, and the owning item/system serializers to read, write, clear, compare, or copy biological data.

Do not inspect private tag names, send complete strain payloads to clients, or copy all NBT when a recipe should copy only blood/strain fields. Preserve subject UUID, source, amount, type, infection fingerprint, quality, and program fields only where the workflow explicitly requires them.

Addon items should expose player tooltips through supported presentation helpers and remain compatible with sterilization/stacking rules.
