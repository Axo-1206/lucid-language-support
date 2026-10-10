# Change Log

All notable changes to the "lucid-language-support" extension will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/).

---

## [0.4.0] — 2026-10-10

Full rewrite to match the **Lucid Graph Format** grammar. The extension no longer targets the old curly-brace language (`let`/`const`, functions, structs, traits, operators, intrinsics). It now highlights the declaration-only graph format: `import`, `enum`, `resource`, `node`, `on`, `@export`.

### Changed
- **File extension:** `.luc` → `.lucid`. The `.luc` extension is deprecated and no longer registered.
- **Language icon:** replaced `lucid-logo-draft.svg` with `logo.svg`.
- **`lucid.tmLanguage.json`:** rewritten from scratch. Removed all patterns for constructs that no longer exist (functions, generics, structs, traits, control flow, async, operators, intrinsics, doc comments, raw multiline strings, unicode/hex escapes).
- **`lucid.json` (snippets):** rewritten. Old snippets (`fn`, `let`, `const`, `struct`, `trait`, `if`, `for`, `while`, `spawn`, `await`, `#alloc`, `@inline`, …) removed. New snippets cover `import`, `enum`, `resource`, `node`, `on`, `@export`, field access, enum member access, and the two comment forms.
- **`language-configuration.json`:** removed the malformed `/* … */` auto-close pair and the non-existent `#region` folding markers.
- **`package.json`:** version bumped to `0.4.0`; description updated from "the Lucid language" to "the Lucid graph format"; `Luc`/`luc` aliases dropped.

### Added
- Syntax highlighting for module qualification (`module::Type`) and field access (`Enum.Member`, `Resource.field`).
- Signed numeric literals (`-400.0`, `+7`) highlighted as single tokens, matching the grammar.
- Nestable block comments (`/- … -/`).

### Removed
- All syntax and snippets for constructs that are not part of the Lucid Graph Format.
- The `.luc` file association.

---

## [0.3.0]

### Changed
- Migrated language support from the deprecated `luc-lang` identifier to `lucid-lang`.

---

## [0.2.0]

### Changed
- All syntax and snippets updated to match the grammar as of 05/2026.

---

## [0.1.1]

### Changed
- All syntax and snippets updated to match the grammar.
- Improved icon design and icon color usage.

### Notes
- Some features may not be ready. This version is not stable; use it carefully.

---

## [0.1.0]

### Notes
- **Do not use this version.** It is corrupted. Use `0.1.1` instead.
- This version was deleted from the Marketplace.

---

## [0.0.1]

### Added
- Initial release of Lucid language support.