# ICM (Interpretable Context Methodology) — Principles

*The folder-as-architecture pattern. Source: Matthew Creamer's Quantum Quill Lyceum community + DeRonin's content-engine playbook. Both 2026 publications.*

---

## The core idea

Instead of a single bloated prompt that tries to be everything, an ICM specialist is a **folder of focused markdown files**, each doing one job, connected by `[[wikilinks]]` so an agent can traverse the graph.

## The five canonical files

| File | Job | Smell test for "done" |
|---|---|---|
| `identity.md` | **Who** the specialist is | A stranger reading it knows what the specialist won't do, not just what it will |
| `rules.md` | **How** the specialist responds | Each rule is testable; each rule has an anti-pattern named |
| `examples.md` | **What good looks like** | At least 2-3 worked examples covering different success/failure shapes |
| `reference/` | **Source material** | Source documents are real, attributed, and cited from rules/identity |
| `README.md` | **How to use** the folder | A cold reader gets value in under 5 minutes |

## The three principles

### 1. Single-responsibility per file

Each file does ONE job. If two files would say the same thing, merge them. If one file says two things, split it.

This is the analogue of single-responsibility principle in code, applied to specialist context.

### 2. Wikilinks carry intelligence

The specialist's intelligence isn't in any single file. It's in the **connections between files**. When a rule cites an example which references a source document, the agent traverses the graph and builds context the user never has to spell out.

A flat prompt = a tool. A graph of linked files = a team.

### 3. RETHINK ≠ reformat

When a specialist needs to handle a new case (different audience, different platform, different ask), the answer is not to copy-paste-and-edit. It's to **decompose the case into atomic claims** and check which existing files cover them. Maybe new rules need adding. Maybe an example needs a new variant. Maybe the identity needs sharpening.

Reformat = laziness. Rethink = engineering.

## What ICM-pure looks like

A folder you can:
1. Drop into a Claude Project (or equivalent agent harness)
2. Hand to a stranger with no context
3. Get value out of in under 5 minutes

If any of those three fail, it's not ICM-pure yet.

## Common failure modes (vetter sees these every week)

- **The single-prompt-with-a-README** — folder has 1 file pretending to be ICM. **FAILED grade.**
- **The thin specialist** — 5 files but 4 are stubs. **PARTIAL grade.**
- **The bundled identity** — `identity.md` claims 8 different things. **FAILED grade** until decomposed.
- **The reference-less specialist** — files exist but nothing cites source material. **PARTIAL grade.**
- **The chatty specialist** — rules say "be helpful and friendly" but nothing testable. **FAILED grade** on rule operability.
- **The voice-collapsed specialist** — multiple voices/registers smear across the folder; a stranger can't tell who's speaking. **PARTIAL grade.**

## How ICM intersects with the observer pattern

ICM is what good specialists LOOK like. The observer pattern (see [observer-pattern-primer.md](observer-pattern-primer.md)) is what GRADES specialists for whether they look that way.

This vetter is the observer evaluating ICM-form specialists. The two patterns work together:

- ICM gives builders a target shape
- The observer pattern lets builders verify they hit it

Both are public, both have multiple independent implementations in 2026, both rest on atomic-claim decomposition (see [atomic-claim-primer.md](atomic-claim-primer.md)).

## Cross-references

- [atomic-claim-primer.md](atomic-claim-primer.md) — ICM-pure files have atomic-claim integrity per file
- [observer-pattern-primer.md](observer-pattern-primer.md) — the architecture this vetter uses to grade ICM specialists
- [confidence-ladder.md](confidence-ladder.md) — how ICM-purity maps to grades
- [up-down-ratio.md](up-down-ratio.md) — ICM-pure specialists almost always score UP-leaning

---

*v0.1 — 2026-05-05. Public source: Matthew Creamer (Quantum Quill Lyceum) + DeRonin (content-engine playbook). This file is a primer; full source playbooks linked from main README.*
