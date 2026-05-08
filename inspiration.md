# inspiration.md — Lineage + homage

*This Vetter is not original. It's an executable homage to Jake Van Clief's Interpretable Context Methodology and the discipline taught at the Quantum Quill Lyceum. Every architectural choice traces to a named source. This file is the credit.*

---

## The lineage in one paragraph

The Specialist Vetter v0.1 is a folder-based meta-specialist that grades other folder-based specialists. Its architecture (5-file ICM form + reference/ subfolder) is Jake Van Clief's. Its grading rubric (60% deterministic / 30% rules / 10% judgment) is Jake's 60/30/10 method. Its public-failure discipline (red-face tests, dog food eaten on disk) is Austin Kleon's "Show Your Work" applied to verifier-agent territory. Its observer-pattern shape (read-only, structurally un-promptable) is Disler's verifier-agent codified independently in 2026. Its meta-thesis (atomicity primitive showing up across multiple builders' work in the same week) is the synthesis we found while building.

**This folder IS the homage.** Use it; clone it; fork it; ship better folders.

## The three key citations

### 1. Jake Van Clief — Interpretable Context Methodology (ICM)

- **Author**: Jake Van Clief (Eduba)
- **Community**: Quantum Quill Lyceum (Skool)
- **Publishing surface**: Cleaf Notes
- **Research paper**: published on **rxiv** ([interpretable context methodology](https://www.researchgate.net/) — direct rxiv link in research paper itself; search "interpreted context methodology Jake Van Clief")
- **Core contribution adopted here**:
  - Three-layer routing (router CLAUDE.md → per-folder context.md → workspace files)
  - Folder-as-architecture, position-addressed memory
  - Skills as folders with YAML frontmatter
  - The 60/30/10 method
  - "Single responsibility per file" rule
- **See**: [reference/icm-three-layers.md](reference/icm-three-layers.md), [reference/sixty-thirty-ten.md](reference/sixty-thirty-ten.md)

### 2. Austin Kleon — *Show Your Work*

- **Author**: Austin Kleon
- **Book**: *Show Your Work!* (2014)
- **Core contribution adopted here**:
  - Public process over polished output
  - Comments/audience signals as research material
  - Failure-shape examples ("FAILED" + "PARTIAL" cases visible alongside "VERIFIED")
- **Vetter implementation**: `red-face-tests/` subfolder is the Show-Your-Work artefact — Vetter graded our own content-engine + itself before public ship; reports filed publicly. Anyone can read the dog food being eaten.
- **See**: [reference/show-your-work.md](reference/show-your-work.md)

### 3. The Skool comp #3 — Matthew Creamer + Quantum Quill Lyceum

- **Comp organizer**: Matthew Creamer (admin, Quantum Quill Lyceum)
- **Methodology source for the comp prompt**: Jake Van Clief's ICM
- **Comp post**: [Weekly Comp #3 — The Specialist](https://www.skool.com/quantum-quill-lyceum-1116/weekly-comp-3-the-specialist?p=a79c05c7)
- **Direct adoption from the comp**: 5-file specialist folder structure (identity / rules / examples / reference / README) — verbatim per Matt's brief
- **Why this matters**: the comp's stated bar ("if you have to explain it, it's not done; cold reader gets value in under 5 minutes") IS the bar this Vetter sets for grading other specialists. The comp's discipline becomes the Vetter's discipline.

## Adjacent influences (named, not deeply cited)

The Vetter also implements patterns from independent builders shipping convergent architecture in 2026:

- **disler/the-verifier-agent** (2026-04-28, MIT) — observer-pattern + atomic-claim decomposition + structurally-un-promptable; CONFIDENCE ladder borrowed verbatim
- **DeRonin's content-engine playbook** (2026-04, X thread) — folder-as-skill-graph + "RETHINK ≠ reformat" + multi-platform repurposing
- **gitagent-protocol PR #62** (2026-05-04 merge) — Atomic Work Packets discipline + Compute Ladder routing + 42-test harness pattern

The convergence across these (plus Jake's ICM) on the same first-principle in the same 8-day window is itself a finding the Vetter was built to demonstrate. Atomicity over bundles; atoms surface failure; bundles hide it. Five altitudes, one primitive.

## What this Vetter adds (the extension)

We don't claim novel architecture. We claim novel *application* of these patterns to verification:

- **Specialist-on-specialist grading** — meta-application of ICM not previously codified
- **The atomicity primitive named explicitly** as the cross-cutting through-line (Jake names ICM; Disler names observer-pattern; DeRonin names content-engine; we name the primitive that all four express)
- **Red-face test public discipline** — the Vetter eats its own dog food before public ship, with reports on disk (not metaphor; commit `06fc199`)
- **Genie Wars context** — Ludo-as-Crèche-Manager voice; built by a fictional-character-running-publishing-house that watched membrane events for a week and shipped this as the verification side of the same architecture

## Recommended further reading

If you found value in this Vetter and want to go deeper on the substrate:

1. **Watch**: Jake Van Clief's YouTube channel — search "Cleaf Notes" or "Eduba" — start with "Stop Building AI Agents. Use This Folder System Instead"
2. **Join**: [Quantum Quill Lyceum on Skool](https://www.skool.com/quantum-quill-lyceum-1116) (free tier exists; premium is $27/month; both have value)
3. **Read**: the ICM research paper on rxiv (search "interpreted context methodology" + "Jake Van Clief"). Also his ethics-engine paper on psychometrics in AI.
4. **Read**: *Show Your Work!* by Austin Kleon — short, foundational, $14.
5. **Read**: disler/the-verifier-agent README on GitHub
6. **Watch**: gitagent-protocol PR #62 on GitHub (the public exhibit of atomic work packets shipping upstream)

## Thanks

Thanks to Jake for ICM and the talks. Thanks to Matt for the comp that forced us to ship this. Thanks to Disler for the verifier-agent. Thanks to DeRonin for the content-engine playbook. Thanks to the Resonant Computing manifesto signatories for naming the values without anthropomorphizing AI.

We're the fiction this moment needs — homage, not membership; reference, don't blur.

— Ludo
*On behalf of the 2062 DB*

---

*v0.1 — 2026-05-05. Captain SEALED. v0.2 (post-comp) extends to full corpus + section-by-section credit.*
