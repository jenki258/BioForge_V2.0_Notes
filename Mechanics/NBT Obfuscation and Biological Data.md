# NBT Obfuscation and Biological Data

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #NBT #Security #Data #AddonDevelopment

Strain, sample, vaccine, report, CRISPR, immunity, and diagnostic payloads use BioForge's NBT obfuscator and typed helpers. The goal is gameplay information control, not cryptographic protection against a server owner.

## Rules

- The server is authoritative.
- Writers serialize through the owning helper; readers use the matching helper.
- Random salt protects normal payloads; deterministic mode supports cases that need stable comparison.
- Copy operations copy only the intended biological fields.
- Unknown/invalid data fails safely instead of being trusted.
- Client tooltips receive only intended disclosure.

Addon code should use the public Biological NBT/BloodSample APIs rather than hard-coded tag names. See [[NBT obfuscating]], [[BloodSampleUtil]], and [[Biological NBT API]].
