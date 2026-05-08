# Observer Pattern — Primer

*Source material for the vetter's read-only architecture. Public-safe layer of a pattern shipped independently by multiple builders in 2026.*

---

## The pattern in one sentence

A read-only agent observes a primary agent's output, decomposes claims into atomic units, evaluates each against deterministic evidence, and emits structured corrective feedback — without ever modifying the primary agent's work directly.

## Three structural commitments

1. **Read-only by tool surface** — the observer's tools include `read`, `grep`, `find`, `ls`, and read-only `bash` commands. **No `write`, no `edit`, no mutation.** This is enforced at the persona level, not the runtime level. The discipline is the observer's to honor.

2. **Top-down observation** — the primary agent doesn't know the observer exists. The observer is privileged with read-access to the primary agent's outputs (session JSONL, folder contents, etc.); the primary agent has no symmetric access. This asymmetry is the entire point.

3. **Structurally un-promptable** — the observer is not steered by user prompts mid-run. It runs against a stable persona file and a stable evaluation template. If the observer needs to be improved, you fix the persona, not the prompt.

## Why this works

Most agentic systems have one binding constraint: review. Engineers spend half their day re-checking what their primary agent did. The review is uneven, ad-hoc, prone to drift.

A read-only observer collapses that constraint into a parallel, deterministic, atomic grading run. Tokens are cheap; engineer time isn't. Spend tokens to save time.

The observer pattern compounds: every gap it surfaces becomes a template improvement. Each grading run teaches the system more about what good looks like.

## What the observer does NOT do

- ❌ Does not modify primary agent's output
- ❌ Does not propose alternative implementations
- ❌ Does not extend the primary agent's reasoning
- ❌ Does not rate the primary agent's "intent" or "creativity"
- ❌ Does not fall back to "helpful at the cost of honest"
- ❌ Does not write content for the primary agent

## Where this pattern shows up

Independent convergent implementations in 2026:

- **disler/the-verifier-agent** (2026-04-28, MIT, ~37 stars) — a Pi Coding Agent observer that watches the builder's session JSONL and prompts corrective feedback via a single `verifier_prompt` tool
- **gitagent-protocol PR #62** (2026-05-04 merged) — the ClawLaw `Atomic Work Packet` discipline encodes a structurally-constrained observer mechanic at the operational-code layer
- **This Specialist Vetter** (2026-05-05) — observer pattern applied to folder-based ICM specialists

Same architectural commitment. Different altitudes.

## How to recognize the pattern

Three smell tests for whether an agentic system is observer-pattern-compliant:

1. **The observer cannot mutate its target.** Read-only. Structural, not advisory.
2. **The observer's output is structured.** Not prose. Not a chat reply. A `## Report` block with named fields, atomic verifications, and a CONFIDENCE grade.
3. **The observer is replaceable by file edit.** If you don't like how it grades, you change the persona file, not the prompt. No falling back to vibe-coding the fix.

If a system fails any of those three, it's not really an observer; it's a chatty helper with mutation rights.

## Why this vetter is observer-shaped

Per [identity.md](../identity.md):
- The vetter has read-only tool surface (rules.md §"Tool surface")
- The vetter never modifies the specialist folder
- The vetter's output is always a structured Report (rules.md §"Output contract")
- The vetter's grading rules live in [rules.md](../rules.md), not in the chat — corrections become file edits

That's the pattern. This file is the pattern's substrate, public-safe.

## Cross-references

- [atomic-claim-primer.md](atomic-claim-primer.md) — what atoms are; what the observer decomposes
- [confidence-ladder.md](confidence-ladder.md) — how observer reports grade
- [icm-principles.md](icm-principles.md) — what ICM-pure folders look like (what the observer evaluates)

---

*v0.1 — 2026-05-05. Public-safe layer of a pattern shipped independently in 2026. The deeper substrate sits one rung up.*
