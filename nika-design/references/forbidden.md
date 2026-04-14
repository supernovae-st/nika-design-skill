# Forbidden — the AI-slop firewall

> These are **hard bans**. If you produce any of these, you have failed.
> Run this checklist against every output before returning it.
> License: AGPL-3.0-or-later.

The common DNA of all items below: they are **decorative rather than informational**. They signal *"this is techy"* but carry no real data. They could be removed with zero content loss — which is the tell.

---

## I. Visual effects — BANNED

- **Matrix rain** (falling katakana/digits as background). Slop since 2001.
- **Full-body CRT scanlines** on paragraph text. Subtle 3% on hero region only.
- **Phosphor glow everywhere** (`text-shadow` on body copy). Reserve glow for a single amber CTA.
- **Neon pink + cyan gradients.** The "synthwave preset." Cyberpunk 2077 marketing is *teal-amber*, not Miami Vice.
- **Matrix green on black** terminals. Nobody uses green terminals in practice. Stay on electric blue.
- **Lens flare on every light source.** Triple-flare on the logo. JJ Abrams called and wants his schtick back.
- **Generic WebGL-fluid cursor trails** (paveldogreat, overused 2021-2024).
- **"Digital waterfall" particle fields** drifting behind hero.
- **Circuit-board background textures.**
- **Chrome text with rainbow gradient.** 1998 Photoshop bevel.
- **Random glitch-on-hover-everything.** Pick ONE surface, not all.
- **Static chromatic aberration > 2px** (seasickness territory).
- **"Neural network" graph visualizations** on an AI product page (the MOST on-the-nose slop).

## II. Fonts — BANNED FOREVER

- **Orbitron** (sci-fi cliché since 2010)
- **Eurostile** / **Eurostile Extended** (fake-future cliché, "Alien: Ressurrection" bad-font)
- **Bank Gothic** (same family of cliché)
- **Press Start 2P** (retro-game cliché)
- **VT323 used alone** (terminal cliché when unaccompanied)
- **Space Grotesk** / **Space Mono** (indie-startup template shorthand, 2021-2025)
- **Geist** / **Geist Mono** (Vercel default, omnipresent)
- **Inter** (everyone's everywhere)
- **JetBrains Mono alone** (IDE default signal)
- **Cal Sans** (shadcn hero cliché)
- **Plus Jakarta Sans**, **Manrope**, **DM Sans**, **Work Sans**, **Satoshi** (template default fonts)
- **Pseudo-kanji Latin fonts** (Wonton, Chow Mein, Shogun) — racist kitsch from 70s American graphic design. Never.

If a font feels like it's "trying to look futuristic," it isn't. See PRINCIPLES.md §13.

## III. Layout patterns — BANNED

- **Centered-everything**: centered hero + three-column feature grid + testimonial carousel + centered CTA. The default shape of AI slop.
- **Gradient hero backgrounds** (purple→blue mesh, radial fade, "aurora"). Flat colors only.
- **Soft bevel / neumorphism / glassmorphism.** Flat planes with 1px borders.
- **Rounded corners > 6px** on cards. Our radius ceiling is 6px (see `tokens/spacing.css`).
- **Box-shadow on cards.** No shadow. 1px border communicates depth enough.
- **Bento grids with 3D hover tilts** (Apple M1 launched it, everyone copied).
- **Mouse-parallax floating cards.** WebDeveloper++ cliché.

## IV. Motion patterns — BANNED

- **Bounce / spring / elastic easing.** Any curve with overshoot.
  - Example of banned: `cubic-bezier(0.68, -0.55, 0.27, 1.55)`
- **Soft-bounce on hover.** Scale 1 → 1.05 → 1. Every SaaS dashboard. No.
- **Parallax > 0.4 multiplier.** Creates seasickness.
- **Scroll-hijacking past 3vh.** The hero pins for a beat, then releases. No more.
- **Typewriter on every h1.** ONE location per page, maximum.
- **Smooth scroll with lerp < 0.08.** Too buttery = reads as 2022.

## V. Typography patterns — BANNED

- **Gradient text** (`background-clip: text` + animated hue). Every SaaS template.
- **ALL CAPS body paragraphs.** ALL CAPS reserved for labels only (10-11px mono).
- **Letter-spacing > 0.2em** on body. Reserve wide tracking for hero display.
- **Auto-typing hero headlines.** Typewriter on the main H1 = every AI site 2023-2025.
- **Variable font animating weight on hover.** Gimmick.

## VI. Iconography — BANNED

- **Emoji as UI element** (✨🚀💎 in buttons, nav, CTAs). Emoji in body copy is OK in moderation; emoji as chrome is not.
- **Generic "tech particle" icons** (atomic symbol, neural node, cube wireframe).
- **Filled icon sets** — use stroke/outline icons only (see Lucide, Phosphor Thin).
- **Skull-and-crossbones, parrots, treasure chests, crossed cutlasses, eye patches** — pirate cosplay. Voice-only pirate, not visual. See PRINCIPLES.md §11.
- **Cartoon mascot butterfly.** Our butterfly is illustrated once, custom, restrained. Never cute-3D, never emoji 🦋 in UI.

## VII. Copy patterns — BANNED

- **Marketing-voice superlatives**: "Supercharge," "Cutting-edge," "Revolutionary," "Unleash," "10x developer."
- **Pirate cosplay**: "Ahoy matey," "Plunder yer LLMs," "Shiver me timbers," "Savvy?"
- **"AI-powered"** as a descriptor (every landing page 2023-2025).
- **"The future of X"** as hero headline. Cliché.
- **"Built for developers, by developers"** — say something specific instead.
- **Emoji bullets** (⚡ Fast · 🔥 Hot · 💎 Premium). Use Unicode geometric glyphs (▶ ◆ ●).

## VIII. Japanese-adjacent — BANNED

- **Faked kanji/katakana as decorative texture.** Characters the author cannot read, placed for "vibes." Classic weeb-slop.
- **Random katakana flavor-words** (サイバー, メモリー, システム). Over since Neuromancer.
- **Rotated fake-Japanese** (tategaki layout with meaningless content).
- **Shoji grid backgrounds, cherry blossoms, torii gates, rising-sun imagery, hanko stamps, ukiyo-e filters** on a tech product. Politically and culturally tone-deaf.

See PRINCIPLES.md §10 for the ethical borrowing pattern.

## IX. The overall tell: "this is cyberpunk" decoration

**Authentic cyberpunk is administrative.** NERV looks like a municipal water authority. GITS Section 9 looks like a tax office. Akira's command bunker looks like a 1970s Soviet hospital. Alien's Nostromo looks like a shipping firm's back-office.

The **test**: *would a civil servant in 1997 find your interface unremarkable?* If yes, you have achieved authentic cyberpunk. If no, you have slop.

**Nika should look like the developer-tooling department of a Japanese public broadcaster circa 2003.** Functional. Labeled. Slightly ugly. Totally coherent.

---

## Pre-commit gate

Before returning any generated Nika-style output, confirm **none** of sections I–VIII above appear in your code or assets. If a single item triggers, revise.

When in doubt, delete the decorative element and add a mono annotation instead. PRINCIPLES.md §15: *annotations > animations*.

🦋
