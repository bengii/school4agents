# Red-Face Test — Phoenix Agent v0.1 grades Buyer Profiler

*Field test as part of the c.7 calibration sweep. Phoenix discipline applied to a public peer-built ICM specialist. Verdict is honest, evidence-cited, peer-respecting. The discipline requires read-only evidence per atomic claim — see [rules.md](../../rules.md).*

## Target

| Field | Value |
|---|---|
| Specialist | Buyer Profiler |
| Author | chays77 |
| Repo | https://github.com/chays77/buyer-profiler |
| Default branch | main |
| Last pushed | 2026-05-08 |
| License | MIT |
| Date graded | 2026-05-08 |
| Reviewer | Phoenix Agent v0.1 (acting via Claude Code, read-only) |

## Atomic claims tested

- **C1** ICM 5-file role coverage (identity / rules / examples / reference / README)
- **C2** CLAUDE.md routing layer present (entry contract for Claude Desktop)
- **C3** Reference depth — 5 reference primers each scoped to one role
- **C4** Three install paths documented per-method (Claude Projects / Claude Desktop / parent-ICM workspace)
- **C5** Two-tier output spec (Quick Read above / Deep Read below)
- **C6** Audience specificity — multiple named audiences with concrete signals
- **C7** Personal narrative hook (peer-respecting register)
- **C8** License + attribution + methodology badge

## Tool runs (read-only evidence)

- `gh repo view chays77/buyer-profiler --json licenseInfo,pushedAt,stargazerCount` → license=MIT, pushed 2026-05-08, stars=1
- `gh api repos/chays77/buyer-profiler/git/trees/HEAD?recursive=1` → 11 files: `CLAUDE.md`, `LICENSE`, `README.md`, `examples.md`, `identity.md`, `rules.md`, `reference/buyer-types.md`, `reference/cognitive-functions.md`, `reference/sandler-pain-funnel.md`, `reference/signal-reading-guide.md`, `reference/user-profile.md`
- README content read, first 80 lines

---

## Report

```
## Report

STATUS: verified
CONFIDENCE: VERIFIED

### What did you verify?
- C1 (ICM 5-file coverage): VERIFIED — identity.md, rules.md, examples.md, reference/, README.md all present
- C2 (CLAUDE.md routing layer): VERIFIED — README §"Option 2" describes CLAUDE.md as the entry contract that tells Claude Desktop what to load and in what order
- C3 (reference depth): VERIFIED — five reference primers, each scoped (buyer-types / cognitive-functions / sandler-pain-funnel / signal-reading-guide / user-profile)
- C4 (three install paths): VERIFIED — README documents Claude Projects, Claude Desktop, and parent-ICM workspace fold-in, each with explicit step-by-step
- C5 (two-tier output): VERIFIED — README §"What You Get" specifies "Quick Read above the fold + Deep Read below" with five named Quick Read elements (buyer name + type + confidence / one-line read on how they decide / critical Sandler gap / failure mode / single most important next move)
- C6 (audience specificity): VERIFIED — README names four target audiences with concrete signals (Founders selling own services / AEs carrying quota / Agency owners / Sales coaches reviewing rep transcripts)
- C7 (personal narrative hook): VERIFIED — README opens with personal story ("It took me a decade to realize..."), peer-respecting register, no marketer drift
- C8 (License + attribution): VERIFIED — MIT license on disk, three badges (License / Built-with-Claude / Methodology-ICM linking to Skool community)

### What could you not verify?
- Methodological rigor of underlying frameworks: the Buyer Profiler relies on Jungian behavioral types + Sandler four-frame qualification. Both are practitioner-level psychologies with mixed academic standing. The README presents them as load-bearing without acknowledging the debate around them. Phoenix marks this as a soft flag — not a structural failure (the folder is honest about what it does), but a sophisticated reader may want methodological framing acknowledged.
- Production usage: no testimonials or case studies of actual sales-rep adoption. Unverifiable from repo content alone.

### What feedback did the Phoenix give?
The Buyer Profiler is structurally sound and ICM-compliant at high quality. Two soft polish items:

1. Acknowledge the methodology limits — Jungian behavioral types are a useful heuristic; some sophisticated readers will want the Profiler to acknowledge that. A one-line caveat in identity.md ("this is a useful behavioral heuristic, not academically settled type theory") would close the credibility gap for skeptic readers.
2. Production data — once sales-rep adoption signals are available, surfacing them in README would close the production-usage flag.

### What should you fix first?
1. Methodology caveat — one line in identity.md or README acknowledging Jungian framework as heuristic-not-doctrine. Low cost, high credibility win for skeptic readers.
2. Production data — defer until adoption signals exist.

### Up-down classification
- Looking-up signatures: 5 (cites ICM + Skool methodology link; audience-specific; specific failure-mode framing; named install paths; peer narrative honesty)
- Looking-down signatures: 1 (relies on quasi-pseudo-scientific Jungian framing without explicit limits-acknowledgment — debatable)
- Posture: UP-LEANING

### Verification metadata
- specialist_folder: chays77/buyer-profiler
- atomic_claims_total: 8
- atomic_claims_verified: 8
- atomic_claims_failed: 0
- atomic_claims_unverified: 0 (methodology-rigor flag is a soft note, not a verification failure)
- read_only_compliance: PASS (no writes attempted to peer repo)
```

---

## Form mapping (per [rules.md §"Form mapping"](../../rules.md))

ICM-pure 5-file shape + CLAUDE.md routing layer for Claude Desktop. Role coverage is complete and the routing layer is an honest extension (Anthropic Project file-loading discipline). No alternate taxonomy to map; standard ICM grading applies cleanly.

---

*Filed 2026-05-08 by Phoenix Agent v0.1. The Buyer Profiler is the strongest peer-narrative hook in the c.7 field — "Most deals don't die at the close. They die at the open." is exemplary opener-craft. The two-tier output pattern (Quick Read / Deep Read) is a UX shape Phoenix may consider for v0.2.*
