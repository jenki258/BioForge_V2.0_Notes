# CRISPR Notes

#BioForge #BioForge_V2_0 #Build_V0_54T #Item #CRISPR #Template #PlayerGuide #ModpackGuide #AddonDevelopment

> Registry ID: `bioforge:crispr_notes`.

CRISPR Notes store a reusable complete CRISPR cartridge program. They are separate from a Medical Report: notes remember sequence work, while a report proves exact-strain clinical and blood evidence.

- Write them in the Vaccine Maker when all 15 cartridges are installed and complete.
- Paper or a Book and Quill can provide the writing material through the document slot.
- Copy completed notes with paper without destroying the original.
- Load a template into 15 installed cartridges even when the current sample or Cas Module differs.
- The notes do not reveal the strain's public name.
- Sensitive stored data uses the NBT obfuscation layer.

See [[CRISPR and Vaccine Maker]].

## Correction templates

The same notes item can also store a complete antigen/correction matrix written from the fourth Vaccine Maker page. Sequence and correction payloads are typed, bound to a strain signature, and rejected when used as the wrong template kind or for another strain.

## Copying and books

- Right-click copy interactions preserve the source notes.
- Paper creates another notes/document result when supported.
- Book and Quill receives readable documentation without opening its GUI or deleting existing pages.
- A complete template loads only into the appropriate installed program layout.

The visible text is a research record; hidden sequence/matrix payloads use BioForge's obfuscation helpers.

See [[CRISPR Programming]], [[Vaccine Correction Matrix]], and [[Biological NBT API]].
