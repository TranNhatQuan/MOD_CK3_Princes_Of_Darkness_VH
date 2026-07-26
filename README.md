# CK3 Vietnamese Localization Project

## Overview

This repository contains the Vietnamese localization project for Crusader Kings III and the **Princes of Darkness** total conversion mod.

The project is intentionally split into two independent localization sources.

```
VH_mod/
│
├── base_game_vh/
│
├── princesofdarkness/
│
└── README.md
```

---

# Folder Structure

## base_game_vh/

This folder contains an existing Vietnamese localization for:

- Crusader Kings III base game
- Official DLCs
- Official game updates

It **does NOT contain any localization for Princes of Darkness**.

This folder is considered the project's **translation reference**.

It should be treated as:

- terminology dictionary
- writing style reference
- grammar reference
- naming reference
- translation consistency reference

Unless explicitly instructed, Claude should **NOT rewrite or change translations inside this folder.**

---

## princesofdarkness/

This folder contains the localization files of the **Princes of Darkness** mod.

Only this folder should be translated.

All new translations should follow the style established inside **base_game_vh**.

---

# Translation Priority

Whenever translating Princes of Darkness, use the following priority:

1. Existing translation in `base_game_vh`
2. Vanilla CK3 terminology
3. World of Darkness lore
4. Natural Vietnamese

Never invent a different translation if the same concept already exists in `base_game_vh`.

---

# IMPORTANT

The objective is **NOT** to create a completely new Vietnamese terminology.

The objective is to make Princes of Darkness feel like an official extension of the existing Vietnamese localization.

Players should not notice any difference between:

- vanilla CK3
- DLCs
- Princes of Darkness

Everything should read as if translated by the same translator.

---

# Translation Memory

Before translating any text, Claude should always search inside:

```
base_game_vh/
```

If an identical or equivalent string already exists, reuse that translation.

Examples:

If `Steward` is translated as

```
Quản gia
```

inside base_game_vh,

then every occurrence of

```
Steward
```

inside Princes of Darkness should also become

```
Quản gia
```

Never use alternatives like

- Tổng quản
- Nội vụ đại thần
- Quản lý

unless the game context is fundamentally different.

---

# Style Guide

The translation should imitate the style already used inside `base_game_vh`.

Maintain consistency for:

- sentence structure
- terminology
- capitalization
- punctuation
- honorifics
- medieval tone

Do not modernize the writing style.

---

# Lore Terms

Princes of Darkness introduces many concepts that do not exist in vanilla CK3.

Examples include:

- Clans
- Disciplines
- Bloodlines
- Generation
- Vitae
- Resonance
- Beast
- Masquerade
- Diablerie

When translating these:

1. Search the entire repository first.
2. Search `base_game_vh` for similar concepts.
3. If no translation exists, create a new one that matches the style of `base_game_vh`.
4. Reuse that translation consistently everywhere afterward.

---

# Consistency Rules

A translated term must always remain identical.

For example:

```
Scheme
```

must always be translated the same way.

Do not alternate between

- Âm mưu
- Kế hoạch
- Mưu kế

unless the English source is actually different.

---

# CK3 Localization Rules

Never modify:

- localization keys
- script variables
- formatting
- color tags
- icons
- placeholders

Only translate visible text.

Correct:

```yaml
trait_brilliant:0 "Thiên tài"
```

Incorrect:

```yaml
trait_genius:0 "Thiên tài"
```

(localization key changed)

---

# Workflow for Claude

For every file:

1. Read the original localization.
2. Search `base_game_vh` for identical terminology.
3. Reuse existing translations whenever possible.
4. Translate only new Princes of Darkness concepts.
5. Preserve all CK3 localization syntax.
6. Never modify file structure.

---

# Project Goal

The final result should feel like:

> Princes of Darkness was officially localized by the same team that translated Crusader Kings III.

A player switching between vanilla CK3 and Princes of Darkness should experience a seamless and consistent Vietnamese localization.