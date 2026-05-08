# ICM Three-Layer Routing — Primer

*Source: Jake Van Clief's Interpretable Context Methodology (ICM). Research paper on rxiv. Live at the Quantum Quill Lyceum on Skool.*

---

## The three layers (Jake's framing)

ICM organizes folder-based specialists into three concentric layers:

### Layer 1 — The Router (CLAUDE.md at root)

Loaded automatically every time. Tells the agent:
- The folder map (where files live)
- Naming conventions
- Routing rules ("doing X? look in Y directory")

Think of it as the floor plan. Every room visible. Every door labeled.

### Layer 2 — The Context (per-folder context.md)

Loaded when the agent enters a specific subfolder. Tells the agent:
- What the agent should do in this room
- Which sources to read for this task
- Which skills to invoke

Layered on top of the router. Same identity, different room.

### Layer 3 — The Workspace (the actual files)

The work itself — your scripts, your drafts, your reference material, your output.

Layers 1 and 2 do the routing; Layer 3 does the work.

## Why three layers (not two, not five)

Jake's research paper details a 5-layer architecture, but he repeatedly notes that **3 is enough for most workflows**. The two extra layers (sub-skills and sub-sub-routing) are for enterprise-scale or research-grade workflows.

For folder-based specialists (the comp's target shape): **three is the canonical number**.

## How this Vetter applies the principle

The Vetter doesn't strictly use Jake's 3-layer routing because it IS a folder-based specialist (the comp's 5-file form: identity / rules / examples / reference / README), not a multi-folder workspace. But the principle holds:

| ICM Layer | Vetter analog |
|---|---|
| Router (CLAUDE.md) | [README.md](../README.md) — entry point, names the structure |
| Context (per-folder) | [identity.md](../identity.md) + [rules.md](../rules.md) — load when running |
| Workspace | [examples.md](../examples.md) + [reference/](../reference/) — the work |

When the Vetter grades OTHER specialists that use Jake's full 3-layer routing (multi-folder workspaces with router + per-folder contexts + workspace files), it grades against ICM principles directly:
- Is there a clear router? (CLAUDE.md or equivalent)
- Are per-folder contexts present where complexity demands them?
- Does the workspace separate work from routing?

## When NOT to use 3-layer routing

Single-purpose specialists (the comp's 5-file shape) don't need it. Adding 3-layer routing to a single-task folder creates complexity without leverage.

Use 3-layer routing when:
- Your workspace has multiple distinct task types
- You need to share context across subfolders
- Your folder structure is complex enough that a stranger needs a map

For a Specialist Vetter, the 5-file ICM form is sufficient. The router-context-workspace pattern is what we'd grade against, not what we'd implement here.

## Cross-references

- [icm-principles.md](icm-principles.md) — the broader 5-component ICM form (identity / rules / examples / reference / README)
- [sixty-thirty-ten.md](sixty-thirty-ten.md) — Jake's complementary methodology for what to automate vs. what to leave alone
- [../inspiration.md](../inspiration.md) — full lineage + citations
- Jake's research paper on rxiv: search "interpreted context methodology"

---

*v0.1 — 2026-05-05. Public-safe primer derived from Jake's published methodology.*
