# Cinema — the why

> The transferable visual-design techniques behind Nika's aesthetic.
> Four references analyzed: Ghost in the Shell (1995), Akira (1988),
> Neon Genesis Evangelion (1995–2021), Daft Punk.

Read this to understand WHY the rules in `PRINCIPLES.md` exist. Don't copy the references literally — extract the *technique*.

---

## Meta-lesson (read first)

**Restraint is the entire aesthetic.** Eva uses five colors. Daft Punk uses five camera frames. Akira uses one red. GITS uses one rain. The designers who built these worlds did so by saying **no** to ninety percent of what was technically possible.

**Authentic cyberpunk is administrative.** NERV looks like a municipal water authority. Section 9 looks like a Japanese tax office. Akira's command bunker looks like a 1970s Soviet hospital. Alien's Nostromo looks like a shipping firm's back-office.

The test: *would a civil servant in 1997 find your interface unremarkable?* If yes, you've achieved authentic cyberpunk. If no, you have slop.

---

## 1. Ghost in the Shell (1995) — Mamoru Oshii, Production I.G

**Anchor frame**: opening credits (00:04:17–00:05:50). Red-orange katakana drifting over wireframe schematic of Motoko's cyborg assembly. Kenji Kawai bone-percussion chant.

**Typography**: **phosphor orange on deep black**. Credits kerned *wide*. Latin technical labels in Helvetica Monospaced, uppercase, with alphanumeric serials (`PROJECT 2501`, `SECTION 9`). Text used as *architectural element* — credits scroll *through* the character model as if code compiling her body.

**Palette transcribed**:
- `#0A0E14` wet-asphalt black (has blue in it)
- `#F26A1F` phosphor orange (credits, warning labels)
- `#3DB9C4` diagnostic cyan (wireframes)
- `#8A9299` zinc grey (concrete, Niihama)
- `#C7B079` sodium lamp amber (one punch)

Never saturated. Everything reads as filmed-in-drizzle.

**Layout**: composition built on **verticals**. Rain falls, credits fall, cables hang, buildings tower. Horizontal is reserved for Motoko's body at rest. Negative space is *wet* — empty areas filled with rain streaks, lens droplets, haze. Oshii never allows a truly empty frame.

**HUD (cyberbrain POV, tank chase 01:02:00)**: orange crosshair reticles with measurement ticks every 15°, version strings (`Ver 2.20 REV-C`), target boxes that **snap with 1-frame latency, not smoothly**. The jank makes it feel real. Data readouts are unreadable on purpose. Crosshairs are **thin (1px equivalent), not bold**.

**Motion signature**: "rain-traced camera" — Oshii's long slow pans at 0.5x the speed you expect.

**Web translation for Nika**: terminal output block with thin orange reticle crosshair top-right, version string top-left (`nika v0.90.0-alpha.7 REV-C`), monospace content. **1-frame snap** on state change (not CSS ease). Scroll parallax at 0.3–0.5 multiplier, never 1:1. Backgrounds carry subtle noise+wet texture (`backdrop-filter: blur(1px)` + SVG noise overlay 3%).

---

## 2. Akira (1988) — Katsuhiro Otomo (manga)

**Anchor panel**: Volume 3 page 164 — Tetsuo's arm-mutation double-page spread. Also Volume 5 p. 220, Neo-Tokyo collapse: single panel, skyscrapers tilted 12° right with motion-streak kanji spilling vertically down the gutters.

**Typography**: Otomo's kanji are **hand-inked**, heavy brush variance (thick-to-thin within a single stroke). Latin type is **custom geometric sans** mechanically stretched 120% vertically. Sound effects integrated as **structural elements** — a `ドドド` tremor runs along a building edge and becomes the building's cladding. Text-as-architecture.

**Palette**:
- `#0D0B0F` pure shadow
- `#D13C1B` Kaneda's red (motorcycle, jacket) — **the one punch**
- `#F0DFBE` paper cream (manga page tint)
- `#7A8288` concrete grey
- `#1E2A38` Neo-Tokyo night blue

**Layout**: **diagonal compositions obsessively**. Almost no horizon is level. Panels break grids to create momentum: a motorcycle crossing a 9-panel page has one panel **bleed across three gutters diagonally**. Rhythm: **dense → dense → dense → empty single-image spread**. Pacing is the design.

**HUD**: clinical and medical. Colonel's command center uses **graph-paper backgrounds with white-on-black oscilloscope traces**, hand-drawn tick marks, no anti-aliasing. Akira's frozen-storage readouts **typed on a 1970s IBM Selectric** — serif monospace, not sans. *Slightly wrong, slightly old.* That's what makes it feel researched, not imagined.

**Motion signature**: "lens flare whip" — Kaneda's bike leaves red trail streaks with CRT-style horizontal smear.

**Web translation for Nika**: **density-rhythm layout**. Three dense sections + one single-image ceremonial break (a quote, a logo, a silence). Diagonals at ±6° to ±12°, never 45°. Use Kaneda-red (`--nika-crimson`) as single accent on a greyscale-warm page — never alongside cyan/amber/lichen. Transitions with motion-blur + 2-4px horizontal chromatic aberration decaying over 180ms.

---

## 3. Neon Genesis Evangelion — the NERV console is king

**Anchor frame**: Episode 08, 00:12:40 — MAGI system voting display. Also End of Evangelion 00:42:30 Human Instrumentality diagram.

**Typography (the secret)**: Anno used **MS PGothic** and **Matisse-EB** for NERV interface text. **MS PGothic is a system default Windows Japanese font from 1995, not a designer font. It looks like a spreadsheet. That is the point.** NERV feels real because it is typographically *ugly* — it looks like a government agency's intranet, not a film prop. Large display: Matisse-EB (thick brush Japanese face). English: plain Helvetica Bold condensed. No creative fonts. No flourishes.

**Palette**:
- `#000000` pure black (rare in anime)
- `#E8472A` Eva warning red
- `#F5B300` caution amber
- `#FFFFFF` pure white text
- `#6CA03C` MAGI terminal green (when diagnosis is nominal)

**Five colors. No gradients. Flat fills.**

**Layout**: **split-screen everything**. NERV displays are **grids of 4, 6, 9, 12 panels** — never a single image. Each panel has its own header label, timestamp, and version string. Text orbits subjects: a mecha schematic centered surrounded by 14 floating labels with **thin leader lines**. Alignment is **strictly orthogonal** — nothing tilts (unlike Akira). Eva is *bureaucratic precision*.

**Five NERV/MAGI moves to steal**:

1. **MAGI voting screen (Ep 13, 00:15:20)** — three boxes `CASPER / MELCHIOR / BALTHASAR`, each with voting state. Web translation: **3-column status grid** for provider parity (e.g., `CLAUDE / OPENAI / GEMINI` — `OK / OK / PENDING`). Big flat color fills per state.
2. **A.T. Field warning (Ep 19)** — red-on-black full-screen warning with **giant "WARNING"** bilingual. Web: error boundary / 5xx page design.
3. **Sync ratio display (Ep 02, 00:09:10)** — numeric percentage in **huge type, frame-counter style, fixed-width digits**, subtle scanline. Web: benchmark/mutation-score big-number callout.
4. **Terminal Dogma schematic (Ep 22)** — **isometric cross-section with labeled depths** (`-4200m BETHANY BASE`). Web: architecture page with crate-layer cross-section, labeled depths (L0, L1, L2…).
5. **Episode title card** — single kanji + English translation, extreme black-and-white, hard cut. Web: section transitions with hard cut + fixed-position mono-sans glyph.

**Motion signature**: **hard instant cuts + slow organic zooms + typewriter text reveals**. Anno used 3-second static frames. **Stillness is content.** No smooth transitions. No ease-in-out-quart. Jump-cut or nothing.

**Web translation for Nika**: the *entire* Nika interface should feel like MAGI. **Flat colors. Spreadsheet precision. Ugly-on-purpose mono font. Hard cuts between sections. No hover animations longer than 80ms. The design should feel *administrative* — like reading a regulatory filing, not a portfolio.**

---

## 4. Daft Punk — ceremonial grid

**Anchor**: Random Access Memories interview series (2013). Each collaborator (Moroder, Rodgers, Edwards) filmed in **single fixed frame**, 65mm, **precise symmetrical composition**, helmets visible in reflection.

**Typography**: Daft Punk's canonical type is **chrome serif** (RAM logotype = custom ITC Caslon with aggressive mirror polish). Contrasting: **Discovery-era pixel-grid sans** (1980s arcade). The pairing — **ceremonial chrome serif + pixel mono** — is the signature: silver ritual + 8-bit machine. Electroma titles: extreme letter-spacing (tracking 200+), centered, thin weight.

**Palette (RAM era)**:
- `#0A0A0A` studio black
- `#C0C0C6` polished chrome (cool silver)
- `#8E6F2F` gold helmet (Guy-Manuel)
- `#D9D9D9` white light reflection
- `#1A2F4A` deep studio blue (lighting gel)

Only five colors. Saturation near zero. **Metallic, not chromatic.**

**Layout — "ceremonial"**: single subject, perfectly centered, **massive air around it**. RAM interviews put the musician alone in 2.35:1 frame with 40% of image as ceiling or wall. No cuts for 90 seconds. The audience is **forced to slow down**.

**Web translation for Nika**: a homepage hero with a **single centered mark, 60vh+ empty air, no CTA above the fold, zero secondary content**. One line of pixel-mono subtitle: `nika — workflow engine for AI. v0.90.0-alpha.7`.

**Chrome done right (not 1998-bevel)**: SVG text with **banded gradient fill** (5–7 hard stops, not smooth) + 1px black inner stroke + no outer shadow, on slightly textured dark background. For 3D chrome: R3F `MeshPhysicalMaterial` `metalness: 1.0, roughness: 0.15, clearcoat: 1.0`, envMap studio HDRI. **Never `MeshStandardMaterial`.**

---

## 5. Secondary canon — 3 picks

- **Blame! (Tsutomu Nihei)** — megastructure cross-sections with humans at 2% scale. Web: architecture diagram where viewer scrolls 8000px vertically to traverse the stack. Layer labels with depth coordinates (`L0 -2400m`). **One page max.**
- **Serial Experiments Lain (1998)** — power-line silhouettes against washed sky, interface glitch as emotional state. Web: intentional analog-video artifacts (0.5px horizontal jitter, 2-frame dropout on hover, 16Hz scanline roll) as **page state** — reserve for 404/error pages only.
- **Alien (1979) — Nostromo / MU-TH-UR** — Ron Cobb's UI, green phosphor Futura, 40 columns wide, no graphics, slow typewriter. Web: `/docs` boots as green-phosphor MU-TH-UR-style terminal with typewriter reveal, then resolves to full chrome on first interaction. **One-time effect per session.**

---

## 6. Cross-cutting themes (extract for every page)

1. **Everything is labeled.** Every section header gets metadata strip: `§ 03.02 / 2026-04-14 / L1-effect`. Every figure gets a caption with a version number.
2. **Red/black/white + one chromatic punch.** Eva proves three colors feel richer than twenty.
3. **Japanese typography borrowed ethically.** Half-width Latin in katakana-width monospace rhymes geometry without appropriating script.
4. **Blueprint aesthetic done well.** SVG grid with varying line weight, origin crosshair at a meaningful point, measurement ticks with real pixel coordinates. The grid teaches you the page is a drawing.
5. **Chrome without 1998 Photoshop.** Banded gradients, 1px inner stroke, no outer shadow. R3F MeshPhysicalMaterial for 3D.
6. **Title cards.** Eva-style full-viewport card with single word + section number, held 600ms, then hard-cut dissolve.
7. **Ceremonial layout.** Daft Punk's law: if something is important, it gets the whole stage. One image. One sentence. Giant air.

---

## 7. Texture — organic overlay

One dithered texture per page minimum. Build-time pipeline:

```bash
sharp hero.jpg --resize 1440 \
  | dither-script --method atkinson --palette "#05070A,#7AB8FF,#FFB000,#7DAA6E" \
  > hero-dithered.png
```

Or runtime WebGL: Worley noise (cellular, 2nd-nearest minus 1st-nearest, thresholded) tinted lichen-green `#7DAA6E` over near-black, slowly panning at 0.01 units/sec. See `lygia/generative/worley.glsl`.

For lichen: Voronoi distance field, thresholded, 3–5 tones, dithered to locked palette. For nebula: raymarched FBM noise (desktop only, gate with `@media (min-width: 1280px)` for Lighthouse).

Never photographic. Always SVG or canvas-rendered or build-time PNG.

---

## 8. Twenty shippable moves (condensed)

1. MAGI 3-column provider parity status grid.
2. A.T. Field full-screen error boundary, bilingual `WARNING / 警告`.
3. Terminal Dogma isometric cross-section of crate architecture, 8000px scroll.
4. Episode-title-card section transitions (hard cut + section number + single Latin word).
5. Graph-paper backgrounds with real pixel coordinate annotations.
6. Kaneda-red (`--nika-crimson`) as single accent on greyscale-warm error page.
7. Pixel-mono benchmark numerals (mutation score, crate count, test count).
8. RAM-ceremonial founder/team page: fixed 2.35:1 frames, no hover.
9. Daft Punk chrome SVG title with banded gradient for Nika wordmark.
10. MU-TH-UR boot on first-ever visit to `/docs`, one-time.
11. GITS thin orange reticle crosshairs in terminal output blocks.
12. Tron-style 1px border panels on dark surfaces (no blur/glassmorphism — use 1px `--nika-border` + SVG noise overlay instead).
13. Hard-cut section boundaries — no scroll animations > 80ms.
14. Every section gets a technical metadata strip.
15. Typewriter reveal for homepage headline, then static forever.
16. Blame!-style scale annotations on architecture diagram.
17. Lain CRT distortion reserved for 404 / error pages only.
18. Half-width Latin in katakana-width monospace for CLI examples.
19. Akira density rhythm: three dense sections, one ceremonial silent.
20. Eva orthogonal grid labels orbiting architecture figures with 0.25px leader lines.

---

**License**: AGPL-3.0-or-later.
All references are quoted/described under fair-use for analysis. Source
works © their respective rights-holders (Production I.G, Kodansha,
Khara/Gainax, Daft Arts/Columbia).
🦋
