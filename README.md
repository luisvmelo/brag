# /brag

> [!IMPORTANT]
> **Esta é uma cópia adaptada, não um projeto próprio.**
> Todo o mérito do `/brag` é de **[Shunit Haviv Hakimi](https://github.com/shunithaviv)** e de quem contribuiu com o projeto original, **[latent-spaces/brag](https://github.com/latent-spaces/brag)** (licença MIT): [anukulKun](https://github.com/anukulKun), [Zoroo2626](https://github.com/Zoroo2626) e [ShantanuTaro](https://github.com/ShantanuTaro). A animação é feita com o [Hyperframes](https://hyperframes.heygen.com/) (HeyGen), os efeitos sonoros são da [Kenney](https://kenney.nl/) e as músicas são da série "Happy Beats / Business Moves" da [ende.app](https://ende.app/en).
>
> A única alteração feita aqui foi ampliar o limite de duração dos vídeos de 25 s para até 90 s (1:30), para uso interno de um time. Todo o resto (código, instruções, materiais e ideia) é do projeto original. Para usar, aprender ou contribuir, prefira o [repositório original](https://github.com/latent-spaces/brag).
>
> *This is an adapted copy, not an original project. All credit for `/brag` belongs to Shunit Haviv Hakimi and the contributors of [latent-spaces/brag](https://github.com/latent-spaces/brag) (MIT License). The only change here raises the maximum video length from 25 s to 90 s for internal team use. Please use and contribute to the original repository.*

**You built it. Now brag.**

[![the /brag launch site — you built it, now brag](docs/assets/hero.png)](https://latent-spaces.github.io/brag/)

`/brag` is a Claude Code skill that turns the project you created into a short, shareable launch video — music, motion, and share copy included. One command, powered by [Hyperframes](https://hyperframes.heygen.com/).

The looping video on the [launch site](https://latent-spaces.github.io/brag/) was made by `/brag` on this very repo. 

## Install

```bash
/plugin marketplace add latent-spaces/brag
/plugin install brag@brag
```

Then run `/brag` inside any project.

**Any other agent** — one command via the [`skills`](https://github.com/vercel-labs/skills) CLI (Cursor, Codex, Copilot, Gemini CLI, opencode, and more):

```bash
npx skills add https://github.com/latent-spaces/brag --skill brag
```

Add `-g` to install globally (available in every project); drop it to scope to the current one. ([browse on skills.sh](https://www.skills.sh/latent-spaces/brag/brag))

<details>
<summary>No installer? Copy the skill directly.</summary>

```bash
rsync -a --exclude '.DS_Store' skills/brag/ ~/.claude/skills/brag/
```

Restart Claude Code after copying.
</details>

### Also works with

This repo exposes the skill at every agent's standard discovery path via symlinks. No extra config needed.

| Agent | How it discovers |
|---|---|
| **Google Antigravity** | Auto-detects from `.agents/skills/brag/` at project root or `~/.gemini/config/skills/brag/` globally |
| **opencode** | Auto-detects from `.opencode/skills/brag/` at project root |
| **Codex CLI** | Reads `.agents/skills/brag/`, walking up to repo root |
| **Claude Code** | Also reads `.claude/skills/brag/` (in addition to the `.claude-plugin/` marketplace install above) |
| **Other agents** | Point custom instructions at `skills/brag/SKILL.md` — see [`docs/other-agents.md`](docs/other-agents.md) |

> **Windows users:** Git requires `git config core.symlinks true` (or `git clone -c core.symlinks=true`) and Windows Developer Mode or Administrator privileges to create symlinks. If symlinks don't work on your system, copy `skills/brag/` to the agent's skill directory manually instead.

## Use it

From any project directory, ask your agent:

```text
let's /brag
```

Or steer the tone:

```text
/brag --tone "fake Series A launch from 2016"
```

Voiceover is off by default. Enable it explicitly with:

```text
/brag --voice
```

Narration uses Kokoro through Hyperframes when enabled.

You get a `brag-output/` folder with the plan, a composition brief, share copy, and the rendered `brag.mp4`.

## How it works

`/brag` owns the story — the product angle, tone, and which moments to show. It hands a focused brief to [Hyperframes](https://hyperframes.heygen.com/), which builds, times, and renders the video.

## Requirements

- An agent that supports Agent Skills — Claude Code, opencode, Codex CLI, or any agent with custom instructions (see "Also works with" above)
- Node.js 22+
- FFmpeg on `PATH`
- Hyperframes CLI — `npx hyperframes` (check it with `npx hyperframes doctor`)

## What's in this repo

- `skills/brag/` — the skill, references, and bundled music + SFX
- `examples/` — fake product sites used as a benchmark suite
- `docs/` — the launch site (GitHub Pages)
- `.claude-plugin/` — plugin manifest + marketplace catalog
- `.claude/skills/brag/` — symlink → `skills/brag/` (Claude Code discovery)
- `.agents/skills/brag/` — symlink → `skills/brag/` (Codex CLI + opencode discovery)
- `.opencode/skills/brag/` — symlink → `skills/brag/` (opencode discovery)

## Credits

- Music — [ende.app](https://ende.app/en) "Happy Beats / Business Moves"
- Sound effects — [Kenney](https://kenney.nl/)
- Video generation — [Hyperframes](https://hyperframes.heygen.com/)
- Fake demo sites — built with [Impeccable](https://impeccable.style/)

## Contributing

Contributions, ideas, and new demo brags are welcome — open an issue or a PR.

## Star History

<a href="https://www.star-history.com/?type=date&repos=latent-spaces%2Fbrag">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=latent-spaces/brag&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=latent-spaces/brag&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=latent-spaces/brag&type=date&legend=top-left" />
 </picture>
</a>