# nika-design-skill — Roadmap

> Evolution plan for the Claude Code skill + canonical design system.
> Tracks alongside nika.sh (primary consumer) but ships independently.

---

## Philosophy

- **The skill is an artifact, not a product.** It doesn't need feature-creep.
- **Forkable on purpose.** `brand/` folder (v0.3+) will isolate Nika-specific tokens so the structural design principles are reusable.
- **Progressive disclosure.** Add complexity only when a specific consumer needs it.
- **AI-native.** Every addition must answer: does Claude (or another agent) actually benefit from this, or is it decorative?

---

## v0.1.0 — SHIPPED 2026-04-14 (initial public release)

- [x] `SKILL.md` with anti-trigger description + self-audit output contract
- [x] `PRINCIPLES.md` — 15 non-negotiable rules
- [x] `DESIGN.md` — ~3000 word design system, registry-ready frontmatter
- [x] Tokens in plain CSS: `colors.css` (OKLCH), `typography.css` (Triad A), `spacing.css`, `motion.css`
- [x] `references/cinema.md` — GITS / Akira / Eva / Daft Punk analysis, 20 shippable moves
- [x] `references/forbidden.md` — anti-AI-slop firewall
- [x] `references/licenses.md` — font license tracking (pending live verification)
- [x] `README.md`, `CHANGELOG.md`, `LICENSE` (AGPL-3.0-or-later)
- [x] Post-release: 4 P0 + 1 P1 fixes from 3-agent review swarm (dead refs, Nabla dropped, CRSV axis, glassmorphism contradiction, parallax ambiguity)

---

## v0.1.1 — License verification & polish (target: week +1)

- [ ] Live-verify OFL text for each font (download foundry repos, paste actual copyright lines into `references/licenses.md`)
- [ ] Measure subsetted WOFF2 byte budgets (`pyftsubset`)
- [ ] Add fallback hex values for `--nika-cyan-dim`, `--nika-amber-dim`, `--nika-lichen-dim` in `colors.css` `@supports not` block
- [ ] Fix DESIGN.md §4 spacing doc ("1..16" → "0..24" matches actual CSS scale)
- [ ] Verify VoltAgent/awesome-design-md "rule 16" reference in README, or remove if nonexistent
- [ ] Mark cinema.md's "RAM logotype = ITC Caslon" claim as unverified, cross-check

---

## v0.2.0 — Components & examples (target: month +1)

- [ ] `components/hero/` — spec.md + example.html + variants.html
- [ ] `components/terminal-block/` — spec + example + 3 variants (command, output, error, file-tree)
- [ ] `components/changelog-entry/` — spec + example
- [ ] `components/error-page/` — spec + example
- [ ] `components/404/` — spec + example
- [ ] `components/texture/` — dithered panel SVG generators (lichen, nebula, wing-scale, blue-noise)
- [ ] `examples/` folder with standalone HTML references
- [ ] `tests/` folder: 3–5 input/output fixtures for regression testing the skill

---

## v0.3.0 — Forkability via `brand/` split

- [ ] Move Nika-specific assets into `brand/`:
  - `brand/tokens/*.css` (colors, fonts, spacing, motion values)
  - `brand/voice.md` (pirate-technical voice + vocabulary)
  - `brand/references/` (cinema, moodboard, forbidden)
  - `brand/fonts/` (the actual WOFF2 files)
- [ ] Keep structural files at root (PRINCIPLES.md, SKILL.md, DESIGN.md, component specs)
- [ ] Document the fork contract: "swap `brand/`, inherit root"
- [ ] Example fork scaffold for a hypothetical `fellforge-design` (docs only, no separate repo)

---

## v0.4.0 — Astro output format

- [ ] `outputs/astro/` with working `.astro` components matching each `components/*/` spec
- [ ] Add Astro to SKILL.md frontmatter `compatibility.output_formats`
- [ ] Test with a fresh Astro project scaffold

## v0.5.0 — Tests & automation

- [ ] Formalize `tests/` with assertion harness (fixture prompt + expected HTML + diff threshold)
- [ ] Optional: GitHub Action that runs the skill through Claude Code CLI (if Anthropic ships a CLI) and reports drift
- [ ] CHANGELOG discipline: semver bump + breaking-change notice per release

---

## v1.0.0 — Battle-tested (target: ≥ 10 real pages consumed it)

- [ ] All P2 items from 2026-04-14 review closed
- [ ] Used on nika.sh, nika-docs, and at least one external site
- [ ] CONTRIBUTING.md with curation policy (following VoltAgent/awesome-design-md convention: curated, not crowdsourced)
- [ ] Published design.md at canonical URLs: https://nika.sh/design.md + submitted to getdesign.md

---

## Deferred / considering

- [ ] `outputs/next/`, `outputs/svelte/`, `outputs/vue/` (wait for actual consumer demand)
- [ ] Light-mode variant (locked NO until engine v1.0 per PRINCIPLES §1)
- [ ] Figma plugin / design-tool bridge (only if a designer joins the team)
- [ ] Video specimen / animated preview for README (probably not)
- [ ] Berkeley Mono paid upgrade path (documented in licenses.md already)

---

## Non-goals

- ❌ npm package (the project is AGPL-activist; npm implies node-toolchain dependency)
- ❌ Theme variants (shadcn-style). We have one brand. Forks swap brand/ entirely.
- ❌ CSS-in-JS or component framework dependency (plain CSS is the product)
- ❌ Screenshot gallery (it's a design skill, not a portfolio)
- ❌ Marketing site of its own (this is an artifact; nika.sh references it)

---

## Release cadence

- Patch versions (`0.1.x`): weekly if needed, small fixes
- Minor versions (`0.x.0`): when a discrete feature lands (components, Astro output, brand split)
- Major version (`1.0.0`): after battle-testing, not before

Every release: CHANGELOG entry + git tag + optional Twitter note (if significant).

🦋
