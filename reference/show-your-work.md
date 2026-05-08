# Show Your Work — Primer

*Source: Austin Kleon's *Show Your Work!* (2014). Core principle adopted as Vetter discipline.*

---

## The principle in one sentence

Make the process visible, not just the polished output.

## Kleon's argument

Polished outputs hide the work. The work IS the value. By showing process, you:
- Build trust (people see HOW you got there, not just where you ended up)
- Generate audience (people relate to process more than to outputs)
- Improve via feedback (gaps become visible; corrections arrive)
- Become teachable (other people can replicate your discipline)

Don't wait until you're a master to share. Share while you're learning. The amateur showing genuine work beats the master hiding behind polish.

## How this Vetter applies the principle

### Red-face tests on disk

Before the Vetter ships publicly, it grades:
1. The content-engine folder (commit `8bfa6d5`) — result: PARTIAL with 3 named fixes
2. Itself, recursively (commit `06fc199`) — result: VERIFIED, dog food edible

Both reports are filed in `red-face-tests/` and committed to repo. Anyone can read them. The dog food is being eaten in public.

This is Show Your Work as verifier-agent discipline:
- The Vetter's own grading is publicly auditable
- Failure shapes are visible (PARTIAL on content-engine — 3 fixes named)
- Recursive integrity is demonstrated (Vetter passes its own grading)
- Honest grades over flattering grades

### Failure shapes in examples.md

[examples.md](../examples.md) shows three worked specialists:
- A FAILED specialist (Salary Negotiation Coach, 2 files, "trust me" README)
- A PARTIAL specialist (B2B CFO Emails, 4-of-5 ICM components, missing reference/)
- A VERIFIED specialist (Django Code Reviewer, all components, evidence-backed)

This isn't unusual structure for examples — but it IS unusual to ship the FAILED case as canonical. Most "examples" sections show only success shapes. We show failure shapes deliberately, because failure shapes are where builders learn the most.

### Anti-fabrication discipline

The Vetter's [rules.md](../rules.md) §"Evidence discipline" makes Show-Your-Work explicit:

> Without evidence, the verdict is unsure, not verified. I do not extrapolate. I do not assume. I do not fill in gaps with what I think the specialist probably meant.

Showing your work = showing where you DON'T know. The "What could you not verify?" field in every Report block is the Show-Your-Work moment per grading run.

## Why this matters for verification

A verifier that hides its uncertainty is worse than useless. It manufactures false confidence. Builders ship folders thinking they're VERIFIED when they're actually PARTIAL.

A verifier that shows uncertainty teaches builders:
- Where verification was confident (cite the evidence)
- Where it was uncertain (cite what's missing)
- What would close the gap (specific, actionable)

That last bullet is the gift. Fix the gap, re-grade, ship.

## How to apply Show-Your-Work to your own specialist

If you're building a folder-based specialist for the comp or for production:

1. **File your failure cases** — show what the specialist refuses to do, alongside what it succeeds at
2. **Run the specialist on itself** — recursive integrity test. If it can't grade itself, it's not done.
3. **Commit your iteration history** — git log IS the show-your-work artefact
4. **Name what you don't know** — explicit "what couldn't you verify?" sections in any Report
5. **Make corrections trackable** — corrections become file edits / PR commits, not chat patches (per Jake's templated-engineering principle)

## Cross-references

- [examples.md](../examples.md) — failure shapes deliberately filed alongside success shapes
- [../red-face-tests/](../red-face-tests/) — the Vetter eating its own dog food publicly
- [icm-principles.md](icm-principles.md) — the form the Vetter grades against
- [../inspiration.md](../inspiration.md) — full lineage + citations
- Austin Kleon's book *Show Your Work!* — short read, foundational

---

*v0.1 — 2026-05-05. Public-safe primer. Show-Your-Work is the Vetter's public-failure discipline.*
