# intuitree

Minimal intuitive navigation for a repository's spatial distribution.

Drag the map. Scroll to zoom. Click shapes. Type to search. Everything lives in one file.

## What you get

| Thing | What it does |
|-------|--------------|
| Spatial map | Files and folders as sized, colored dots in organic clusters (by top-level dir). Size = bytes. Color + shape = type. |
| Direct nav | No sidebar tree. Pan by drag. Zoom centered on pointer. Click to inspect. |
| Search | Live filter with bright rings. Forgiving, case-insensitive. |
| Inspector | Big readable card: full path, human size, plain type. Redundant visual encoding. |
| Linear escape | "export list (plain)" gives a clean indented text file — great for reading or screen readers. |
| Shareable | `?repo=owner/name` loads any public GitHub repo instantly. |

## Quick start

1. Open `index.html` directly in a browser (no build, no server needed for the demo data).
2. Or run locally:
   ```powershell
   cd git\intuitree
   python -m http.server 5173
   ```
3. Click **Demo data** for instant view.  
   Or enter `owner/repo` (public only) and hit **Load**.  
   Try `octocat/Hello-World` or any small-to-medium public repo.

## Controls (cheat sheet)

- Drag anywhere on the map → pan
- Scroll wheel or +/- keys → zoom (centered where you point)
- Click any dot or square → inspect (large text, full details)
- Type in the search box → live highlights + result count
- Press **r** → reset to clean overview
- Press **/** → focus search
- Press **Esc** → close inspector / clear search
- "export list (plain)" button → downloadable text tree

## Design notes (why it feels this way)

- High-contrast warm dark theme (adapted from other tools that work well for the author).
- Short labels and instructions everywhere. No walls of text.
- Large tap targets and generous spacing.
- Color is never the only cue: size, shape, stroke, and on-demand labels back it up.
- The map shows "distribution" — clusters respect real folders but feel spatial and organic.
- One self-contained HTML. Open it, see the graphic immediately.

## Tips for dyslexia

- The help text is deliberately 5 short bullets.
- Inspector uses ≥1 rem text and breaks paths clearly.
- Linear export is one click away if the visual map is too much on a given day.
- All controls are keyboard-reachable and labeled plainly.
- Try browser zoom at 150–200%. The canvas and text hold up.

## Technical

- Pure Canvas 2D + RAF. Culling + level-of-detail so thousands of nodes stay responsive.
- High-DPI handling for crisp text and shapes on retina/zoomed screens.
- Client-only. Fetches GitHub's public `/git/trees?recursive=1` + `/commits` + `/branches` (rate limits apply; falls back to demo).
- File spatial map + commit DAG (branches as moving tags, nodes as commits with parent edges). Layout uses simple lane + jitter for spatial feel.
- History controls (in the bar) drive the model: step/replay/simulate commit. Simulate shows actual object transitions (new commit + tree + branch advance) + ledger text. Selection pipes the commit's tree into the spatial file view.
- Legend always visible with object symbols (● commit, ◆ merge, ▣ tree, ○ blob, branch tags) and transition notes. All text short + high contrast.

## New in this release (branches, nodes, transitions)

- Toggle the commit graph panel (top-right) to see the real (or demo) DAG with branches.
- Use the history bar (prev/next/replay/simulate) — this is the control panel for the Git state.
- Simulate commit: creates a new commit node, advances a branch, updates the file map, and prints the objects that were "born".
- Click any commit node in the graph → spatial map jumps to the files at exactly that point in history.
- Full legend explains every glyph and what a transition actually mutates in git objects.

Open the HTML. Drag the map. See your repo as a living field instead of a list.

---

**Tip for dyslexia:** keep this README in a second tab. The numbered sections and short table make it easy to jump back to what you need. All critical controls are also printed on the page itself in 5 lines.