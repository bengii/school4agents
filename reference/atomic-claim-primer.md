# Atomic Claims — Primer

*Source material for the vetter's decomposition discipline. Public-safe layer of a primitive that has shown up across multiple agentic-engineering frontiers in 2026.*

---

## What's an atomic claim?

An atomic claim is a proposition with **a single, unambiguous truth value**. It either is or isn't. There's no "kind of." There's no "it depends on what you mean."

Bad: *"The specialist gives helpful guidance on copywriting."*
Good (decomposed): *"The specialist's `rules.md` contains 5+ rules"* + *"Each rule has a measurable outcome"* + *"Examples in `examples.md` follow each rule"* + *"The rules are documented in a way a stranger can verify cold"*

Each of those four sub-claims can be PASSed or FAILed independently with deterministic evidence. The original "helpful guidance" claim cannot be — it's a bundle.

## Why bundles fail

Bundles hide failure. Atoms surface it.

When you grade *"the specialist gives helpful guidance"* as PASS, you might be hiding three sub-claims that failed quietly. Six months later, a user discovers it doesn't actually work for their case. The PASS was wrong, but you never knew because the bundle never decomposed.

When you decompose to atoms first, then grade each — you can't hide failure. Either each atom passes (then the bundle is true) or some fail (then you know exactly where).

## The decomposition rule

For any claim a specialist makes, ask:

1. **Is this one truth-value, or several smashed together?**
2. **If decomposed, what are the smallest sub-claims?**
3. **Can each sub-claim be tested with a deterministic tool?**
4. **What evidence would PASS or FAIL it?**

If you can't answer 3-4 cleanly, the claim is still too big. Decompose further.

## Worked example

**Original claim** (specialist's `identity.md`): *"I help authors write better cyberpunk fiction by applying classical narrative structure to modern bio-cyberpunk settings."*

**Atomic decomposition:**
- A1: The specialist provides help (verb form: actionable advice)
- A2: The help concerns authors (audience check)
- A3: The help concerns cyberpunk fiction (genre check)
- A4: The mechanism is "classical narrative structure" (specific framework named)
- A5: The mechanism applies "to modern bio-cyberpunk settings" (specific subgenre)
- A6: The output is "better" cyberpunk fiction (improvement claim — needs measurable definition)

A6 is the weakest atom. "Better" is undefined. Vetter would FAIL A6 unless the specialist defines what "better" means with measurable signals.

A1-A5 are gradeable: check `examples.md` for actionable author-facing help in cyberpunk-noir bio-cyberpunk register, applying classical narrative structure. Each atom either has supporting evidence or it doesn't.

## When atoms become bundles again

Sometimes "atomic" is relative to the question. *"The specialist's identity is specific"* feels atomic. But if a vetter is grading 20 specialists, "specific" needs to be operationalised: word count? Named-stack mention? Audience precision? The atom decomposes further depending on the grading rubric.

**Rule of thumb**: an atom is small enough that a deterministic tool (read, grep, find, ls, bash-read-only) can settle it without judgment. If you'd need to think about it, decompose more.

## Where this primitive shows up

Atomic claim decomposition is the shared substrate of:

- **Verification discipline** (Disler's verifier-agent: "break every claim into the smallest atomic unit that can be independently proven or disproven")
- **Operational code** (Atomic Work Packets in gitagent-protocol PR #62: "every side effect needs an APPROVED packet before dispatch")
- **Production discipline** (DeRonin's content engine: "RETHINK ≠ reformat; one topic = N atomic platform-native posts")
- **Verification of folder-based specialists** (this vetter)

Same first principle, four altitudes. Atoms over bundles.

## Cross-references

- [observer-pattern-primer.md](observer-pattern-primer.md) — the read-only-observer architecture atomic claims live inside
- [confidence-ladder.md](confidence-ladder.md) — how atomic verifications aggregate into a CONFIDENCE grade
- [up-down-ratio.md](up-down-ratio.md) — atomic posture classification

---

*v0.1 — 2026-05-05. Public-safe layer of a primitive shipped at multiple altitudes in 2026. See cross-references for related substrate.*
