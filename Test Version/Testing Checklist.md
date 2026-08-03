# Testing Checklist

This is the release-readiness checklist for the current test version. Mark a box only after testing inside Minecraft; compilation alone does not complete runtime checks.

## Already validated outside the game

- [x] Direct Java 17 compilation completed for all 225 source files.
- [x] Bundled JSON files passed syntax parsing.
- [x] Validation was performed without Gradle, as requested.
- [ ] Full Forge launch with final resources and textures.

## Blood and tools

- [ ] JEI shows a filled blood tube in the applicable recipe.
- [ ] Direct intended blood collection works on self and valid mobs.
- [ ] End Crystal, TNT, projectile, fire, fall, and other indirect damage cannot fill a blood tool.
- [ ] A filled tube transfers into an empty syringe.
- [ ] Same compatible blood can be combined; incompatible transfer is rejected without loss.
- [ ] Infection transfers from an infected tube to the syringe.
- [ ] Thermometer cannot mine blocks and records the correct Clipboard temperature.

## Clipboard and documents

- [ ] Clicking a mob assigns that mob on both client and server.
- [ ] Changing patient produces one message, never two.
- [ ] Paper prints one correctly bound Medical Report.
- [ ] Data-compatible reports stack to 16 and paper cloning preserves contents.
- [ ] Report and Clipboard text append to a Book and Quill without clearing the source.
- [ ] Book GUI does not open during transfer.
- [ ] Tooltips advertise copy/book interactions.
- [ ] Complete and incomplete blood findings render correctly.
- [ ] Report evidence is accepted only for its bound infection fingerprint.
- [ ] Supported older Clipboard/report items remain readable.

## Microscope and Incubator

- [ ] Incubator/Microscope labels match Centrifuge text color.
- [ ] Microscope calibration dragging, scrolling, and button textures align.
- [ ] Unknown Gene Imprint becomes identified only after Microscope analysis.
- [ ] Symptom and Cas/PAM names are localized, not raw IDs.
- [ ] Incubator JSON recipes preserve strain data and charge/item costs.
- [ ] JEI shows all bundled Incubator recipes accurately.
- [ ] `/reload` refreshes supported Microscope/Incubator/catalyst JSON.

## Vaccine Maker GUI

- [ ] CRISPR, Journal, and Synthesis tabs switch without moving/duplicating items.
- [ ] Addon page ordering remains stable.
- [ ] All 15 cartridge slots accept only valid cartridges.
- [ ] Each four-base hitbox edits the clicked base.
- [ ] Numeric quality updates after relevant edits/input changes.
- [ ] Translated labels remain inside the GUI or use tooltips.
- [ ] Document and Gene Imprint interactions work from the CRISPR page.
- [ ] Every physical slot appears on Synthesis.
- [ ] The `18x19` frame aligns around the normal 16x16 item and shows its shadow.
- [ ] Textured buttons have correct normal/hover/disabled behavior.
- [ ] Reopening preserves inventory and machine state.

## Notes and templates

- [ ] Notes can be written only with all 15 complete cartridges.
- [ ] Paper and Book and Quill produce the intended CRISPR Notes.
- [ ] Notes clone with paper without altering the original.
- [ ] Templates load into 15 installed cartridges.
- [ ] Loading remains allowed despite current sample/Cas mismatch.
- [ ] Loading never duplicates cartridges or unexpectedly consumes notes.
- [ ] Notes do not reveal the strain name.

## Vaccine recipes and processing

- [ ] Full, Mutation, Transmission, Symptom, and Random Mutation carriers insert and craft.
- [ ] Mismatched directed carrier/imprint category is rejected.
- [ ] Clone recipes preserve vaccine family.
- [ ] The button starts once when conditions are valid.
- [ ] A rising redstone edge starts once; continuous power does not restart each tick.
- [ ] Blocked output prevents processing without consuming inputs.
- [ ] Recipe-specific time and consumption flags are honored.
- [ ] Low-quality failure can mutate the source and plays the mutation scroll.

## Treatment and immunity

- [ ] Exact high-quality vaccine uses configured probability rather than guaranteeing success.
- [ ] Below-minimum similarity gives no full-vaccine cure chance.
- [ ] Infection strength and defense mutations reduce success.
- [ ] Exact ABO/Rh, same-Rh, mismatch, and unknown multipliers differ as configured.
- [ ] Directed actions add/remove/opposite mutation, transmission, and symptom targets.
- [ ] Random Mutation Vaccine requires a matching active infection.
- [ ] Random selection respects requirements/conflicts and does not reveal its result immediately.
- [ ] Successful full treatment grants only exact-strain immunity.
- [ ] Immunity blocks the intended strain, persists through relog, and expires.
- [ ] Quality correctly scales duration from low to high.
- [ ] Inventory/effect tooltips show the catalogued infection and remaining time.

## Mutation lifecycle

- [ ] Apply, continuous, and remove triggers run at their intended times.
- [ ] Continuous effects respect intervals and conditions.
- [ ] Effects refresh after relog, respawn, load, and `/reload`.
- [ ] Requirements/conflicts prevent invalid random mutations.
- [ ] Interaction modifiers amplify/suppress the selected effect.
- [ ] Interaction grants/removals settle without loops.
- [ ] Attribute modifiers clean up when infection/mutation is removed.
- [ ] Mutation scrolling remains synchronized in multiplayer.

## Naming and disclosure

- [ ] First eligible discovery opens the naming GUI automatically.
- [ ] Later permits the intended later prompt.
- [ ] Only one researcher can claim the first name.
- [ ] Invalid/stale naming requests are rejected server-side.
- [ ] Admin list/rename survives restart.
- [ ] Vaccines, Gene Imprints, and CRISPR Notes hide strain names.
- [ ] Live Culture Vial hides raw pathogen/symptom details.
- [ ] Complete reports and immunity UI show the correct public name.

## Dedicated server and compatibility

- [ ] Dedicated server starts without client-only classloading errors.
- [ ] Two players' machines and Clipboard sessions do not cross-talk.
- [ ] Menu packets reject invalid distance, block, slot, and page data.
- [ ] World `serverconfig` is created and changed values apply after restart.
- [ ] BioForge starts when JEI is absent.
- [ ] Malformed addon JSON fails clearly without corrupting saved strains.
- [ ] Old worlds load Vaccine Maker inventories with the expanded slot count.
- [ ] Missing optional textures fall back to readable GUI rendering.

## Sign-off rule

The build is ready for wider testing when all critical item-loss, duplication, networking, exact-strain binding, and persistence checks pass. Cosmetic issues may be documented in milanote; data loss, disclosure bypasses, cure bypasses, and duplication cannot.

