# CONFIDENCE Ladder — five-level grading

*The grading ladder this vetter uses. Same shape as the verifier-agent pattern (Disler) — adapted for folder-based ICM specialists.*

---

## The ladder

| Grade | Meaning | Bar color (UI convention) | Ship-ready? |
|---|---|---|---|
| **PERFECT** | Every atomic claim verified with deterministic evidence. Zero unverifiable claims. No corrective feedback needed. | 🟢 green | Yes — ships cold without modification |
| **VERIFIED** | All checked claims passed. May have 1-2 minor unverifiable claims (missing oracle, ambiguous detail) but nothing failed and the gaps don't change the outcome. | 🟢 green | Yes — ships |
| **PARTIAL** | No claims actively failed, but significant unverifiable gaps exist — multiple unverifiable claims OR a critical claim is unverifiable. The work might be correct but you can't fully prove it. | 🟠 orange | No — fix the gaps first |
| **FEEDBACK** | One or more atomic claims failed AND the vetter returned concrete corrective feedback. This is the system working as designed: a problem was found, the builder will fix it, the loop closes. | 🟠 orange | No — apply the feedback, re-grade |
| **FAILED** | The vetter cannot verify the work at all. No oracle, no fixture, ambiguous claims that can't be disambiguated, OR the specialist's structure itself is broken. Escalating to human. | 🔴 red | No — major rework needed |

## How to read each grade

### PERFECT (rare)
You shipped a folder that needs nothing. Atomic decomposition all green. Reference materials cited. Rules testable. Examples bidirectional. README cold-onboards. **Ship.**

### VERIFIED (target grade for v0.1 specialists)
You shipped a working folder. Maybe one or two minor things that aren't perfectly evidenced — but nothing that breaks cold-use. **Ship.**

### PARTIAL (most common first grade)
The bones are there. The flesh is missing somewhere — usually `reference/` is thin or absent, or examples don't cover failure modes, or the README is good-but-not-great. **Don't ship yet. The fixes are usually small.**

### FEEDBACK (active failure caught)
A specific claim failed verification AND the vetter returned a specific fix. Apply the fix. Re-grade. The loop is doing its job — you found the problem before a stranger did.

### FAILED (something is structurally wrong)
Not enough to evaluate. Files missing. Claims so vague they can't be tested. Internal contradictions. **Major rework.** Vetter will tell you what's missing.

## Honest grading discipline

The most important rule: **false PERFECT is the worst grade**. A specialist that gets PERFECT but actually fails a stranger cold has done damage — to the user, to the builder, and to the trust the grading system depends on.

Honest PARTIAL with clear gap-flags is always better than wishful VERIFIED.

The vetter picks honestly, every time. If you got PARTIAL and you wanted VERIFIED — fix the gaps. Don't argue with the grade.

## How the grade gets computed

The vetter doesn't use a numeric scoring formula. The grade emerges from:

1. **Were there any atomic-claim FAILs?** → Yes → FEEDBACK or FAILED.
2. **Were all claims VERIFIED?** → Yes → PERFECT or VERIFIED depending on unverifiables.
3. **Were there many unverifiables?** → Yes → PARTIAL.
4. **Was the structure too broken to even decompose claims?** → Yes → FAILED.

The grade reflects the worst-state across the atomic claims — not an average. One critical FAIL with eight VERIFIEDs gets FEEDBACK, not VERIFIED.

## Cross-references

- [atomic-claim-primer.md](atomic-claim-primer.md) — the units the grade aggregates over
- [observer-pattern-primer.md](observer-pattern-primer.md) — the architecture the grading lives inside
- [up-down-ratio.md](up-down-ratio.md) — separate dimension graded alongside CONFIDENCE
- Main [rules.md §"CONFIDENCE ladder"](../rules.md) — operational rules for emitting the grade

---

*v0.1 — 2026-05-05. Adapted from disler/the-verifier-agent (MIT). Public-safe.*
