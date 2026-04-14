# Font licenses — pending live verification

> **v0.1 status**: license strings below are based on training-data knowledge.
> Before v0.1.1 release, each must be replaced with the actual copyright line
> extracted from the font's repo/foundry `LICENSE.txt` or `OFL.txt`.

---

## Triad A — v0.1 stack

### Basteleur (Velvetyne Type Foundry)

- **Source**: https://velvetyne.fr/fonts/basteleur/
- **Designer**: Keegan Mills Cooke
- **License claimed**: SIL Open Font License 1.1 (OFL-1.1)
- **Weights shipped**: Moonlight (Regular, 400) + Bold (700)
- **Variable axes**: none (static)
- **Scope in Nika**: display/hero ONLY, ≥ 32px. Never body, never numbers.
- **TODO**: paste verified OFL copyright line from `OFL.txt` in the Basteleur repo

### Departure Mono

- **Source**: https://departuremono.com/
- **Designer**: Helena Zhang
- **License claimed**: Custom permissive (NOT OFL). Free for personal + commercial use. Redistribution permitted with attribution.
- **Weight shipped**: Regular (400) only
- **Variable axes**: none (static, bitmap aesthetic forbids interpolation)
- **Scope in Nika**: mono workhorse (body, code, terminal, annotations, labels)
- **Box-drawing coverage**: U+2500–U+257F + U+2580–U+259F shipped
- **TODO**: paste verified license from https://departuremono.com/license

### Recursive (Arrow Type)

- **Source**: https://recursive.design/ · https://github.com/arrowtype/recursive
- **Designer**: Stephen Nixon / Arrow Type
- **License claimed**: SIL Open Font License 1.1 (OFL-1.1)
- **Variable axes (5)**: MONO, CASL, wght, slnt, CRSV
- **Scope in Nika**: Sans Linear (MONO=0, CASL=0, CRSV=0) for long-form body only
- **TODO**: paste verified OFL copyright line from `LICENSE` in the Recursive repo

### JGS Font (Velvetyne)

- **Source**: https://velvetyne.fr/fonts/jgs-font/
- **Designer**: JGS (artist)
- **License claimed**: SIL Open Font License 1.1 (OFL-1.1)
- **Scope in Nika**: conditional-load, scoped to `.nika-ascii` / `.nika-frame` classes only
- **Box-drawing + ASCII**: complete U+2500–U+259F + U+2800–U+28FF (braille)
- **TODO**: paste verified OFL copyright line

---

## Dropped from v0.1

### Nabla (Google Fonts)

- **Status**: REMOVED from v0.1 stack
- **Reason**: tonal mismatch with Nika brief. Nabla is playful/3D-dimensional. Nika is flat/brutalist/terminal. Wow-glyph slot stays empty in v0.1.
- **Maybe v0.2**: Cirrus Cumulus (Velvetyne, OFL) as variable-axis wow-glyph — better tonal match.

---

## v0.2+ stretch set (document only, do not ship yet)

| Font | Foundry | Role | License claimed |
|---|---|---|---|
| **Cirrus Cumulus** | Velvetyne | variable wow-glyph | OFL-1.1 |
| **Apoc Revelations** | Collletttivo | alternate hero display | OFL-1.1 |
| **Redaction** | Forest Young | changelog/transparency accent | OFL-1.1 |
| **Apfel Grotezk** | Collletttivo | alternate body | OFL-1.1 |
| **Berkeley Mono** | US Graphics | paid mono upgrade | Commercial ($75+) |

---

## Paid upgrade path — Berkeley Mono

`--nika-font-mono` stack already lists `'Berkeley Mono'` as a pre-token after `'Departure Mono'`. If licensed, swap only the `@font-face` source — zero page-level changes needed.

**License**: Berkeley Graphics commercial. Personal ~$75, indie-commercial ~$200. See https://berkeleygraphics.com/products/berkeley-mono/

---

## Verification action item (pre-v0.1.1)

1. Clone each font's source repo.
2. Extract license text to this file (replace TODOs above with verified substrings).
3. Run `pyftsubset` on each face; record subsetted WOFF2 byte sizes.
4. Commit measurements to `tokens/typography.css` as header comments.
5. Tag v0.1.1 with licensing verified.

Budget: ~2 hours.

🦋
