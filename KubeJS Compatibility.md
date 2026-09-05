# KubeJS compatibility

BioForge 2.1 supports datapack/KubeJS recipe integration for the laboratory systems. Recipes can be added or replaced through their normal JSON recipe types, including Chemical Synthesizer, Pharma Mixer, Sterilization Chamber, Centrifuge, Incubator, Decontamination, and Vaccine Maker operations.

Use item tags for ordinary ingredients so other mods can provide compatible materials. Preserve NBT predicates for researched blood, cultures, medical reports, CRISPR data, and other stateful inputs. KubeJS scripts should run on the same loader-specific recipe events as the target installation: Forge 1.20.1 and NeoForge 1.21.1 are separate builds and should not share loader-specific imports.

When distributing an addon, document the recipe IDs, required NBT fields, and fallback behavior for missing optional ingredients. Test both JEI display and actual machine execution after changing a recipe.
