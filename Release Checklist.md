# Release Checklist

#BioForge #BioForge_V2_0 #Release #QA #Checklist

This is the release gate for BioForge V2.0. Static documentation or compilation alone cannot prove the gameplay loop; every unchecked runtime item should be tested on the exact candidate JAR.

## P0 — release blockers

- [ ] Produce a clean release JAR from a clean checkout and confirm there are no compiler warnings, missing resources, mixin errors, or data-loader errors.
- [ ] Start a fresh single-player world and a dedicated server with the candidate JAR.
- [ ] Join the dedicated server with a matching client and verify definitions, Research Tablet progress, strain names, contamination, immunity, and machine inventories synchronize.
- [ ] Start the dedicated server without JEI and without Curios to prove both integrations remain optional.
- [ ] Start with JEI and Curios installed and verify all categories and wearable renderers.
- [ ] Run `/reload` with the bundled data and confirm all loaders complete without retaining a stale snapshot.
- [ ] Run `/bioforge validate` and resolve every reported invalid or unresolved reference.
- [ ] Back up and load representative V1/V2 test worlds; verify saved blood, infections, reports, vaccines, templates, catalogue names, Research Tablet progress, and contamination migrate or fail safely.
- [ ] Confirm client-only classes never load on a dedicated server.
- [ ] Complete the full infection-to-treatment regression listed below.

## Full gameplay regression

### Infection and lifecycle

- [ ] Acquire each pathogen class through commands and legitimate gameplay.
- [ ] Verify incubation delays normal symptom and mutation runtime, survives relogging, and respects the `contagious_during_incubation` definition.
- [ ] Test finite and infinite lifespan, timed expiry, and self-destruction triggers.
- [ ] Test hot, cold, and neutral climate incubation rates and adaptation points.
- [ ] Confirm heat, cold, and dual adaptation mutations occur at configured thresholds.
- [ ] Confirm infection strength controls competing-strain replacement as documented.
- [ ] Confirm infectivity and cure resistance influence the correct stages without being applied twice.
- [ ] Verify natural infections use entity-specific chance/weight instead of infecting every matching mob.
- [ ] Verify the zombie natural virus is removed on player death and does not leak into unrelated persistent state.
- [ ] Verify full infection invulnerability blocks every acquisition route and actively clears infection without affecting unrelated players.

### All eight transmission routes

- [ ] Air-borne: room boundaries, doors/openings, source shedding, mask/HazCure modifiers, reservoir decay, and Air Vent suppression.
- [ ] Contact-based: interaction, mining, stepping, surface persistence, gloves, and cleanup.
- [ ] Environmental: colony creation, radius/capacity limits, combination with air/contact, and cleanup.
- [ ] Food-borne: contaminated ingredients, recipe outputs, consumption, and sterilization exceptions.
- [ ] Water-borne: drinks/potions, compatible crafting, consumption, and cleanup.
- [ ] Animals: infection of valid hosts, meat/egg/drop propagation, crafting, and consumption.
- [ ] Blood: needles, syringes, tubes, compatible blood transfer, equipment reuse, and HazCure piercing protection.
- [ ] Attack-based: melee transfer, gloves/HazCure behavior, and no false self-sampling from unrelated damage or explosions.

### Mutations and symptoms

- [ ] Apply all 81 mutations to a compatible Universal strain and record validation/runtime failures.
- [ ] Exercise every mutation trigger: apply, continuous, remove, chance, interval, requirements, conflicts, grants, removals, and interactions.
- [ ] Retest wall climbing, scanner evasion, grass dependency, flesh cravings, thermal adaptations, respiratory shedding, and tiered potion/attribute mutations.
- [ ] Confirm mutation effects are reapplied after relogging, dimension travel, death where appropriate, and definition reload.
- [ ] Verify every typed symptom changes its intended gameplay or diagnostic output.
- [ ] Verify coughing/sneezing cadence, particles, sound muffling, Warden vibration/hearing, and honey cough relief.
- [ ] Confirm symptom suppression disables only the programmed penalty for the calculated duration.

### Blood, tools, and records

- [ ] Test every ABO/Rh combination, all three reagents, transfusion compatibility, and infected blood transfer.
- [ ] Verify test tubes cannot consume/fill an entire creative stack incorrectly.
- [ ] Verify blood can return from a tube only to an empty or compatible syringe and carries infection.
- [ ] Verify blood knowledge invalidates when the subject's underlying blood data changes.
- [ ] Test every diagnostic tool against healthy, infected, incubating, and mutated subjects.
- [ ] Verify Clipboard temperature and Stethoscope readings are correct and do not duplicate target-change messages.
- [ ] Verify Medical Notes/Reports, books and quills, templates, cloning, and Gene Imprint off-hand copying preserve existing text and do not open the book unexpectedly.
- [ ] Confirm NBT obfuscation survives copying, machine processing, stacking, save/load, and networking for every biological information item.

### Machines and recipes

- [ ] Centrifuge: eight lanes, correct blood outputs, item rendering/rotation/light, processing animation, persistence, no x-ray transparency, and JEI recipes.
- [ ] Incubator: all recipes, three parallel outputs, catalysts for pathogen classes, Universal chance, facing, and item rendering.
- [ ] Microscope: per-item calibration persistence, scan button state, all symptom/pathogen reagent mappings, vaccinated-blood assay, rendered sample height, knob/lens animation, emitted light, and no transparency holes.
- [ ] Vaccine Maker: tab/page persistence at every GUI scale, no button flash, fixed hitboxes, 15-cartridge templates, Cas/PAM compatibility, correction percentages/numeric input, reset/read/write/import, redstone start, every treatment recipe, failure mutation, and quality concealment.
- [ ] Chemical Synthesizer: three inputs, one output, station-specific recipes, GUI, JEI, Tablet rendering, and persistence.
- [ ] Pharma Mixer: five inputs, product plus waste, station-specific recipes, GUI, JEI, Tablet rendering, and persistence.
- [ ] Sterilization Chamber: parallel in-place cleaning/conversion, no unintended output inventory, GUI, JEI, Tablet rendering, and persistence.
- [ ] Barrel Press: model, inventory model, transparency/z-fighting, progress-bar alignment, recipes, GUI, JEI, Tablet rendering, and Wine Must container behavior.
- [ ] Confirm every recipe uses an appropriate tag where cross-mod interchangeability is intended, while identity-sensitive medical items remain exact.
- [ ] Confirm no JEI or Tablet recipe displays `Uncraftable Potion` or an unresolved ingredient.

### World blocks and protection

- [ ] Test all four viral scanner shapes, multiblock placement/removal, top geometry, texture seams, scanner-evasion behavior, and redstone output.
- [ ] Verify the Area Contamination Scanner marks real hazard blocks temporarily without revealing the strain.
- [ ] Verify Air Vent range, passive cleanup, overlap, chunk unload/reload, and performance.
- [ ] Verify microbial mats, colony cores, sporocarps, necrotic patches, infested blocks/crops, and contaminated substrate preserve colour and infection data.
- [ ] Test Medical Mask, Protective Gloves, Ice Bag Harness, Magma Bag Harness, and each HazCure piece in armour and Curios slots where supported.
- [ ] Inspect all wearable models on both slim and standard player models; verify gloves attach to arms and each thermal harness uses the correct texture.
- [ ] Confirm HazCure physical defence remains intentionally moderate while biological protection follows the documented per-piece/full-set rules.

## P1 — localization and presentation

- [x] `en_us`, `ru_ru`, `uk_ua`, `de_de`, and `tr_tr` have identical 1,076-key sets.
- [x] Turkish JSON syntax, placeholders, and line-break presence have been validated.
- [ ] Refactor mutation `name`/`description` fields to translation keys with backward-compatible literal fallback.
- [ ] Refactor Cas/PAM `display_name` to a translation key with literal fallback.
- [ ] Localize remaining admin/test/validation command output.
- [ ] Localize the Petri Dish growth-stage prefix and Research Tablet emergency fallback.
- [ ] Review every language in-game at GUI scales 1–4 for clipping, overlap, ellipses, and hitbox drift.
- [ ] Have native speakers review Russian, Ukrainian, German, and Turkish terminology in context.
- [ ] Decide whether the public wiki remains English-only or receives maintained language branches.
- [ ] Confirm every sound has a subtitle and every subtitle key is present in all locales.

## P1 — visuals, audio, and accessibility

- [ ] Inspect every item model, blockstate, block model, armour model, GUI background, icon, particle, and tint layer for missing-texture fallback.
- [ ] Check transparent machine parts against adjacent solid blocks to prevent x-ray views.
- [ ] Check scanner and barrel models from every direction for z-fighting and missing faces.
- [ ] Test GUI scale, Unicode fonts, colour contrast, scrollbars, tooltips, keyboard focus, and mouse hitboxes.
- [ ] Verify animated machine items do not clip through models and stop when processing stops.
- [ ] Balance coughing, sneezing, machine, UI, paranoia, alarm, and completion sounds; confirm masks/HazCure muffle only intended sources.
- [ ] Verify sound files, textures, models, and contributed assets have documented ownership and release permission.

## P1 — performance and persistence

- [ ] Run the built-in report and stress commands on a dedicated server with recorded MSPT, memory, entity count, contaminated-block count, and reservoir count.
- [ ] Soak-test a populated server for several hours with air-borne, contact, animal, food, and environmental spread active.
- [ ] Confirm scheduled work is bounded per tick and unloaded chunks are not force-loaded.
- [ ] Confirm expired airborne/contact reservoirs are removed from saved data and indexes.
- [ ] Confirm Air Vents and scanners use spatial indexes/caches without retaining removed blocks.
- [ ] Profile mutation ticks with many infected mobs and verify interval/chance effects do not scan the world unnecessarily.
- [ ] Restart the server and verify every machine inventory, page/tab, calibration target, strain catalogue entry, immunity, lifecycle counter, and contamination record persists exactly once.

## P1 — addon and datapack contract

- [ ] Build at least one external test addon against API version 3 without importing internal packages.
- [ ] Load a JSON-only test pack containing one custom pathogen, symptom, transmission, mutation, lifecycle, natural infection, machine recipe, Microscope mapping, Vaccine Maker recipe, and Research Tablet page.
- [ ] Test duplicate IDs, aliases, priorities, replacement, disabled built-ins, invalid references, and atomic reload rollback.
- [ ] Verify addon namespaces survive samples, reports, CRISPR, vaccines, immunity, transmission, save/load, and client sync.
- [ ] Publish exact JSON schemas or validated examples for every reloadable directory.
- [ ] Mark public Java API stability and deprecation policy; avoid promising internal packages.
- [ ] Document version compatibility in addon `mods.toml` and the wiki.

## P2 — packaging and public release

- [ ] Set one consistent public version across Gradle metadata, `BioForge.VERSION`, filename, changelog, download page, and wiki snapshot.
- [ ] Review `mods.toml`: license, authors, description, logo, dependency ranges, issue tracker, and update/download links.
- [ ] Decide and publish the actual licence terms; `All Rights Reserved` must match the intended addon and redistribution policy.
- [ ] Prepare a concise player changelog and a separate migration/addon changelog.
- [ ] Publish installation, server, configuration, known-issues, reporting, and world-backup instructions.
- [ ] Remove development-only files and secrets from the distributable JAR while keeping data examples intentionally shipped.
- [ ] Verify the JAR contains all five locale files, assets, data, access transformers if any, and no source-only paths.
- [ ] Test the exact uploaded artifact, not only the development run directory.
- [ ] Create release hashes and archive the matching source/documentation snapshot.
- [ ] Publish the `GitHub-Wiki` clone and verify every sidebar and page link after GitHub normalizes filenames.

## Recommended release decision

Do not call V2.0 stable until every P0 item passes on one immutable candidate JAR. P1 failures may justify another test build even when the mod starts successfully, especially localization gaps, save corruption, dedicated-server failures, recipe discovery failures, contamination leaks, or unbounded spread cost. P2 is the difference between a working build and a release that players and addon authors can safely adopt.

