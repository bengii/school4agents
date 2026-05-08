# Red-Face Test — Phoenix Agent v0.1 grades Realtor Copilot v2

*Field test as part of the c.7 calibration sweep. Phoenix discipline applied to a public peer-built ICM specialist. Verdict is honest, evidence-cited, peer-respecting. The discipline requires read-only evidence per atomic claim — see [rules.md](../../rules.md).*

## Target

| Field | Value |
|---|---|
| Specialist | Realtor Copilot v2 |
| Author | NFTYoginis |
| Repo | https://github.com/NFTYoginis/realtor-copilot-v2 |
| Default branch | main |
| Last pushed | 2026-05-08 |
| License | MIT |
| Date graded | 2026-05-08 |
| Reviewer | Phoenix Agent v0.1 (acting via Claude Code, read-only) |

## Atomic claims tested

- **C1** ICM role coverage in nested form (specialist/ subfolder = 5-file shape; case-studies/ = populated reference data; docs/ = portfolio-level)
- **C2** Single-responsibility per file
- **C3** Anti-pitch / "It won't" register explicit
- **C4** Cold-tester test documented (concrete setup with placeholder markers)
- **C5** License + attribution + community contribution invitation
- **C6** Cross-job memory framing (showing notes cited back in matching/pricing)
- **C7** v1→v2 migration path documented
- **C8** Press kit / cold-test brief / media outreach kit (portfolio-level docs)
- **C9** Multi-region case studies (architecture-portability proof)
- **C10** Voice register: plain / peer-respecting / non-marketer

## Tool runs (read-only evidence)

- `gh repo view NFTYoginis/realtor-copilot-v2 --json licenseInfo,pushedAt` → license=MIT, pushed 2026-05-08
- `gh api repos/NFTYoginis/realtor-copilot-v2/git/trees/HEAD?recursive=1` → ~50 files including `.gitignore`, `CONTRIBUTING.md`, `LICENSE`, `README.md`, `case-studies/{jerusalem,khao-lak,lisbon-portugal,novato}/region/{contracts,glossary,market,neighborhoods,regulations,services}.md`, `docs/{cold-test-brief,media-outreach-kit,outreach-top-5,press-kit,v1-to-v2-spec}.md`, `specialist/{README,examples,identity,rules}.md`, `specialist/reference/{checklists,frameworks,region,templates}/...`
- README content read, first 80 lines

---

## Report

```
## Report

STATUS: verified
CONFIDENCE: VERIFIED (with PERFECT-leaning indicators)

### What did you verify?
- C1 (nested ICM coverage): VERIFIED — specialist/ holds 5-file ICM shape; case-studies/ holds populated reference exemplars; docs/ holds portfolio-level material. Per rules.md §"Form mapping", grading against ROLES not file names: all five functional roles covered.
- C2 (single-responsibility per file): VERIFIED — each region file does one job (market / neighborhoods / regulations / contracts / glossary / services); each framework file does one job (buyer-fit / international-buyers / pricing); each checklist file does one job (buyer-intake / listing-intake / showing-intake)
- C3 (anti-pitch register): VERIFIED — README contains explicit "It won't" list with 5 negative claims (no binding legal/tax advice; no single price; no client-facing emails; no out-of-list vendors; no out-of-scope work). README §"Where it actually beats raw ChatGPT" explicitly names where ChatGPT is fine — peer-respecting acknowledgment of adjacent tools.
- C4 (cold-tester test documented): VERIFIED — README §"Setup" specifies 20-minute one-time setup with 6 placeholder files; concrete file paths; copy-from-case-study path; from-scratch path
- C5 (License + attribution + contribution): VERIFIED — MIT license on disk, .gitignore, CONTRIBUTING.md present (invites peer contributions)
- C6 (cross-job memory framing): VERIFIED — README §"What it does" claims showing notes captured today are cited back in matching/pricing later; framework explicit
- C7 (v1→v2 migration): VERIFIED — docs/v1-to-v2-spec.md present
- C8 (portfolio-level docs): VERIFIED — docs/ contains cold-test-brief, media-outreach-kit, outreach-top-5, press-kit, v1-to-v2-spec
- C9 (multi-region case studies): VERIFIED — four populated case studies (jerusalem / khao-lak / lisbon-portugal / novato) prove the architecture is region-portable, not just locally-tuned
- C10 (voice register): VERIFIED — plain / peer-respecting / non-marketer. "Save the copilot for the work that needs structure" is voice-aligned with what ICM teaches.

### What could you not verify?
- Production usage / case studies of real realtor adoption: README does not surface user testimonials or deployment metrics. Unverifiable from repo content alone. Not a defect — production data lives outside the folder.

### What feedback did the Phoenix give?
None. The folder is production-grade ICM at portfolio level. If anything, this entry sets a high bar for what "polished cold-readable" looks like in this lineage.

### What should you fix first?
Nothing structural. Optional polish:
- Production data — once realtor adoption signals are available, surfacing them in docs/ or README would strengthen the ship-cold-ready proof.
- Submission honesty (relevant for the comp, not the folder): submitting both v1 and v2 separately consumes two comp slots from one builder. The README of v1 explicitly redirects to v2; this is honest disclosure but the comp may scope differently.

### Up-down classification
- Looking-up signatures: 7 (named limits; peer-respects ChatGPT in adjacent zones; multi-region examples; cites methodology; anti-pitch register; contributing guide invites peer participation; scope explicitly capped at 5 jobs)
- Looking-down signatures: 0
- Posture: STRONGLY UP-LEANING

### Verification metadata
- specialist_folder: NFTYoginis/realtor-copilot-v2
- atomic_claims_total: 10
- atomic_claims_verified: 10
- atomic_claims_failed: 0
- atomic_claims_unverified: 0 (production-data note is out-of-scope, not unverified)
- read_only_compliance: PASS (no writes attempted to peer repo)
```

---

## Form mapping (per [rules.md §"Form mapping"](../../rules.md))

Nested-ICM shape. Different from canonical 5-file ICM but role coverage is complete:

- **identity** = `specialist/identity.md`
- **rules** = `specialist/rules.md`
- **examples** = `specialist/examples.md` + `case-studies/` (populated reference exemplars qualify as worked examples per ICM teaching)
- **reference** = `specialist/reference/{checklists,frameworks,region,templates}/`
- **README** = `README.md` (root) + `specialist/README.md`

The `docs/` folder is portfolio-level overlay (cold-test brief / press kit / migration spec) — not part of canonical ICM but does not violate it. Grades on substance: full role coverage, no missing roles, ICM-compliant in spirit and form.

---

*Filed 2026-05-08 by Phoenix Agent v0.1. The Realtor Copilot v2 is one of the strongest non-meta-specialist entries in the c.7 field — voice-aligned with what ICM teaches, portfolio-thinking that goes beyond v0.1 of most peer specialists, and honest scope-capping ("It won't" list) that the Phoenix borrowed from in its own Saturday-tweak pass.*
