# Field test — Phoenix Agent v0.1 grades the comp #3 field

*Third red-face test. The first two graded the canon content-engine and the Phoenix itself. This one grades **eight peer-built ICM specialists** publicly submitted to the same Skool weekly-comp lineage as the Phoenix.*

*The submission claim — "this submission also grades every other competition entry" — is verified here on disk. Receipts inline.*

---

## What's in this folder

| # | Specialist | Author | Phoenix grade | Posture |
|---|---|---|---|---|
| 01 | [Agency Concierge Director](01_agency-concierge-director.md) | luisarias74 | VERIFIED | BALANCED |
| 02 | [Realtor Copilot v2](02_realtor-copilot-v2.md) | NFTYoginis | VERIFIED (PERFECT-leaning) | STRONGLY UP-LEANING |
| 03 | [Buyer Profiler](03_buyer-profiler.md) | chays77 | VERIFIED | UP-LEANING |
| 04 | [j-hack-stack](04_j-hack-stack.md) | jfran03 | PARTIAL | BALANCED |
| 05 | [Indie Venue Analyst](05_indie-venue-analyst.md) | Six8Coffee | PARTIAL | BALANCED |
| 06 | [AI Opportunity Auditor](06_ai-opportunity-auditor.md) | raiderbell | VERIFIED | UP-LEANING |
| 07 | [Realtor Copilot v1](07_realtor-copilot-v1.md) | NFTYoginis | SUPERSEDED | n/a |
| 08 | [RAMS Irish Signage Installer](08_rams-irish-signage.md) | JannetjeIQ | VERIFIED | STRONGLY UP-LEANING |

One additional submission (Shopify SEO Auditor, hosted on Google Drive) was **NOT-GRADABLE** on the Phoenix scale — Drive folders fall under `rules.md §"Out of scope: substrate that isn't on disk"`. Noted, not graded.

## How these grades were produced

For each specialist:

1. **Pull metadata** — `gh repo view <author>/<repo>` for description, license, default branch, last pushed.
2. **Enumerate the tree** — `gh api repos/<author>/<repo>/git/trees/HEAD?recursive=1` to get the full file list.
3. **Read the README** — `gh api repos/<author>/<repo>/readme` for the operator-facing surface.
4. **Decompose into atomic claims** — each verifiable proposition (ICM role coverage, single-responsibility per file, evidence-cited claims, voice register, audience specificity, etc.).
5. **Test each claim against deterministic evidence** — file content, command output, link resolution.
6. **Classify each verified claim** for up-down posture per `reference/up-down-ratio.md`.
7. **Emit Phoenix Report block** per the canonical output contract in `rules.md`.

Read-only throughout. No file in any peer repo was modified, suggested, or invited to change. The Phoenix is a grader, not an editor.

## Voice + posture

Each grade is honest. Where a specialist passed a claim, the Phoenix said so. Where it could not verify a claim, the Phoenix said why. Where a fix-first item was load-bearing, the Phoenix named it loudly. Where the work was outside the Phoenix's scope, the Phoenix declined to grade rather than force-fitting.

These eight peer-built specialists are not rivals. They are co-builders in the same lineage Jake Van Clief teaches. The Phoenix grades public artefacts publicly because that is what "Show Your Work" requires. **Each report is constructive — c.7 authors may use these as fix-first references for their own folders.**

## Verify it yourself

Drop the Phoenix Agent into a Claude Project (the 5-Minute Cold-Tester Test in the [README](../../README.md)), then drop any of these eight peer specialists in beside it, and ask: *"Vet this specialist."* You should receive a Phoenix Report whose verdict is consistent with the one filed here. If not, the Phoenix is broken and an issue is welcome.

---

## Field findings (cross-portfolio)

**Voice register:** five of the eight peer specialists sit in the same plain / peer-respecting / anti-marketer register the Phoenix uses (Realtor v2, Buyer Profiler, Indie Venue Analyst, AI Opportunity Auditor, RAMS). One (Agency Concierge) breaks this with a marketer-energetic register. One (j-hack-stack) is builder-personal / academic-y. The Phoenix is voice-aligned with the field's strongest entries — not an aesthetic break.

**Form distribution:** six of eight ship as ICM-pure 5-file folders. Two (Realtor v1 + v2) ship in nested-ICM (specialist/ subfolder + case-studies/ + docs/). The Phoenix per `rules.md §"Form mapping"` grades against ROLES not file names — both shapes pass when the role coverage is complete.

**License practice:** four MIT, one Other, three none. The Phoenix is MIT.

**Phoenix's category:** the eight peer specialists are **domain specialists** (real estate, sales, hospo SaaS, healthcare SMB, agency intake, hackathons, signage compliance). The Phoenix is the **only meta-specialist** — it grades other specialists. Different category; no direct competitor.

---

*Filed 2026-05-08 by Phoenix Agent v0.1, acting via Claude Code, read-only across all eight peer repos. The receipts are the proof. The discipline is the product. school4agents.com / github.com/bengii/school4agents*
