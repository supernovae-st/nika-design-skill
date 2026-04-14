# nika-design-skill 🦋

> A Claude Code skill for generating UI in the **Nika** design language —
> retro-futurist cyberpunk terminal. Ghost in the Shell × Akira × Evangelion
> × Daft Punk, filtered through a pirate open-source terminal.

Part of [SuperNovae Studio](https://github.com/supernovae-st) · AGPL-3.0-or-later

---

## What it is

A portable design system shipped as:

1. **A Claude Code skill** — drop it into `~/.claude/skills/` and Claude generates UI in Nika aesthetic on demand.
2. **A canonical `DESIGN.md`** — published at [nika.sh/design.md](https://nika.sh/design.md) for any AI agent to consume.
3. **A design reference** — humans can read it too.

The aesthetic: **dark-only, monospace-heavy, everything is labeled, restraint as signal**. 90% Linear-quiet craft, 10% shock surfaces. Electric blue and amber on near-black. A butterfly that earns every placement. A pirate voice in the words, not the visuals.

## Install (as a Claude Code skill)

```bash
git clone https://github.com/supernovae-st/nika-design-skill.git
cp -r nika-design-skill/nika-design ~/.claude/skills/
```

Invoke in Claude Code:

```
"generate this page in nika style"
"/nika-design"
"apply nika aesthetic to this component"
```

The skill explicitly **does not** auto-trigger on generic UI tasks. If you don't name Nika, it stays out of your way.

## Read it yourself

- [`nika-design/PRINCIPLES.md`](./nika-design/PRINCIPLES.md) — 15 non-negotiable rules (read first)
- [`nika-design/DESIGN.md`](./nika-design/DESIGN.md) — full design system (~3000 words, publishable standalone)
- [`nika-design/references/cinema.md`](./nika-design/references/cinema.md) — the "why": GITS / Akira / Eva / Daft Punk analysis
- [`nika-design/references/forbidden.md`](./nika-design/references/forbidden.md) — the anti-AI-slop firewall

## Canonical links

- Website: [nika.sh](https://nika.sh)
- Design system (plain markdown): [nika.sh/design.md](https://nika.sh/design.md)
- Nika (workflow engine): [github.com/supernovae-st/nika](https://github.com/supernovae-st/nika)
- Studio: [supernovae.studio](https://supernovae.studio)

## Status

`v0.1.0` — initial public release. The skill evolves with nika.sh. Expect refinement. PRs for typos + factual errors welcome; aesthetic direction is curated (not crowdsourced) per rule 16 of the [Nothing skill convention](https://github.com/VoltAgent/awesome-design-md).

## License

AGPL-3.0-or-later. See [LICENSE](./LICENSE).

You may fork, adapt, and redistribute under the same terms. If you ship a fork as a public service, you must release your modifications under AGPL as well.

🦋 SuperNovae Studio · Paris · 2026
