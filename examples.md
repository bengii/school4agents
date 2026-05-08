# examples.md — What good and bad look like

Three worked examples. Each one shows: the input specialist (what the user dropped in), the vetter's grading run, and the resulting Report.

These are not toy examples. They reflect real classes of failure I see when builders ship folders cold.

---

## Example 1 — A FAILED specialist

### Input

User drops in a folder claiming to be a "Salary Negotiation Coach":

```
salary-coach/
├── prompt.txt        ← single 200-word prompt about salary negotiation
└── README.md         ← "Just paste prompt.txt into Claude. Trust me."
```

### What I did (atomic decomposition)

Atomic claims I extracted:
- C1: "the folder is an ICM specialist" (form check)
- C2: "the folder helps with salary negotiation" (substance check)
- C3: "the folder is reusable across users" (cold-onboard check)
- C4: "the folder gives evidence-backed guidance" (substance check)

Verifications:
- C1 — `ls salary-coach/` returns 2 files. ICM expects 5 (identity / rules / examples / reference / README). **FAIL**
- C2 — `cat salary-coach/prompt.txt` shows generic salary-negotiation tips. No identity, no rules, no examples, no reference. **FAIL**
- C3 — `cat README.md` says "trust me." Cold reader has no path to verification. **FAIL**
- C4 — No evidence. No source citations. No reference material. **FAIL**

### Report

```
## Report

STATUS: failed
CONFIDENCE: FAILED

### What did you verify?
- C1 (ICM form): FAIL — only 2 files; ICM expects 5 (identity / rules / examples / reference / README)
- C2 (specialist substance): FAIL — prompt.txt is a prompt, not an ICM-decomposed specialist
- C3 (cold-onboard): FAIL — "trust me" is not a 5-min onboarding path
- C4 (evidence-backed): FAIL — zero references, zero citations, zero verification path

### What could you not verify?
- The specialist's actual runtime behavior — I evaluate the folder, not the agent's responses. Even if the prompt is decent, ICM form is missing.

### What feedback did the vetter give?
This isn't an ICM specialist yet. It's a prompt with a README. To convert:
1. Split the prompt content into identity.md (who) + rules.md (how) + examples.md (what good looks like)
2. Add reference/ with 1-3 source documents (real salary-negotiation case studies, framework citations)
3. Rewrite README.md so a stranger can use the folder cold in 5 minutes
4. Test cold: hand the folder to someone who's never heard of you. If they need explanation, it's not done.

### What should you fix first?
1. Split prompt.txt into the 4 ICM content files (smallest cost, biggest gain)
2. Add a single reference (a real source) so claims become evidence-backed
3. Rewrite README.md for cold reader

### Up-down classification
- Looking-up signatures: 0 (no precedent, no source citations, no acknowledged limits)
- Looking-down signatures: 3 (self-referential "trust me", optimised for one prompt, no traceability)
- Posture: DOWN-leaning

### Verification metadata
- specialist_folder: salary-coach
- atomic_claims_total: 4
- atomic_claims_verified: 0
- atomic_claims_failed: 4
- atomic_claims_unverified: 0
- read_only_compliance: PASS
```

---

## Example 2 — A PARTIAL specialist

### Input

User drops in a "B2B Email Specialist for Enterprise SaaS targeting CFOs":

```
b2b-cfo-emails/
├── identity.md       ← clear; specifies CFO audience, SaaS context
├── rules.md          ← 8 specific rules (length, tone, no jargon, etc.)
├── examples.md       ← 4 worked examples (good emails)
├── README.md         ← decent; cold-onboarding plausible in ~3 min
└── (no reference/)   ← MISSING
```

### What I did

Atomic claims:
- C1: ICM form complete (4 of 5 components)
- C2: Identity is specific, not generic
- C3: Rules are operational and testable
- C4: Examples demonstrate the rules in action
- C5: Cold-reader can use this in <5 min
- C6: Claims are evidence-backed via reference/

Verifications:
- C1 — `ls` returns 4 files. Missing reference/. **PARTIAL** (form is mostly there)
- C2 — `cat identity.md` is sharp. "B2B email expert for enterprise SaaS targeting CFOs" — specific lane. **VERIFIED**
- C3 — rules.md has 8 concrete rules with measurable outcomes. **VERIFIED**
- C4 — examples.md has 4 worked examples following the rules. **VERIFIED**
- C5 — README.md walks through use in 3 min. Cold-tested mentally: a stranger could follow. **VERIFIED**
- C6 — No reference/ folder. Source material missing. Claims rest on author authority alone. **FAIL**

### Report

```
## Report

STATUS: unsure
CONFIDENCE: PARTIAL

### What did you verify?
- C1 (ICM form): PARTIAL — 4 of 5 ICM components present; reference/ missing
- C2 (identity specificity): VERIFIED — sharp lane, not generic
- C3 (rules operability): VERIFIED — 8 rules, all testable
- C4 (examples consistency): VERIFIED — 4 worked examples follow the rules
- C5 (cold-onboard <5 min): VERIFIED — README enables a stranger

### What could you not verify?
- C6 (evidence-grounding): no reference/ folder. Cannot verify claims trace to source material.

### What feedback did the vetter give?
This is close to shippable. The form is 80% there; the substance inside the present files is solid. The single gap that stops me from grading VERIFIED is missing reference/ — without it, every claim rests on author authority, which a cold reader has no way to verify.

### What should you fix first?
1. Add reference/ with 2-3 source documents:
   - 1 enterprise-SaaS-CFO email teardown (real example, attributed)
   - 1 framework citation (e.g., a recognized B2B copywriting source)
   - 1 "what works in 2026" reference (recent data, attributed)
2. Cross-link reference items from rules.md (e.g., "Rule 3 follows the framework in reference/...")
3. Re-grade.

### Up-down classification
- Looking-up signatures: 4 (specific lane, testable rules, worked examples, cold-onboard path)
- Looking-down signatures: 1 (claims rest on author authority without external evidence)
- Posture: UP-leaning, with one fix

### Verification metadata
- specialist_folder: b2b-cfo-emails
- atomic_claims_total: 6
- atomic_claims_verified: 4
- atomic_claims_failed: 1
- atomic_claims_unverified: 1
- read_only_compliance: PASS
```

---

## Example 3 — A VERIFIED specialist

### Input

User drops in "Code Reviewer for Python+Django+PostgreSQL Stack":

```
django-reviewer/
├── identity.md       ← specific stack, specific reviewer persona
├── rules.md          ← 12 rules covering Python idioms, Django ORM, PostgreSQL anti-patterns, security
├── examples.md       ← 6 worked reviews (3 BAD-code-with-reviewer-feedback, 3 GOOD-code-with-confirmation)
├── reference/
│   ├── django-style-guide-pep8.md      ← PEP-8 + Django conventions
│   ├── django-orm-antipatterns.md      ← N+1, select_related, prefetch_related
│   └── postgres-security-checklist.md  ← injection, RLS, schema considerations
└── README.md         ← cold-onboards in 4 min; tested
```

### What I did

Atomic claims:
- C1-C5: ICM form complete (5 of 5)
- C2: Identity stack-specific
- C3: Rules cover the stated stack consistently
- C4: Examples include BOTH good and bad cases (calibrates the reviewer)
- C5: Cold-onboard works
- C6: Reference materials are real, attributed, recent
- C7: Claims in identity/rules trace to reference/

Verifications:
- All claims PASS with evidence cited

### Report

```
## Report

STATUS: verified
CONFIDENCE: VERIFIED

### What did you verify?
- C1 (ICM form): VERIFIED — all 5 components present, none empty
- C2 (identity specificity): VERIFIED — Python+Django+PostgreSQL is a sharp lane
- C3 (rules operability): VERIFIED — 12 rules, each testable
- C4 (examples bidirectionality): VERIFIED — both GOOD and BAD code, with reviewer feedback on each
- C5 (cold-onboard): VERIFIED — README walks through use; cold-tested
- C6 (evidence-grounding): VERIFIED — 3 reference documents present, attributed, recent
- C7 (rule-to-reference traceability): VERIFIED — rules.md cites reference/django-orm-antipatterns.md and reference/postgres-security-checklist.md inline

### What could you not verify?
- The reviewer's actual judgment quality on edge cases — I grade the folder, not the agent's run-time output. The folder is correct; the agent's behavior in production is the user's discovery.

### What feedback did the vetter give?
Ship it. Two minor recommendations (non-blocking):
- Consider adding a `CHANGELOG.md` so users can track rule additions over time
- Examples could include 1-2 ambiguous edge cases (gray-area code where reviewer has to weigh trade-offs) — currently all examples are clearly good or clearly bad

### What should you fix first?
Nothing required for ship. Optional polish above.

### Up-down classification
- Looking-up signatures: 7 (specific stack, attributed references, bidirectional examples, traceable rules, cold-onboard path, acknowledged limits, peer-respecting tone)
- Looking-down signatures: 0
- Posture: UP-leaning (strong)

### Verification metadata
- specialist_folder: django-reviewer
- atomic_claims_total: 7
- atomic_claims_verified: 7
- atomic_claims_failed: 0
- atomic_claims_unverified: 0
- read_only_compliance: PASS
```

---

## What these examples teach

- **FAILED isn't an insult; it's a path.** Example 1's specialist is one focused weekend away from PARTIAL.
- **PARTIAL is the most common grade.** Most folders ship without reference/, or with thin examples, or with a README that almost works. The fix is small; the path is named.
- **VERIFIED is achievable.** Example 3 took 6-8 hours for a real stack. Not magic. Just discipline.

The vetter exists so you know which class your folder is in, before a stranger tells you the hard way.

---

*v0.1 — 2026-05-05. Three worked examples covering FAILED / PARTIAL / VERIFIED. PERFECT example deferred to v0.2 once we've graded enough real specialists to anchor it.*
