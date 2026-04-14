# Nika Design — 15 Principles

Non-negotiable. If a rule here conflicts with anything in `SKILL.md` or `DESIGN.md`, **this file wins**. If a rule here conflicts with a user request, explain the conflict, then ask.

---

## 1. Dark-only for v0.9x

No light mode until post-v1.0. Don't "just add a toggle." The aesthetic is calibrated for near-black. Light mode breaks the dither, kills the lichen, inverts the amber-on-black labels. Ship dark-only, ship confident.

## 2. The 90/10 rule — restraint is the signal

Every page is 90% Linear-quiet craft and 10% shock. Identify your single shock moment **before** composing anything else — the oversized serial number, the full-bleed lichen panel, the NIKA-042 card. Everything around the shock dials back. If everything is loud, nothing is.

## 3. Everything is labeled

Version stamps on every page footer. `LAST UPDATED 2026-04-14`. `FIG 01 — MEMORY TOPOLOGY`. `NIKA-107`. `§ 02.1 / L1-EFFECT`. `T+00:42:17`. Treat the UI like an instrument panel from the Kusanagi briefcase. Labels are not decoration — they are the design.

**Ethical basis**: every string must resolve to real data queryable from the codebase. No `LOT-A9-4421` fake IDs. If the annotation doesn't mean anything, delete it.

## 4. The butterfly earns each placement

Maximum one butterfly per page. Never decorative. It appears only when it signifies:

- Brand lockup in nav
- 404 pages (butterfly escaping the frame)
- Error state (butterfly pinned = something's wrong)
- Changelog wingtips (one per major release marker)
- Loading state (AsciiMorph taking shape, one-time per session)

If you can't justify it with a one-sentence reason, delete it. No butterfly-spray.

## 5. Monospace hegemony (and font scope)

Default = monospace (**Departure Mono** workhorse, **Basteleur Bold** display). Sans-serif (**Recursive Sans Linear**) allowed **only** for long-form reading > 200 chars. Display numerals are ALWAYS mono. Labels are ALWAYS mono ALL CAPS with 0.08em tracking. If you're reaching for a sans-serif, justify why.

**Scope constraints (hard):**

- **Basteleur Bold ≥ 32px only.** Never below. Its crystalline serifs dissolve at small sizes. Never use it for body, never for numbers, never for tables.
- **Departure Mono 11–18px preferred.** The anchor of the stack. Use for everything data-shaped: code, terminal, annotations, changelog versions, stats, tabular numerics. Tabular figures + slashed zero enabled by default.
- **Recursive Sans Linear 13–24px.** Lock axes: `MONO=0, CASL=0, CRSV=0`. Body and long-form only.
- **JGS Font** conditional-load, scoped to `.nika-ascii` / `.nika-frame` classes only.

## 6. One chromatic punch per screen

`--nika-cyan` (electric blue, primary), `--nika-amber` (warnings, NIKA-XXX codes), `--nika-lichen` (success, organic textures) — exactly **one** is hot per screen. The others present only as de-saturated outlines (≤ 30% opacity) or not at all. Never all three at full saturation on the same view. The rainbow is slop.

## 7. Typography creates hierarchy — not color, not icons

Three layers:

- **Primary** — display-mono 56–96px (Basteleur Bold or Departure Mono Display)
- **Secondary** — body-mono 14–16px (Departure Mono / Recursive)
- **Tertiary** — label-mono 10–11px (Departure Mono, ALL CAPS, 0.08em tracking)

If two elements compete, shrink or fade one. Test: squint at the screen, can you still tell what's most important? Color and icons are **banned** as primary hierarchy tools.

## 8. Motion: slow zooms, instant cuts

- Section transitions: 400–600ms, `cubic-bezier(0.16, 1, 0.3, 1)` (slow ease-out)
- State changes: 0ms (instant) or 80–150ms linear
- Hover: border luminance +20%. No translate. No scale.
- Reveal-on-scroll: opacity 0→1 over 300ms. No translate.

**Banned**: spring, bounce, elastic, overshoot. Any easing curve with visible overshoot is slop. `cubic-bezier(0.68, -0.55, 0.27, 1.55)` is forbidden.

## 9. Organic texture — one dithered panel per page minimum

Lichen, nebula, wing-scale, or blue-dither noise. Rendered as 1-bit dither (Atkinson or Bayer 8×8), never as a JPG, never photographic. Always SVG or canvas or build-time PNG with locked palette. The texture is the celluloid grain — the page feels sterile without it.

## 10. Japanese typography — borrowed ethically, never faked

Allowed:

- Katakana-width monospace (Iosevka Term, DotGothic16 Latin subset) as margin annotation at ≤ 50% opacity
- Translated, meaningful Japanese text next to its English equivalent
- Unicode geometric symbols (▶ ◆ ● ┌─┐ ①②③ ──) — culturally neutral

**Banned**:

- Faking kanji/katakana as decorative texture (classic weeb-slop)
- Pseudo-kanji Latin fonts (Wonton, Chow Mein, Shogun — racist kitsch)
- Random katakana flavor-words (サイバー, メモリー)
- Rotated Japanese text ("tategaki") without real content
- Cherry blossoms, shoji, torii, rising-sun imagery, ukiyo-e pastiche, hanko stamps

**Rule**: use Japanese glyphs only if Japanese copy exists and was authored by someone who can read it. Otherwise, rhyme with geometry (half-width Latin mono) and Unicode, not script.

## 11. Pirate voice in copy, not visuals

The pirate lives in the paragraphs: direct, technical, unmarketed, AGPL-proud, occasionally funny, never try-hard.

- ✅ "Workflows, not chat. AGPL. Runs on your laptop."
- ✅ "NIKA-042: the pirate lost the map. Check `nika keys doctor`."
- ✅ "Built by a solo pirate. Maintained in the open."
- ❌ "Supercharge your AI agents with cutting-edge workflows!"
- ❌ "Ahoy matey, plunder yer LLMs!"
- ❌ Skull icons, parrots, treasure chests, crossed cutlasses

If you're drawing a skull, delete it. The voice carries the pirate; the visuals stay straight.

## 12. No Matrix rain, no CRT on body, no phosphor glow everywhere

Subtle 3% CRT scanline on hero section only, clipped to the hero region — no full-body CRT. No Matrix falling katakana (it's been slop since 2001). No text-shadow glow on paragraphs. No RGB-split-by-default on h1. No glitch-on-everything.

Subtle chromatic aberration (0.3–0.6px) is allowed on scroll velocity peaks only, decaying within 200ms. Anything static above 2px is slop.

## 13. No forbidden fonts

Banned forever:

- **Orbitron** (sci-fi cliché since 2010)
- **Eurostile / Eurostile Extended** (fake-future cliché)
- **Bank Gothic** (same)
- **Press Start 2P** (retro-game cliché)
- **Space Grotesk / Space Mono** (indie-startup template shorthand)
- **Geist / Geist Mono** (Vercel default)
- **Inter** (everyone's everywhere)
- **JetBrains Mono alone** (IDE default)
- **Cal Sans** (shadcn hero cliché)

If a font feels like it's "trying to look futuristic," it isn't. Our font discipline is Basteleur (display) + Departure Mono (mono workhorse) + Recursive Sans Linear (long-form body) + JGS Font (ASCII blocks) + Nabla (one wow-glyph moment, COLRv1).

## 14. Layout — asymmetric, edge-anchored, deliberately unbalanced

Centered-everything is the default shape of AI slop. Ours is asymmetric:

- Large-left + small-right, or the reverse
- Edge-anchored navs (not centered logos)
- Vast negative space on one side, tight grid on the other
- Balance heavy with empty, never with more heavy
- Hero left, specs right. Annotation column pinned to a margin.

The one exception: Daft Punk ceremonial hero (single centered object + 60vh air). Use sparingly.

## 15. Annotations > animations

If you're reaching for motion to make something feel "designed," you're doing it wrong. Add a margin annotation instead — a mono caption, a fig-number, a timestamp, a NIKA-XXX code. Our design feels designed because it's **labeled**, not because it moves.

---

## Self-audit checklist (run before commit)

- [ ] Dark-only (no light-mode toggle)
- [ ] 90/10 respected (one shock moment, rest calm)
- [ ] Everything labeled (versions, dates, fig-numbers, real data)
- [ ] Butterfly earns placement (or absent)
- [ ] Mono default, sans only for long-form
- [ ] One chromatic punch, not rainbow
- [ ] Type creates hierarchy, not color or icons
- [ ] Motion: slow zoom OR instant cut, no bounce
- [ ] At least one dithered texture
- [ ] No faked Japanese
- [ ] Pirate voice in copy, not visuals
- [ ] No Matrix rain / CRT-on-body / phosphor-everywhere
- [ ] No Orbitron / Eurostile / Geist / Inter / Cal Sans
- [ ] Asymmetric layout, not centered-everything
- [ ] Annotations > animations

If any fails, rewrite until all pass. No exceptions.

🦋
