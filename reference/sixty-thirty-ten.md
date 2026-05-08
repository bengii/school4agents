# The 60/30/10 Method — Primer

*Source: Jake Van Clief's framework, taught at the Quantum Quill Lyceum and detailed in the "10 Skills That Replace Generic Prompts" field manual. Operationally critical for specialist design.*

---

## The method in one sentence

Most workflows decompose into three layers, in this approximate ratio: **60% traditional solutions, 30% rule-based / database / decision logic, 10% AI for parts that need genuine judgment.**

Most builders invert this and try to do 90% AI. The result: brittle, expensive, slow workflows that fail at the seams.

## Why the ratio matters

### The 60% — traditional / deterministic

Folders. File systems. Naming conventions. Path-based routing. SQL queries. Static templates. Code that returns the same output every time.

This is where most of the work actually lives. AI doesn't need to do it; AI shouldn't do it. Traditional code is faster, cheaper, more predictable.

### The 30% — rule-based / decision logic

If-this-then-that flows. Decision trees. Lookup tables. Schema validation. Gating logic. Permission checks.

AI can handle this, but doesn't need to most of the time. Hardcoded rules ARE judgment-free; coding them once is cheaper than re-prompting every time.

### The 10% — AI / genuine judgment

Synthesis. Voice / tone. Novel-case reasoning. Cross-domain analogy. Edge-case interpretation.

This is where the magic actually happens. Spending AI tokens here pays off. Spending them on the 60% or 30% wastes capability.

## How this Vetter applies the principle

The Vetter's grading rubric is 60/30/10:

### 60% — Deterministic file checks (atomic, fast, cheap)

```bash
find <specialist>/ -type f -name "*.md" | wc -l    # form check
ls -la <specialist>/                                # presence check
test -s <specialist>/identity.md                    # non-empty check
grep -r "wikilink target" <specialist>/             # link integrity
```

These are PASS/FAIL atomic claims with zero ambiguity. No judgment. No AI tokens needed.

### 30% — Rule-based logic (atomic, structured)

- Voice Wall integrity: does each platform-slot have ONE owning voice?
- ICM form compliance: are all 5 components present (or alternate-taxonomy mapping clear)?
- CONFIDENCE ladder usage: are the 5 grades named correctly?
- Cross-reference resolution: do `[wikilinks]` resolve to existing files?

Rule checks. Yes/no per claim. Some structure to evaluate but not synthesis.

### 10% — Judgment (the actual AI work)

- Up-down ratio classification (looking-up vs looking-down signatures)
- Voice integrity assessment ("does this read as one consistent register?")
- Posture inference ("UP-leaning vs DOWN-leaning")
- "What feedback did the vetter give?" — actual corrective synthesis

This is where the Vetter's intelligence lives. The other 90% is plumbing.

## Why most builders get it wrong

The dopamine of "I made AI do a thing!" is much stronger than "I wrote a script that does a thing." So builders default to AI for tasks that don't need it.

Symptoms of inverted ratio:
- LangChain workflows for what could be a 5-line bash script
- Vector databases for what could be a folder
- AI-generated SQL for what could be a saved query
- Multi-agent orchestration for what could be a function call

Each of these has a place. None of them is the default.

## How to test your own ratio

For any workflow you build, ask:
- What's deterministic? (this is your 60%)
- What's rule-based? (this is your 30%)
- What needs genuine novel judgment? (this is your 10%)

If your 10% is ballooning to 50% or 90%, you're either:
1. Building something genuinely novel (rare; congratulations)
2. Defaulting to AI for tasks that don't need it (common; refactor)

## Cross-references

- [icm-three-layers.md](icm-three-layers.md) — the complementary architectural pattern
- [icm-principles.md](icm-principles.md) — the 5-component ICM form
- [../inspiration.md](../inspiration.md) — full lineage + citations
- Jake's "10 Skills That Replace Generic Prompts" field manual — premium-tier resource at Quantum Quill Lyceum on Skool

---

*v0.1 — 2026-05-05. Public-safe primer. Adopted as Vetter grading rubric framework.*
