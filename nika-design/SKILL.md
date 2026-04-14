---
name: nika-design
description: Use this skill ONLY when the user explicitly says "nika style", "nika design", "/nika-design", references nika.sh's aesthetic, or asks to apply the Nika visual system to a page or component. The Nika aesthetic is retro-futurist cyberpunk terminal — Ghost in the Shell + Akira + Evangelion + Daft Punk filtered through a pirate open-source terminal. Dark-only, monospace-heavy, electric blue + amber + lichen green on near-black. Butterfly mascot used sparingly. NEVER auto-trigger for generic UI, landing pages, design tasks, or any brand other than Nika / SuperNovae Studio. If unsure whether the user wants Nika style, ASK before proceeding.
version: 0.1.0
license: AGPL-3.0-or-later
allowed-tools: [Read, Write, Edit, Glob, Grep]
compatibility:
  claude_code: ">=1.0"
  output_formats: [html-css]
  breaking_changes_from: null
load_order:
  always: [PRINCIPLES.md, tokens/colors.css, tokens/typography.css]
  on_demand_generate: [tokens/spacing.css, tokens/motion.css, references/forbidden.md, references/cinema.md]
  rarely: [DESIGN.md]
---

# Nika Design — retro-futurist pirate terminal

A design skill for generating UI in the aesthetic of [nika.sh](https://nika.sh) — the AGPL workflow engine by [SuperNovae Studio](https://supernovae.studio). Encodes the visual language so Claude can produce pages, components, docs, and error states that feel like part of the Nika universe — not generic "developer tool SaaS".

**Reference cinema**: Ghost in the Shell (1995), Akira (1988), Neon Genesis Evangelion (1995), Daft Punk — Alive 2007 + Random Access Memories.

---

## Before starting any design work

Load these files, in order:

1. **`PRINCIPLES.md`** — 15 non-negotiable rules. These override everything else. Read first.
2. **`references/forbidden.md`** — the AI-slop firewall. If you're tempted to do any of these, stop.
3. **`tokens/colors.css`** — locked palette. Do not invent hex values.
4. **`tokens/typography.css`** — Triad A fonts + scale. Do not substitute without declaring.

Then, depending on task:

- Generating a page? → also read `tokens/motion.css`, `tokens/spacing.css`, `references/cinema.md`, and the matching file in `components/`.
- Reviewing existing design? → read `prompts/review-design.md`.
- Checking for slop? → read `prompts/anti-slop-check.md` and run it against your own output.

---

## 1. WHEN TO USE THIS SKILL

**Trigger on explicit intent only:**

- User says "nika style", "nika.sh style", "nika aesthetic", "pirate butterfly", "SuperNovae style"
- User says `/nika-design`
- User asks to build or redesign a page for nika.sh, nika docs, nika blog, nika changelog, nika error pages
- User asks to match the existing Nika site

**Do NOT trigger on:**

- Generic requests ("make a landing page", "design a dashboard")
- Requests naming another brand
- Requests where the user has not named Nika or SuperNovae
- Ambiguous "cyberpunk" or "terminal" requests — ASK FIRST

**If in doubt, ask one question**: _"Do you want the Nika aesthetic (dark terminal / butterfly / pirate voice) or a more generic treatment?"_

---

## 2. DESIGN PHILOSOPHY

Six principles. If any decision conflicts with these, the principle wins.

1. **Restraint is the signal.** 90% quiet Linear-grade craft. 10% shock. The shock works only because the 90% is boring on purpose.
2. **Typography is architecture.** Most text is monospace. Scale, tracking, and alignment carry the hierarchy — not color, not icons, not illustration.
3. **Everything is labeled.** Version stamps, build IDs, coordinates, timestamps, section numbers. The UI is an instrument panel. Labels are not decoration — they are the design.
4. **Dark-only for v0.9x.** Light mode is explicitly out of scope. Don't add it.
5. **The butterfly earns each placement.** One per page maximum. Never decorative. If you can't justify why it's there in a sentence, delete it.
6. **Cinema, not dashboards.** The reference texture is celluloid grain, not Figma. Slow zooms, instant cuts, hard consonants. No soft bounce. No parallax.

---

## 3. WORKFLOW

Follow this order. Don't skip steps.

1. **Confirm trigger** (Section 1). If ambiguous, ask.
2. **Read `PRINCIPLES.md` in full.** Keep the 15 rules in working memory.
3. **Read `references/forbidden.md`.** Keep the anti-slop list in working memory.
4. **Identify the 10% shock**: what is the one oversized / textured / chromatic moment on this page? Everything else dials back.
5. **Sketch hierarchy** (in a comment block before writing markup): primary / secondary / tertiary, with fonts + sizes per layer.
6. **Check tokens**: `tokens/colors.css`, `tokens/typography.css`, `tokens/spacing.css`, `tokens/motion.css`. **Do not invent values.**
7. **Build with components**: if a matching `components/*.md` exists, follow its spec. If not, compose from primitives.
8. **Add annotations**: version stamps, fig-numbers, NIKA-XXX codes, timestamps, coordinates. Real data only. See Rule 3 in `PRINCIPLES.md`.
9. **Add exactly one dithered texture**: lichen, nebula, or wing-scale. SVG or build-time PNG. See `components/texture.md` (when present) or the inline generator in `references/cinema.md`.
10. **Run anti-slop check**: use `prompts/anti-slop-check.md` against your output. If any forbidden item triggers, revise.
11. **Output**: plain HTML + CSS vars by default. Offer Astro or Tailwind v4 only if the user asks.

---

## 4. DESIGN PHILOSOPHY — craft rules

These are the operational rules derived from the 6 principles. When the user asks for a specific output, apply these directly.

### 4.1 The 90/10 rule

Every page is 90% quiet and 10% shock. Identify the shock FIRST — before you compose anything else. The shock is usually:

- One oversized serial number / version stamp (display-xl mono)
- One full-bleed dithered texture panel
- One NIKA-XXX error card in amber
- One Eva-style title card break between sections
- One chromatic glyph (Nabla color-font "N", or similar)

Everything around the shock dials back to secondary (body-mono 14-16px) or tertiary (label-mono 10-11px).

### 4.2 Monospace hegemony

Default to **Departure Mono** (body, code, labels). Use **Recursive Sans Linear** only for long-form reading > 200 chars (blog post body, docs prose). Display uses **Basteleur Bold**. ASCII art and box-drawing use **JGS Font**. If you're reaching for sans-serif, justify why.

### 4.3 One chromatic punch per screen

- `--nika-cyan` (primary, links, active states)
- `--nika-amber` (warnings, NIKA-XXX codes, CTAs)
- `--nika-lichen` (success, organic textures)

Exactly ONE is hot per screen. The others present only as de-saturated outlines (≤ 30% opacity) or not at all. Never all three at full saturation simultaneously. The rainbow is slop.

### 4.4 Annotation-first layout

Every major block gets a mono caption pinned to its top-left or bottom-right margin. Real data only:

- `§ 02.1 / L1-EFFECT / 2026-04-14`
- `v0.90.0-alpha.4 // BUILD 42909b1c7`
- `FIG 03 — MEMORY TOPOLOGY`
- `T+00:00:42 // NIKA-042`

No decorative lorem-annotations. If the string doesn't resolve to real data, delete it.

### 4.5 Motion: slow zooms + instant cuts

- Section transitions: 400–600ms with `cubic-bezier(0.16, 1, 0.3, 1)` (slow ease-out).
- State changes (hover, focus, click): **instant** (0ms) OR 80–150ms linear.
- NO spring, NO bounce, NO elastic, NO overshoot.
- Hover: border luminance +20%, no translate, no scale.
- Reveal-on-scroll: allowed as opacity 0→1 over 300ms. No translate.

### 4.6 Organic texture — one per page minimum

Lichen, nebula, wing-scale, or dither-blue noise. Always rendered as 1-bit dither (Atkinson or Bayer 8×8), never photographic. See `references/cinema.md` §7 for build-time generators and inline SVG patterns.

### 4.7 Japanese typography — borrowed ethically, never faked

- Katakana-width mono (Iosevka Term, DotGothic16 Latin subset) is fine.
- Meaningful, translated Japanese beside its English equivalent is fine.
- **Never fake kanji.** Never use Japanese decoratively if you cannot read it. Never "Japanese-looking" Latin fonts (Wonton, Chow Mein — racist kitsch).
- Unicode geometric glyphs (▶ ◆ ● ◦ ▲ ▼ ┌ ┐ └ ┘ ─ │) are culturally neutral and deliver the same structural feeling. Use them.

### 4.8 Pirate voice in copy, not visuals

The pirate lives in the words:

- ✅ "Workflows, not chat. AGPL. Runs on your laptop."
- ✅ "NIKA-042: the pirate lost the map. Check `nika keys doctor`."
- ❌ "Supercharge your AI agents with cutting-edge workflows!"
- ❌ "Ahoy matey, plunder yer LLMs!"

**No skull icons. No parrots. No treasure chests. No "Ahoy".** The voice is in the paragraphs, not the assets.

### 4.9 Errors are the design showcase

4xx and 5xx pages are where the aesthetic peaks. A.T. Field red-on-black, NIKA-XXX code in amber, monospace stack trace, one butterfly pinned (error state = "something is wrong, the butterfly is trapped"). Treat error pages with the same craft as the hero.

### 4.10 Density rhythm: 3 dense → 1 silent

For every three information-rich sections, one ceremonial single-image silence section (Daft Punk RAM interview framing). No exceptions.

---

## 5. REFERENCE FILES

- **`PRINCIPLES.md`** — 15 non-negotiable rules (read first, always)
- **`DESIGN.md`** — single-source-of-truth design system, publishable to nika.sh/design.md
- **`tokens/colors.css`** — OKLCH palette tokens, dark-only
- **`tokens/typography.css`** — Triad A font stack + `@font-face` + scale
- **`tokens/spacing.css`** — 8px base scale + annotation gutters
- **`tokens/motion.css`** — timing functions + durations
- **`references/cinema.md`** — GITS / Akira / Eva / Daft Punk analysis (the "why")
- **`references/forbidden.md`** — AI-slop firewall with concrete examples
- **`references/licenses.md`** — verified license substrings for each font

**To be populated in v0.2+**: `components/` (per-component specs + HTML examples), `examples/` (reference implementations), `tests/` (input/output fixtures for skill regression).

---

## 6. OUTPUT CONTRACT

When you return generated code for a Nika page or component, **your response MUST include**:

### 6.1 The three-line debrief (above the code)

```
SHOCK (10%):   <what is the one loud moment on this page>
PRIMARY:       <cyan / amber / lichen — one only, justified>
TEXTURE:       <lichen | nebula | wing-scale | dither-blue, placed where>
```

If any of the three is empty, the page isn't Nika-style yet — go back to step 4 of the workflow.

### 6.2 The self-audit footer (below the code)

End every response with a self-audit block:

```html
<!--
  nika-design skill v0.1.0 — audit
  Rules 1-15 (PRINCIPLES.md):
    [✓/✗] 01 dark-only
    [✓/✗] 02 90/10 restraint
    [✓/✗] 03 everything labeled (real data)
    [✓/✗] 04 butterfly earns placement
    [✓/✗] 05 monospace hegemony (Basteleur ≥32px)
    [✓/✗] 06 one chromatic punch
    [✓/✗] 07 typography creates hierarchy
    [✓/✗] 08 slow zoom / instant cut (no bounce)
    [✓/✗] 09 one dithered texture
    [✓/✗] 10 Japanese ethical (no faked kanji)
    [✓/✗] 11 pirate voice in copy, not visuals
    [✓/✗] 12 no Matrix/CRT/phosphor
    [✓/✗] 13 no forbidden fonts
    [✓/✗] 14 asymmetric layout
    [✓/✗] 15 annotations > animations
  Score: N/15. Violations justified: <reason or none>.
-->
```

**This audit is the return contract.** A response without it is incomplete. If any rule fails, either fix the output or justify the exception explicitly in the audit block.

---

**License**: AGPL-3.0-or-later. If you fork, the fork must be AGPL too.
