# intuitree

**Minimal intuitive navigation and spatial graphics for viewing any repository's file structure and distribution.**

> Visualize git repos the way your brain wants to see them — spatial, interactive, zero cognitive load.

## v0 Goals (this scaffold)
- Single interactive `<canvas>` experience (no heavy frameworks)
- Pan, zoom, hover tooltips
- Color nodes by file extension (ext map)
- Mock hierarchical file tree (git-like structure)
- Clean, modern UI
- Ready for real data (GitHub API or local clone) in v0.1

## Quick Start
```bash
git clone https://github.com/Zychs/intuitree.git
cd intuitree
# Just open index.html in a browser (or use a simple static server)
```

## Roadmap
- v0: Interactive canvas + mock data (done)
- v0.1: Load real repo via GitHub API or drag-and-drop .git folder
- v1: Commit history timeline + branch visualization
- v2: 3D spatial / force-directed + search + filters

## Tech
- Vanilla HTML + Canvas + JS
- Tailwind (CDN for v0)
- Zero build step

Built as part of the Grok Build/Compose ecosystem — all changes staged through T:\compose-staging\ before promotion.
