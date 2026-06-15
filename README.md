# intuitree

See CLEANUP.md + derivation-external-view-2026-06-12/

Reliable "time machine" timeline of your local gh CLI .git clones (bardw only).

Exactly **one repo at a time**. Graphics take the **entire window**.

See how commits **added together** (persistent layers/strands emitted per commit) to create the compounded mess at the present end of the timeline. No sizes, no disk details — just the additive history from the real .git/logs.

Drag to scrub. Press play (or s) to watch the additions compound. h to hide everything for pure full-window viz. Everything is one file.

## What you get (for exactly one local repo)

| Thing | What it does |
|-------|--------------|
| Compounding timeline (the time machine) | Horizontal/vertical river from .git/logs. Each commit marker emits persistent visual additions (layers, strands, density) that accumulate toward the present. The right/current end shows the compounded mess built from every prior addition. |
| Replay / play | Animates the real log sequence forward — watch the mess being built commit by commit. |
| Simulate addition | Inject a hypothetical new layer at the current point to explore further compounding. |
| Legend | Short, always-visible explanation of the visual language of additions and accumulation. |
| Inspector + search | Large readable text on the selected commit (what it added to the history). Forgiving search across shas/messages in the logs. |
| Linear escape | Export the actual ordered log lines + summary of additions for the single selected repo. |
| Entire window | After picking one local dir under your bardw git tree, the timeline owns 100% of the pixels. Press h to hide every overlay for pure viz. |

## Quick start (local bardw gh clones only)

1. `cd git\intuitree`
2. `python -m http.server 5173`
3. Open the page. A centered prompt appears over the full-window canvas.
4. Click the button and pick **exactly one** local clone dir from your gh/git clones (example: `C:\Users\bardw\git\LeadLogic-Engine` or `git\Arcadiumandcircadia` or the intuitree dir itself).
5. The compounding timeline (from the real .git/logs of that repo) immediately fills the entire window. Drag to scrub the time machine. Watch how the commits added up to the mess at the present end.

No remote, no multi-repo, no sizes, no header chrome that eats space. Change repo = explicit re-pick. All text short. Linear export of the actual log + additions always available.

## Controls (cheat sheet — 5 short lines)

- Drag anywhere on the timeline → scrub the time machine (see exactly what each commit added)
- Wheel → zoom time scale around pointer
- Click a commit marker → inspector shows what it added to the compounding history
- s or play button → animate the real additions building the visible mess
- h = hide every HUD for pure full-window compounding timeline; r = reset view; Esc = clear

The picker is the only way to choose a repo and it is strictly one at a time. The tool only cares about your local gh CLI .git directories under the bardw tree. The timeline is driven directly by the logs of the chosen repo (the reliable record).

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

## Roadmap (small)

- Better subtree-aware sizing for very large repos
- Optional simple force or treemap toggle (if it stays fast and clear)
- GitHub Pages one-click hosting
- Darker high-contrast mode toggle (if needed)

Open the HTML. Drag the map. See your repo as a living field instead of a list.

---

**Tip for dyslexia:** keep this README in a second tab. The numbered sections and short table make it easy to jump back to what you need. All critical controls are also printed on the page itself in 5 lines.
