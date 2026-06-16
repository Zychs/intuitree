Updated Aggregated Feature Specification: Intuitree Adaptive Visualizer
Module: intuitree (Sesefus Suite – Version Control)
Feature Title: Adaptive Scope-Aware Radial Branch Visualizer with Split-View Sandboxing and Commit/Omit Gating
Purpose: Provide an intuitive, reliable visualization and exploration interface that supports safe, throw-away experimentation while preserving full user capabilities and maintaining workflow continuity.
Core Components and Integration (Updated)

Enumeration and Scope Detection Engine
Retains prior behavior: efficient directory enumeration, scope-signal detection (folder/file names, content patterns), dynamic scope model updates, and non-intrusive tagging (.intuitree-index metadata with timestamps, content hashes, and extracted scopes).
Incremental read-triggered rescans remain active.

Interactive Radial Visualizer
Radial (“starburst”) layout with central root node and radiating branches.
Click-to-re-root behavior with dynamic remapping, pruning, and expansion of accessible branches.
Relate Mode (SSOT anchoring) and Habit / Staged Fork Mode (parallel change paths) fully supported.
Scope overlays and color-coded derivation lanes.

Split-View Sandboxing (New)
Easy Split Mechanism: The visualizer window supports a one-action split into two synchronized or independent views within the same window (e.g., side-by-side panes or tabbed split).
Primary view: Main workspace / current root and scope.
Secondary view: Sandboxed remote or experimental context.

Sandbox Abstraction:
The secondary view operates as a lightweight, isolated sandbox (leveraging existing Sesefus constructs such as isolated worktrees, sidecar subagents, or constrained derivation lanes).
This enables throw-away experiments (e.g., testing scope changes, branch re-rooting, or derivation hypotheses) without affecting the primary view or main repository state.
Sandboxing is abstracted: users interact with it as a natural extension of the visualizer rather than a separate tool or environment.

Gating and Persistence:
The split window remains open and active until the sandbox explicitly returns a commit (merging validated changes back into the primary scope or a staged fork) or an omit (discarding the experimental changes cleanly).
This gating ensures workflow continuity—no premature closure—while preventing resource leakage or unintended state pollution.
User capabilities remain fully intact: the primary view continues normal operations (navigation, scope adjustments, indexing) during sandbox engagement.


Unified Data and Persistence Model
Index and tags are shared where appropriate but isolated for the sandbox pane.
Integration with derivation-priority-guardian for safe sidecar execution during experiments.
Compatibility with Git worktrees, INDEX junctions, SSOT hygiene, and archive relocation patterns.


Benefits and Alignment with Sesefus Vision

Safety and Experimentation: Sandboxed views lower the risk of destructive changes, making advanced features approachable for entry-level users while enabling sophisticated derivation work.
Usability: Split-view in a single window reduces context-switching overhead and supports fluid comparison between main and experimental states.
Abstraction Without Loss: Sandboxing is transparent and reversible, preserving the full power of the underlying system.
Progressive Exposure: Natural usage introduces users to Sesefus concepts such as lane isolation, scoped derivations, and commit/omit hygiene.
Performance: Split views leverage targeted indexing and incremental updates, remaining responsive even in large repositories.

This design evolves the radial visualizer and scope indexing into a cohesive, production-ready module that directly addresses the interaction model from your sketch while incorporating the new sandboxing requirements.
