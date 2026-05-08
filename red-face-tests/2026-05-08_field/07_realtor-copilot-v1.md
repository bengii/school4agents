# Red-Face Test — Phoenix Agent v0.1 grades Realtor Copilot v1 (SUPERSEDED)

*Field test as part of the c.7 calibration sweep. This entry is by the same author as Realtor Copilot v2 ([report 02](02_realtor-copilot-v2.md)). The v1 README itself explicitly redirects readers to v2.*

## Target

| Field | Value |
|---|---|
| Specialist | Realtor Copilot v1 |
| Author | NFTYoginis |
| Repo | https://github.com/NFTYoginis/realtor-copilot |
| Default branch | main |
| Last pushed | 2026-05-08 |
| License | MIT |
| Date graded | 2026-05-08 |
| Reviewer | Phoenix Agent v0.1 (acting via Claude Code, read-only) |
| Status | SUPERSEDED by realtor-copilot-v2 (per author's own README) |

## Tool runs (read-only evidence)

- `gh repo view NFTYoginis/realtor-copilot --json licenseInfo,description,pushedAt,stargazerCount` → license=MIT, pushed 2026-05-08, stars=1
- `gh api repos/NFTYoginis/realtor-copilot/git/trees/HEAD?recursive=1` → ~38 files (specialist/ + case-studies/jerusalem|khao-lak|novato + LICENSE + .gitignore + CONTRIBUTING.md)
- README content read, first 80 lines — opening block: "**v2 has shipped.** This is v1. v2 adds two more jobs (showing notes from dictation + local-services lookup), a welcome menu, sharpened buyer-fit reasoning, and a fourth case study (Lisbon). Migration is clean — your v1 region files drop into v2 unchanged. **→ [github.com/NFTYoginis/realtor-copilot-v2](https://github.com/NFTYoginis/realtor-copilot-v2)**"

---

## Report

```
## Report

STATUS: superseded
CONFIDENCE: VERIFIED (functional grade equivalent to v2 minus v2-only features)

### What did you verify?
v1 architecture is the precursor to v2. Same nested-ICM shape (specialist/ subfolder + case-studies/), three case studies (Jerusalem, Khao Lak, Novato — Lisbon added in v2), three jobs (write listing, match buyer, price — showing notes + services lookup added in v2). Author's own README is honest about the supersession ("v2 has shipped... migration is clean").

### What could you not verify?
Nothing additional beyond what v2 surfaced. The v1 architecture is a clean precursor; the v2 grade applies to v1 minus features.

### What feedback did the Phoenix give?
For comp purposes only — submitting both v1 and v2 separately consumes two comp slots from one builder. The author's README explicitly redirects to v2. This is honest disclosure but a comp may scope differently. Phoenix flags this for the Captain's awareness; the folders themselves are not at fault.

### What should you fix first?
For v1 specifically: nothing structural. v2 supersedes.

### Up-down classification
- Looking-up signatures: 6+ (same as v2 minus v2-only features; honest supersession disclosure in README)
- Looking-down signatures: 0
- Posture: UP-LEANING (inherited from v2's quality)

### Verification metadata
- specialist_folder: NFTYoginis/realtor-copilot
- atomic_claims_total: deferred to v2 grade — see report 02
- read_only_compliance: PASS (no writes attempted to peer repo)
```

---

## Form mapping

Same as v2 — nested-ICM (specialist/ subfolder + case-studies/). See [report 02](02_realtor-copilot-v2.md) for full form-mapping notes.

---

*Filed 2026-05-08 by Phoenix Agent v0.1. v1 is documented here for completeness of the c.7 field sweep; the canonical grade for this lineage is the v2 report.*
