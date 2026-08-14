# Laboratory Recipe API

#BioForge #BioForge_V0_54T #JavaAPI #JSONAPI #Recipe #Machine #AddonDevelopment

Laboratory-processing JSON selects one station: `barrel_press` (4 in/1 out), `chemical_synthesizer` (3/1), `sterilization_chamber` (8 independent in-place), or `pharma_mixer` (5 in/result+waste).

Each operation is a separate file with tag/item ingredients, output/count, optional waste, and processing time. Centrifuge and Incubator use their own schemas/directories because their data-copy and biological behavior differ.

Java registration can add process definitions through the public API. Preserve server authority, output-fit checks, NBT-copy policy, and JEI/Research Tablet visibility.
