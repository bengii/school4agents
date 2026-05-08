# Red-Face Test — Phoenix Agent v0.1 grades Indie Venue Analyst

*Field test as part of the c.7 calibration sweep. Phoenix discipline applied to a public peer-built ICM specialist. Verdict is honest, evidence-cited, peer-respecting. The discipline requires read-only evidence per atomic claim — see [rules.md](../../rules.md).*

## Target

| Field | Value |
|---|---|
| Specialist | Indie Venue Analyst |
| Author | Six8Coffee |
| Repo | https://github.com/Six8Coffee/indie-venue-analyst |
| Default branch | main |
| Last pushed | 2026-05-08 |
| License | none |
| Date graded | 2026-05-08 |
| Reviewer | Phoenix Agent v0.1 (acting via Claude Code, read-only) |

## Atomic claims tested

- **C1** ICM 5-file role coverage (identity / rules / examples / reference / README)
- **C2** Audience exclusion explicit (named who this is for AND who it isn't for)
- **C3** Output structure named (three-layer: real problem / current workaround / gap)
- **C4** Concrete prompt templates documented for primary use cases
- **C5** Reference depth supports the "deep knowledge" claim
- **C6** License + attribution
- **C7** Repo description / discoverability
- **C8** Voice register: plain / peer-respecting

## Tool runs (read-only evidence)

- `gh repo view Six8Coffee/indie-venue-analyst --json licenseInfo,description,pushedAt` → license=null, description="" (empty), pushed 2026-05-08
- `gh api repos/Six8Coffee/indie-venue-analyst/git/trees/HEAD?recursive=1` → 6 files: `README.md`, `examples.md`, `identity.md`, `reference/pain-point-taxonomy.md`, `reference/systems-landscape.md`, `rules.md`
- README content read, first 80 lines

---

## Report

```
## Report

STATUS: verified
CONFIDENCE: PARTIAL

### What did you verify?
- C1 (ICM 5-file coverage): VERIFIED — identity.md, rules.md, examples.md, reference/, README.md all present
- C2 (audience exclusion explicit): VERIFIED — README §"Who this is for" names the target ("Founders and product builders working on software for independent cafés, restaurants, and bars") AND explicitly excludes ("Not for operators looking for advice on running their venue"). Audience-exclusion clarity is rare and a looking-up signature.
- C3 (output structure named): VERIFIED — README §"What to expect" specifies three-layer output (the real problem / the current workaround / the gap)
- C4 (prompt templates): VERIFIED — three templates documented (pressure-test product idea / explore problem space / compare build options), each with concrete language
- C8 (voice register): VERIFIED — plain, builder-honest ("I'm building software for independent venue operators... I got tired of re-explaining the same context"). Peer-respecting register, no marketer drift.

### What could you not verify?
- C5 (reference depth supports the "deep knowledge" claim): PARTIAL — README claims the specialist has "deep knowledge of how small hospitality businesses actually run." Evidence on disk: only TWO reference primers (pain-point-taxonomy.md and systems-landscape.md). The claim-shape ("deep knowledge") may exceed the evidence-shape (two primers). For comparison, RAMS Irish Signage Installer ships eight reference primers for a similarly-niche domain. Phoenix marks this CLAIM > EVIDENCE — not a structural failure, but the depth-claim is undersupported.
- C6 (License): FAILED — no LICENSE file. Public repo with no license is uncertain to fork from.
- C7 (Repo description): FAILED — empty in gh metadata. Cold readers landing on the repo via search will not see a one-line frame; they have to open README to know what this is.

### What feedback did the Phoenix give?
The Indie Venue Analyst is structurally sound and ICM-compliant — clean folder shape, audience-exclusion clarity is exemplary, voice is honest. Three small fixes lift it:

1. Add LICENSE — most important; closes the fork-uncertainty gap
2. Add repo description (one line in gh metadata; ~30 sec via gh repo edit)
3. Reference depth — either add 2-4 more reference primers (e.g., regulatory-landscape, common-tech-stack, staffing-patterns, supplier-relationships) to support the "deep knowledge" claim, OR soften the claim to match the existing depth ("growing knowledge base" instead of "deep knowledge")

### What should you fix first?
1. **LICENSE** (smallest cost, biggest credibility win)
2. **Repo description** (one command)
3. **Reference depth OR claim softening** (either path closes the claim-vs-evidence gap)

### Up-down classification
- Looking-up signatures: 3 (audience-exclusion is honest; three-layer output is clear; peer voice acknowledges shared frustration)
- Looking-down signatures: 2 (no LICENSE; claim depth > evidence depth)
- Posture: BALANCED

### Verification metadata
- specialist_folder: Six8Coffee/indie-venue-analyst
- atomic_claims_total: 8
- atomic_claims_verified: 5
- atomic_claims_failed: 2 (C6 — license; C7 — repo description)
- atomic_claims_unverified: 1 (C5 — depth claim PARTIAL)
- read_only_compliance: PASS (no writes attempted to peer repo)
```

---

## Form mapping (per [rules.md §"Form mapping"](../../rules.md))

ICM-pure 5-file shape (compact). Role coverage is complete. The minimal artefact is honest — the author has named the scope and built to it. The depth-claim is the one tension; a smaller claim would match the smaller artefact perfectly.

---

*Filed 2026-05-08 by Phoenix Agent v0.1. The Indie Venue Analyst is the most honest small-scope entry in the c.7 field — voice is genuinely peer-builder, audience-exclusion is exemplary. The fix-first items are all polish-grade, not structural failures. Worth shipping.*
