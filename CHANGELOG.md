# Changelog

All notable changes to `nika-design-skill` are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [0.1.0] — 2026-04-14

### Added — initial public release

- `SKILL.md` — Claude Code skill frontmatter + workflow. Anti-trigger description forbids auto-invocation on generic UI. Output contract includes mandatory self-audit footer.
- `PRINCIPLES.md` — 15 non-negotiable rules covering dark-only, 90/10 restraint, labeling discipline, monospace hegemony, chromatic punch, typography hierarchy, motion, dithered textures, ethical Japanese borrowing, pirate voice, anti-slop firewall, forbidden fonts, asymmetric layout, annotations-over-animations.
- `DESIGN.md` — single-source-of-truth design system (~3000 words). Publishable standalone at [nika.sh/design.md](https://nika.sh/design.md) for AI-agent consumption. Registry-compatible frontmatter for getdesign.md / VoltAgent/awesome-design-md.
- `tokens/colors.css` — OKLCH palette with hex fallbacks. Dark-only (no light mode). Electric blue `#3BE8FF`, amber `#FFB000`, lichen green `#7DAA6E`, on near-black `#05070A`. Crimson `#E63946` reserved for error states.
- `tokens/typography.css` — Triad A stack: Basteleur Bold (display ≥32px), Departure Mono (mono workhorse), Recursive Sans Linear (body), JGS Font (ASCII frames). Fluid `clamp()` scale. OT features `tnum`, `zero`, `ss01` enabled by default on mono. Forward-compatible pre-token for Berkeley Mono paid upgrade.
- `tokens/spacing.css` — 8px base, annotation gutter first-class, radii capped at 6px.
- `tokens/motion.css` — two easing curves (slow zoom + instant cut), six durations, banned-pattern documentation, respects `prefers-reduced-motion`.
- `references/cinema.md` — Ghost in the Shell / Akira / Evangelion / Daft Punk analysis with transferable techniques and 20 shippable moves.
- `references/forbidden.md` — AI-slop firewall with concrete bans across visual effects, fonts, layouts, motion, typography, iconography, copy, and Japanese-adjacent patterns.
- `references/licenses.md` — license tracking per font, flagged for live verification in v0.1.1.
- `README.md` — human-readable pitch, install, canonical links.
- `LICENSE` — AGPL-3.0-or-later (GNU Affero General Public License v3, full text).
- `.gitignore` — standard editor/OS ignores.

### Design decisions locked

- **Triad A** chosen over alternatives (Redaction/Iosevka/Sligoil). Basteleur + Departure + Recursive + JGS.
- **Nabla dropped** from v0.1 — tonal mismatch with cyberpunk-brutalist brief. Wow-glyph slot stays empty until v0.2 Cirrus Cumulus evaluation.
- **No Tailwind as skill output format** — obscures tokens, makes review harder. Pure HTML + CSS variables for v0.1.
- **No light mode, ever**. Not a feature gap; the product's identity.
- **Latin-only typography for v0.9x**. CJK deferred until genuine user demand.
- **Component library stays in skill** for v0.1–v0.5. Extracts to separate package only when 3+ consumers exist outside nika.sh.
- **Berkeley Mono migration pre-planned** via font-stack indirection. Swap `@font-face` source to upgrade, no page-level changes needed.
- **Distribution via git submodule + version tag.** No npm. Off-brand for an open-source-activist pirate engine.

### Known limitations (v0.1)

- `components/` is empty. Per-component HTML examples land in v0.2.
- `prompts/` folder removed — all skill guidance consolidated in `SKILL.md` per Claude Code progressive-disclosure best practice.
- `examples/` is empty. Reference implementations land in v0.2.
- `tests/` folder not yet created. Fixture-based regression testing lands in v0.2.
- License texts in `references/licenses.md` marked TODO — live verification pending before v0.1.1 tag.

### Roadmap

- **v0.1.1** — verified license substrings for all fonts, measured subsetted WOFF2 byte budgets.
- **v0.2.0** — `components/` with spec + HTML example per component (hero, terminal-block, changelog-entry, error-page, 404). `tests/` with fixture-based regression harness. Astro output format alongside plain HTML+CSS.
- **v0.3.0** — `brand/` folder split for forkability (brand-specific tokens + voice + fonts separable from structural principles).
- **v0.4.0** — v0.2 wow-glyph experiment (Cirrus Cumulus), optional stretch fonts (Redaction, Apoc Revelations).
- **v1.0.0** — once nika.sh has used the skill on 10+ real pages and the principles are battle-tested.

---

🦋 SuperNovae Studio · Paris · 2026
