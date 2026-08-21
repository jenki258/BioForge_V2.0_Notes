# Cas and PAM Selection

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #CRISPR #Cas #PAM #VaccineMaker #PlayerGuide #AddonDevelopment

Cas/PAM is a functional module choice, not decorative text shared by every vaccine.

## Bundled modules

- SpCas9.
- Cas12a.
- Cas13d.

Each module definition can set display data, pathogen/guide compatibility, PAM rules, quality modifiers, and other constraints consumed by the Vaccine Maker. The item tooltip uses the module's human-readable name rather than exposing an internal ID.

## Gameplay consequence

A perfect base sequence paired with an unsuitable module does not produce the same result as a fully compatible program. Researchers must identify both guide sequence and enzyme context.

## Extension

JSON modules live under `data/<namespace>/crispr/cas_modules/`. Java addons may register supporting behavior before data reload. Keep IDs namespaced and stable.

Related: [[Cas PAM Module]], [[CRISPR Programming]], [[Vaccine Maker API]].

