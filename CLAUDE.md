# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is **not a software project** — there is no build, test, lint, or package manifest, and it is not a git repository. It is a **Vietnamese localization workspace** for Crusader Kings III and the *Princes of Darkness* (POD) total-conversion mod. All work is editing CK3 `.yml` localization files by hand.

Read [README.md](README.md) first — it is the authoritative translation policy (terminology priority, consistency rules, style guide). This file covers the structural/technical facts that README does not.

## The two trees

| Path | Role | Editable? |
|---|---|---|
| [base_game_vh/](base_game_vh/) | **Finished** Vietnamese localization of vanilla CK3 + official DLCs. 1199 `.yml` files. | **No.** Read-only translation memory. |
| [princesofdarkness/](princesofdarkness/) | The POD mod, shipped as-is by its authors. | Only `localization/english/`. |

`base_game_vh/` is a reference dump, not a loadable mod — it has no `descriptor.mod`. `princesofdarkness/` is the real mod (`descriptor.mod`, `princesofdarkness.mod`, version 1.19.0.6).

## How Vietnamese is delivered

CK3 has no Vietnamese language slot. Both trees solve this the same way: **Vietnamese text lives under the `l_english:` header, in `*_l_english.yml` files, inside `localization/english/`.** The English strings are overwritten in place; keys are never renamed. Confirm this by opening any file in `base_game_vh/localization/english/` — English keys, Vietnamese values.

So translating POD means editing [princesofdarkness/localization/english/](princesofdarkness/localization/english/) in place. Do **not** create a `localization/vietnamese/` folder — the game would ignore it.

**Current state: POD is 0% translated.** All 460 English `.yml` files (~87,000 keys, ~104,000 lines) are still English.

## Non-obvious file conventions

These differ between the two trees; **match whatever the file you are editing already uses** rather than normalizing:

- **BOM:** every `.yml` in both trees starts with a UTF-8 BOM (`EF BB BF`). Preserve it — CK3 fails to parse files without it.
- **Line endings:** POD files are **CRLF**; `base_game_vh` files are **LF**.
- **Version suffix:** `base_game_vh` keeps vanilla's `key:0 "value"` numbering. POD writes `key: "value"` with no number. Do not add or remove the number.
- **Indentation:** one leading space before each key.

## Localization syntax that must survive translation

Only the human-readable words inside `"…"` change. Everything below is machine-read:

- `$other_key$` — string reference to another loc key
- `[Scope.GetSomething]`, `[GetBuilding('tribe_01').GetName]` — script functions
- `[concept_name|E]` — game-concept link (e.g. `[armies|E]`); the token inside is a key, never Vietnamese
- `@icon_name!` — inline icon (e.g. `@artifact_icon!`, `@assamite_icon!`)
- `#T … #!`, `#V …#!`, `#flavor …#!`, `#weak …#!` — colour/style tags; the tag word is not text
- `\n`, `[AddLocalizationIf( … )]`, `[Select_CString( … )]`

### The `Glossary()` trap

POD leans heavily on glossary wrappers, defined in [localization/english/glossary_POD_l_english.yml](princesofdarkness/localization/english/glossary_POD_l_english.yml):

```
pod_diablerie: "[Glossary('Diablerie','game_concept_diablerie_desc')]"
```

**First argument = displayed text (translate it). Second argument = a loc key (never translate it).** `base_game_vh` contains at least one place where the second argument was translated by mistake (`game_concepts_l_english.yml:614`) — do not copy that pattern.

Because so much POD prose goes through `$pod_diablerie$`-style shortcuts, translating `glossary_POD_l_english.yml` early propagates consistent terminology across thousands of strings. Do it before the bulk event files.

### Files that are not prose

- [localization/english/POD_do_not_translate_this_l_english.yml](princesofdarkness/localization/english/POD_do_not_translate_this_l_english.yml) (and its copy under `replace/`) — the *values* are script identifiers (`"potence_visible"`, `"always_yes_gui"`) consumed by GUI code. Leave the whole file alone.
- [localization/english/replace/](princesofdarkness/localization/english/replace/) — CK3's `replace/` subfolder hard-overrides vanilla keys. `pod_replace_vanilla_l_english.yml` mostly contains name-format templates (`CHARACTER_FIRST_NAME_AND_DYNASTY: "$NAME$"`) that are pure structure. Translate only the ones with real words, and remember these override the corresponding `base_game_vh` strings — a change here alters vanilla UI text too.

## Terminology lookup workflow

Before inventing any Vietnamese term, grep the reference tree. Use ripgrep via the Grep tool:

- Find how a vanilla concept was rendered: search `base_game_vh/localization/english/` for the **English key**, not the English word (the English words are gone — only keys remain). E.g. for POD's `trait_brave`, search `trait_brave` in `base_game_vh/localization/english/traits_l_english.yml`.
- Find prior use of a Vietnamese term to check consistency: search the term itself across `base_game_vh/localization/english/`.
- POD-specific concepts have no vanilla key. Check whether a stylistically similar vanilla concept exists first; only then coin a term, and record it so it is reused.

[princesofdarkness/localization/simp_chinese/](princesofdarkness/localization/simp_chinese/) is a **complete** POD translation (498 files) done by another team. It is useful as a structural cross-check — which files/keys they treated as translatable, how they handled `$ref$` and `Glossary()` — but its terminology choices carry no authority over `base_game_vh`.

## Scale, for planning

Bulk of the work in `localization/english/`, by lines:

| Area | Lines |
|---|---|
| `event_localization/` | ~25,300 |
| root-level `*.yml` | ~20,900 |
| `religion/` | ~8,000 |
| `lifestyles/` | ~8,000 |
| `buildings/` | ~7,300 |
| `gui/` | ~5,300 |
| `modifiers/` | ~5,100 |
| `interactions/` | ~4,700 |
| `names/` | ~4,500 |

`names/`, `dynasties/` and `bookmark/` are largely proper nouns — usually left as-is, matching how `base_game_vh` handles vanilla names.

## Known conflict: fonts

Both trees ship `fonts/fonts.font` and override the same font slots. `base_game_vh/fonts/fonts.font` maps `l_english` to its bundled Open Sans / Gitan / Fondamento files (the ones that render Vietnamese diacritics). `princesofdarkness/fonts/fonts.font` maps `l_english` to decorative faces (`cinzeldecorative-*.ttf`, `pirataone-regular.ttf`, `cabaletta.ttf`) that are unlikely to carry the full Vietnamese diacritic set. Whichever mod loads later wins. If translated POD text renders with missing or boxed glyphs, this is why — the fix is in POD's `fonts.font` groups, not in the `.yml` files.

## Everything else in `princesofdarkness/`

`common/`, `events/`, `history/`, `gui/`, `gfx/`, `music/`, `map_data/` are the mod's game logic and assets. They define the loc keys but contain no player-facing prose to translate. Do not edit them — with the single exception of `fonts/fonts.font` if the glyph problem above needs fixing.
