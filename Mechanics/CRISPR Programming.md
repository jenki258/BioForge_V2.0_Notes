# CRISPR Programming

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #CRISPR #VaccineMaker #Research #PlayerGuide #AddonDevelopment

BioForge uses four guide bases rather than a binary puzzle. A complete program has fifteen CRISPR cartridges, each carrying a four-base sequence plus one of three guide roles.

## Player loop

1. Insert viable exact-strain evidence.
2. Place/program all fifteen CRISPR cartridges.
3. Select a compatible Cas/PAM module.
4. Compare limited assay feedback rather than reading the hidden answer directly.
5. Record a complete program on paper, CRISPR Notes, or a Book and Quill.
6. Reuse a matching template only when all fifteen cartridge positions exist.

Correct positions use the same style of right/wrong feedback as the assay letter puzzle. The program can be reset or loaded without making the output quality directly visible.

## Data model

Guide profiles, allowed bases, role rules, deterministic strain target generation, assay feedback, and Cas modules are JSON-reloadable. A template is bound to its strain signature so a different strain cannot silently accept it.

Related: [[Cas and PAM Selection]], [[Vaccine Maker Pages and Inventory]], [[CRISPR Notes]], [[Vaccine Quality]].

