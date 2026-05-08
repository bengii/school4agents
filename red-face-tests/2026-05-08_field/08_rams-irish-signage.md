# Red-Face Test — Phoenix Agent v0.1 grades RAMS Irish Signage Installer

*Field test as part of the c.7 calibration sweep. Phoenix discipline applied to a public peer-built ICM specialist. Verdict is honest, evidence-cited, peer-respecting. The discipline requires read-only evidence per atomic claim — see [rules.md](../../rules.md).*

## Target

| Field | Value |
|---|---|
| Specialist | RAMS Specialist for Irish Signage Installers |
| Author | JannetjeIQ |
| Repo | https://github.com/JannetjeIQ/rams-irish-signage-installer |
| Default branch | main |
| Last pushed | 2026-05-05 |
| License | Other (not MIT — license file present, but type "Other" per gh metadata) |
| Date graded | 2026-05-08 |
| Reviewer | Phoenix Agent v0.1 (acting via Claude Code, read-only) |

## Atomic claims tested

- **C1** ICM 5-file role coverage + quickstart skim-reader path
- **C2** Reference depth — 8 reference primers each scoped to one role
- **C3** Jurisdictional grounding (Republic of Ireland, HSA-aligned)
- **C4** Invention-proofing rule (specialist refuses to draft until contractor profile is filled)
- **C5** Acronym glossary in README for non-Irish readers
- **C6** Dual-path docs (Claude Projects + Claude Code) with operational discipline
- **C7** Honest exclusions named explicitly
- **C8** License + attribution

## Tool runs (read-only evidence)

- `gh repo view JannetjeIQ/rams-irish-signage-installer --json licenseInfo,pushedAt` → license="Other", pushed 2026-05-05
- `gh api repos/JannetjeIQ/rams-irish-signage-installer/git/trees/HEAD?recursive=1` → 13 files: `.gitignore`, `LICENSE`, `README.md`, `examples.md`, `identity.md`, `quickstart.md`, `reference/competency-matrix-ireland.md`, `reference/intake-questions.md`, `reference/legal-context-ireland.md`, `reference/permits-framework.md`, `reference/risk-library.md`, `reference/risk-matrix-5x5.md`, `reference/section-templates-hsa-8.md`, `reference/your-contractor-profile.md`, `rules.md`
- README content read, first 80 lines

---

## Report

```
## Report

STATUS: verified
CONFIDENCE: VERIFIED

### What did you verify?
- C1 (ICM 5-file + quickstart): VERIFIED — identity.md, rules.md, examples.md, README.md, reference/, plus quickstart.md as explicit skim-reader path. Adds a fast-onboarding shortcut without violating ICM shape.
- C2 (reference depth): VERIFIED — 8 reference primers, each scoped to one role: legal-context-ireland (statutory framing) / section-templates-hsa-8 (8-section RAMS scaffold) / risk-matrix-5x5 (scoring rules) / risk-library (curated signage-install hazards) / competency-matrix-ireland (Safe Pass, IPAF, PASMA, FAR, CSCS) / permits-framework (hot work / WAH / out-of-hours / lone working / confined space) / intake-questions / your-contractor-profile (gating template). This is the deepest reference set in the c.7 field.
- C3 (jurisdictional grounding): VERIFIED — README and reference primers explicitly grounded in Republic of Ireland law. HSA Guidance Document cited. Separate jurisdiction note for UK/NI ("you swap the legal context — HSA to HSE / CDM 2015"). Statutory references include S.I. 291/2013.
- C4 (invention-proofing rule): VERIFIED — README §"First-time setup" specifies: "The first prompt without a filled-in profile will refuse to draft. This is intentional: it stops Claude inventing a contractor name, insurance number, or PM." This gating discipline is the strongest invention-proofing pattern in the c.7 field — Phoenix has noted it as a discipline pattern Phoenix may consider for v0.2.
- C5 (acronym glossary): VERIFIED — 15-row glossary in README (RAMS / HSA / PSCS / RECI / FAR / IPAF / PASMA / MEWP / Safe Pass / CSCS / SDS / PAT / CPP / S.I. 291/2013) so non-Irish readers are not stranded. Looking-up signature.
- C6 (dual-path docs): VERIFIED — README §"Path A — Claude Project" and §"Path B — Claude Code (cowork)" each with explicit step-by-step. Author honestly notes Path B is the "truer ICM experience" — peer-respecting framing of trade-offs.
- C7 (honest exclusions): VERIFIED — README §"What it will not do" explicitly excludes electrical isolation/live disconnect (RECI registered electrician territory in ROI), anything above insurance height limit, civils/scaffolding-only/demolition (out of scope), UK or NI sites without legal-context swap. Five negative claims; clean anti-overclaim discipline.
- C8 (License + attribution): VERIFIED — LICENSE file present (gh metadata reports type "Other" rather than a standard SPDX identifier). License exists; type is non-standard.

### What could you not verify?
- Specific HSA template fidelity — would require Irish H&S domain expert to confirm the section-templates-hsa-8.md exactly matches the current HSA Guidance Document. Phoenix is not domain-qualified to verify; the framework is consistent and citation-accurate at the level Phoenix can grade.
- Production usage — no fitter testimonials or contractor adoption signals in the repo. Unverifiable from repo content alone.

### What feedback did the Phoenix give?
The RAMS specialist is among the strongest c.7 field entries. Domain specificity, jurisdictional grounding, and invention-proofing are exemplary. One small polish item:

1. License type — gh metadata reports "Other" rather than a standard SPDX identifier (MIT, Apache-2.0, etc.). If the actual license is custom, that's the author's call. If it's intended to be a standard license but mis-declared in LICENSE file, fixing the SPDX header would help discoverability for downstream forks.

### What should you fix first?
1. Standard SPDX license declaration if applicable. Otherwise: ship as-is.

### Up-down classification
- Looking-up signatures: 7 (jurisdictional grounding; invention-proofing rule; acronym glossary for non-Irish readers; dual-path discipline; explicit exclusions; peer-respecting voice on Claude Projects vs Cowork trade-offs; named legal regs)
- Looking-down signatures: 0
- Posture: STRONGLY UP-LEANING

### Verification metadata
- specialist_folder: JannetjeIQ/rams-irish-signage-installer
- atomic_claims_total: 8
- atomic_claims_verified: 8
- atomic_claims_failed: 0
- atomic_claims_unverified: 0 (HSA template fidelity is out-of-scope for Phoenix grading per rules.md §"Out of scope")
- read_only_compliance: PASS (no writes attempted to peer repo)
```

---

## Form mapping (per [rules.md §"Form mapping"](../../rules.md))

ICM-pure 5-file shape with quickstart.md as a fast-path overlay. Role coverage is complete. The quickstart is an honest extension (skim-reader optimization) — does not violate ICM, adds operator surface.

---

*Filed 2026-05-08 by Phoenix Agent v0.1. The RAMS Irish Signage Installer is the strongest domain-specific entry in the c.7 field. The invention-proofing rule (refuses to draft until profile filled) is a discipline pattern Phoenix has noted as worth considering for v0.2 — substantive credit lands here. Niche audience (Irish signage contractors), but the discipline is the template the rest of the field can learn from.*
