# Localization and Translation

#BioForge #BioForge_V2_0 #Localization #Translation #AddonDevelopment

## Bundled languages

BioForge currently ships these Minecraft locale files:

| Locale | File |
|---|---|
| English (United States) | `en_us.json` |
| Russian (Russia) | `ru_ru.json` |
| Ukrainian (Ukraine) | `uk_ua.json` |
| German (Germany) | `de_de.json` |
| Turkish (Türkiye) | `tr_tr.json` |

Each bundled file contains the same 1,076 keys. Locale filenames must use Minecraft's lowercase locale code; `tr_TR.json`, `uk_uk.json`, and `de_ge.json` are not valid replacements for `tr_tr.json`, `uk_ua.json`, and `de_de.json`.

## Translator rules

1. Copy `en_us.json` and keep every key unchanged.
2. Translate values only.
3. Preserve formatting tokens such as `%s`, `%1$s`, `%s%%`, line breaks, and colour/control semantics.
4. Indexed placeholders may be reordered to form a natural sentence.
5. Keep stable technical terms consistent: CRISPR, gRNA, Cas/PAM, ABO, Rh, JEI, NBT, SpO₂, and registry IDs.
6. Validate the final file as strict JSON and compare its key set with `en_us.json`.
7. Review text at small GUI scales; a grammatically correct translation may still be too wide.

## Current localization boundary

Most items, blocks, GUIs, tooltips, JEI categories, advancements, sounds, Research Tablet pages, pathogens, transmissions, symptoms, and normal player messages are translated through language keys.

The following surfaces are not fully translatable yet:

- bundled mutation JSON stores English `name` and `description` strings and runtime code reads them literally;
- CRISPR Cas/PAM JSON stores a literal `display_name`;
- several administrator, definition-validation, mutation, blood-knowledge, and stress-test command responses are hard-coded English;
- the Petri Dish growth-stage tooltip contains a hard-coded English prefix;
- the emergency fallback Research Tablet page contains hard-coded English text;
- fallback paths may humanize an unknown definition ID when no translation key exists;
- user-created strain names, player names, IDs, CRISPR sequences, numbers, and symbols are dynamic data and are not language-file content.

This is a release-polish limitation, not a missing Turkish key. Adding more entries to `tr_tr.json` cannot translate text that never requests a translation key.

## Addon localization

Java addons should build user-facing components with translation keys. Datapacks cannot ship client language files by themselves; distribute a companion resource pack or Java addon resources for translated names, descriptions, Research Tablet content, icons, and textures. Always provide an English fallback.

