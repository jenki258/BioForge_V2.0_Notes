# Testing and Validation

#BioForge #BioForge_V2_0 #Build_V0_54T #Testing #Validation #Command #ModpackGuide #AddonDevelopment

Use `/bioforge validate` after every datapack reload. It checks IDs, referenced behaviors, ranges, requirements/conflicts, machine recipes, and other reloadable content.

The test command group can create blood samples for every type, generate controlled infections/vaccines/research data, run stress tests, and report results useful to testers. Separate commands cover infection immunity, area decontamination, blood knowledge, Research Tablet unlocks, mutation assignment, CRISPR, vaccine manufacture, and strain naming.

Regression should include dedicated server joins, relog persistence, all eight routes, PPE inward/outward behavior, contaminated crafting, machine inventories, JEI categories, Research Tablet recipes, vaccine assay/calibration, natural reservoirs, mutation interactions, scanner evasion, and cleanup.

Do not run stress commands in an irreplaceable world.
