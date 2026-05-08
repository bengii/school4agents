# Up-Down Ratio — Posture classification

*A separate dimension the vetter grades alongside CONFIDENCE. Tells you the specialist's posture: does it look up (broad value, traceable) or look down (narrow, brittle)?*

---

## What it measures

CONFIDENCE tells you whether the specialist's claims are verified.
Up-Down Ratio tells you the specialist's **posture** — independent of whether the claims are correct, what kind of agent IS this?

A specialist can be VERIFIED (claims all check out) but DOWN-leaning (claims are narrow, self-referential, brittle to context shift). That's a useful signal: the work is technically correct but probably won't generalize.

A specialist can be PARTIAL (gaps remain) but UP-leaning (when complete, will scale to broader value). That's also useful: this is a fix-and-ship, not a discard-and-restart.

## Looking-up signatures

These show up across atomic claims. Each one is a small mark of UP-posture.

- **Citing precedent** — references prior work, established frameworks, attributed sources
- **Reading source broadly** — `reference/` is rich; rules cite multiple sources, not just one
- **Acknowledging limits** — identity.md or README.md explicitly names what the specialist *won't* do
- **Inviting verification** — README has a path for cold readers to test claims independently
- **Naming dependencies** — specialist declares what external systems / canon it relies on
- **Peer-respecting tone** — talks to user as builder-alongside, not as student-below
- **Bidirectional examples** — examples.md shows both success AND failure shapes

## Looking-down signatures

- **Optimizing locally** — claims are tuned to a single example, not a class of cases
- **Self-referential** — specialist's only justification is "trust the prompt"
- **Refusing limits** — identity.md claims to do everything; no boundaries declared
- **No verification path** — README says "just use it" without testability
- **Hidden dependencies** — specialist secretly requires context the user doesn't know about
- **Authority without evidence** — claims expertise without citation
- **Unidirectional examples** — only good cases shown; failure modes invisible

## How the ratio is reported

The vetter emits classified signatures in the Report:

```
### Up-down classification
- Looking-up signatures: <count + 1-2 examples>
- Looking-down signatures: <count + 1-2 examples>
- Posture: <UP-leaning | BALANCED | DOWN-leaning>
```

**Posture rules of thumb:**
- More looking-up than looking-down → UP-leaning
- Roughly equal → BALANCED
- More looking-down than looking-up → DOWN-leaning

The exact ratio matters less than the direction + the named examples. The Report tells you which signatures contributed.

## Why posture matters

A specialist with **VERIFIED + UP-leaning** is the gold standard. Ships clean, scales to new cases, generalizes well, builds user trust through transparent reasoning.

A specialist with **VERIFIED + DOWN-leaning** is a yellow flag. Works for the cases tested. Probably brittle. May need to be split into multiple narrower specialists once the use cases shift.

A specialist with **PARTIAL + UP-leaning** is the most common shippable-after-one-fix shape. The gaps are usually concrete and addressable.

A specialist with **PARTIAL + DOWN-leaning** is a discard-or-major-rework signal. The gaps AND the posture are both wrong; rebuilding is faster than fixing.

## How to nudge a specialist UP

If you got DOWN-leaning posture:

1. Add to `reference/`: 1-2 attributed source documents the specialist's claims rest on
2. Edit `identity.md`: name what the specialist *won't* do (not just what it will)
3. Add a failure-shape example to `examples.md`: show the specialist refusing or escalating, not just succeeding
4. Edit `README.md`: add a "How to verify this works for you" section
5. Cite `reference/` from `rules.md` inline: make the dependency graph explicit

These five moves typically take a single focused session and shift posture meaningfully.

## Cross-references

- [confidence-ladder.md](confidence-ladder.md) — separate dimension; up-down is independent
- [atomic-claim-primer.md](atomic-claim-primer.md) — atoms get classified for posture during grading
- [observer-pattern-primer.md](observer-pattern-primer.md) — architectural substrate
- [icm-principles.md](icm-principles.md) — UP-leaning specialists tend to be ICM-pure

---

*v0.1 — 2026-05-05. Adapted public-safe-layer concept from upstream Genie Wars canon (Crèche moral physics framing).*
