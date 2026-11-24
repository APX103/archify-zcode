# archify-zcode

[Archify](https://github.com/tt-a1i/archify) packaged as a **ZCode plugin**.

Archify turns any idea, plan, or codebase into validated, interactive HTML diagrams:

- **10 native diagram types** — architecture, workflow, sequence, dataflow, lifecycle/state, ERD, class, tree, timeline, waterfall
- **One-page explainers** — conclusion-first pages with structured panels, native diagrams and charts
- **Stories** — guided walkthrough, animated dual-theme SVG, stage player, 1080p MP4/WebM export
- **Code Analysis** — local repository architecture health, coupling, cycles, complexity hotspots
- Mermaid input accepted; output is a standalone HTML file that works offline

Everything is generated and validated locally by the bundled `bin/archify.mjs` (pure Node ≥18, no npm install needed). Each delivery passes `validate → deliver → check → browser-check` gates before it is shown.

All credit for the skill itself goes to [tt-a1i/archify](https://github.com/tt-a1i/archify) (Apache-2.0). This repo only repackages it for ZCode's plugin system; upstream license files (`LICENSE`, `LICENSE-MIT`, `NOTICE`, `THIRD_PARTY_NOTICES.md`) ship inside the skill.

## Install (ZCode)

```bash
# add this repo as a marketplace, then install the plugin
zcode plugins marketplace add APX103/archify-zcode
zcode plugins install archify@archify-zcode
```

Or in the ZCode desktop app: **Plugin Marketplace → Add → Add Plugin Marketplace**, paste `https://github.com/APX103/archify-zcode`, then install **Archify**.

## Use

After installation the `archify` skill is available in ZCode. Try:

```
Use Archify to draw: Browser -> API -> Redis cache -> PostgreSQL fallback
```

```
用 Archify 把当前仓库的构建流程画成 workflow 图
```

Diagrams land in `.archify/<type>-<slug>-<timestamp>/` under your working directory as standalone HTML.

## Update

Bump with upstream releases: sync `archify/skills/archify/` from the upstream `archify/` directory, bump the version in `.zcode-plugin/plugin.json` and `.claude-plugin/marketplace.json`, then `zcode plugins update archify@archify-zcode`.

## License

Apache-2.0, © tt-a1i and contributors (see `archify/skills/archify/LICENSE`). Packaging changes are also released under Apache-2.0.
