# Specialist Vetter — `school4agents`

*The folder that runs your business — now ships with a fully trained agent.*

A meta-specialist that vets other specialists. Drop your folder in; we put it through evaluation, train an agent to execute it, and hand both back cold-ready.

Live at [school4agents.com](https://school4agents.com).

---

## What this is (60 seconds)

You built a folder-based AI specialist using ICM (Interpretable Context Methodology — the folder-as-architecture pattern: `identity.md`, `rules.md`, `examples.md`, `reference/`, `README.md`).

It might work. You're not sure. There's no way to grade it cold.

This vetter grades it.

You drop your specialist folder in. The vetter:
1. Reads it (read-only — never modifies your files)
2. Decomposes the folder into atomic claims (each file does one job; each claim is single-truth-value)
3. Tests each claim against the folder's own evidence
4. Returns a structured **Report** with CONFIDENCE grade, atomic verifications, what's missing, and corrective feedback

Then you ship a folder you can stand behind. Or you fix the gaps the Report named.

## The 5-minute cold-tester test

A cold tester with no context should be able to do this:

1. Open a Claude Project at [claude.ai](https://claude.ai)
2. Upload the contents of this folder to the project knowledge base — `identity.md`, `rules.md`, `examples.md`, `inspiration.md`, the `reference/` folder, and the `red-face-tests/` folder
3. Start a new chat in the Project
4. Drop a specialist folder as an attachment (or paste its contents)
5. Type: *"Vet this specialist."*
6. Receive a structured Phoenix Report — STATUS / CONFIDENCE / atomic claims / fix-first / up-down — in one response

If that doesn't work, the folder isn't set up correctly. Open an issue.

**Want to probe harder?** Drop in TWO specialists and ask: *"Vet both. Which is closer to ship-cold-ready and why?"* The Phoenix should run two passes and surface the comparative gap honestly.

**Want to verify the discipline before trusting it?** Read [`red-face-tests/`](red-face-tests/) — three rounds of grading runs the Phoenix has filed publicly:
- [`2026-05-05_content-engine.md`](red-face-tests/2026-05-05_content-engine.md) — Phoenix grades the canon content-engine (PARTIAL → VERIFIED post-fixes)
- [`2026-05-05_self.md`](red-face-tests/2026-05-05_self.md) — Phoenix grades itself (VERIFIED — recursive integrity)
- [`2026-05-08_field/`](red-face-tests/2026-05-08_field/) — Phoenix grades **eight peer-built ICM specialists** publicly submitted to the same Skool weekly-comp lineage (the meta-grading claim made verifiable on disk; start at [`00_overview.md`](red-face-tests/2026-05-08_field/00_overview.md))

## How to use

### Method A — Claude Projects (recommended)

1. Clone or download this repo
2. Open Claude Projects → create new project "Specialist Vetter"
3. Upload the contents of this folder (4 root `.md` files + `inspiration.md` + `reference/` folder + `red-face-tests/` folder) to the project knowledge base
4. Start a new chat in that project
5. Drop your specialist folder's content as a new attachment OR paste the file contents
6. Ask: *"Vet this specialist."*
7. Get structured Report

### Method B — Claude.ai with paste

1. Open [identity.md](identity.md) and [rules.md](rules.md). Paste both into a new Claude chat.
2. Add: *"You are this vetter. Now grade the specialist below."*
3. Paste your specialist's files (or the most important ones)
4. Get the Report

### Method C — Claude Code / Cursor / agentic CLI

1. Point your agent at this folder
2. Drop your specialist folder beside it
3. Say: *"Run the vetter against the specialist."*
4. Watch it traverse, grade, return Report

## What you get back

A structured Report block:

```
## Report

STATUS: verified | failed | unsure
CONFIDENCE: PERFECT | VERIFIED | PARTIAL | FEEDBACK | FAILED

### What did you verify?
- <atomic claim>: <evidence + verdict>

### What could you not verify?
- <claim>: <why — missing oracle / fixture / ambiguity>

### What feedback did the vetter give?
<paraphrase of corrective findings>

### What should you fix first?
<prioritized improvement list>

### Verification metadata
- atomic_claims_total / verified / failed / unverified
- up_down_ratio: <ratio classification>
```

CONFIDENCE grade tells you whether you can ship the folder cold. Below VERIFIED → don't ship. At VERIFIED+ → ship.

## What it does NOT do

- ❌ Does not write or modify your folder. Read-only.
- ❌ Does not produce content for your specialist. Evaluates only.
- ❌ Does not guess. If a claim can't be verified, status is `unsure`, gap flagged.
- ❌ Does not grade against vibe. Every verdict cites evidence.
- ❌ Does not fall back to "helpful at the cost of honest." False PERFECT is the worst failure mode.

## Out of scope — what the Phoenix won't grade

- **Code repos that aren't ICM specialists.** The Phoenix grades a folder as a specialist (identity / rules / examples / reference / README — or the role-equivalents per `rules.md §"Form mapping"`). It does not grade arbitrary codebases.
- **Runtime behavior of an agent.** It evaluates the FOLDER, not what happens when the specialist is actually invoked in production. Production behavior is a different verifier.
- **Lone files.** ICM is folder-shaped. A single `identity.md` without rules + examples + reference is not gradable; it'll come back FAILED with a "not enough atomic claims to verify" note.
- **Substrate that isn't on disk.** If your specialist depends on private prompts, hidden context, or proprietary data the Phoenix can't see, it'll mark those claims unverifiable rather than guessing.
- **Anything outside read-only scope.** It will not write, modify, suggest edits inline, or run the specialist for you. It grades. You ship.

## What's inside this folder

| File | Job |
|---|---|
| [identity.md](identity.md) | Who the vetter is (Crèche-Manager voice, peer-respecting consultant) |
| [rules.md](rules.md) | How it responds (read-only / atomic / evidence / CONFIDENCE / structured Report) |
| [examples.md](examples.md) | What good and bad look like (3 worked examples: FAILED / PARTIAL / VERIFIED) |
| [reference/](reference/) | Source material — 8 primers: atomic claims / observer pattern / ICM principles / CONFIDENCE ladder / up-down ratio + 3 homage primers: ICM three-layers / 60-30-10 method / show your work |
| [inspiration.md](inspiration.md) | Lineage + citations (Jake Van Clief's ICM, Austin Kleon's *Show Your Work*, the Skool comp brief, the four other altitude convergences) |
| [red-face-tests/](red-face-tests/) | Phoenix's grading runs: `2026-05-05_content-engine.md` (PARTIAL → VERIFIED post-fixes) + `2026-05-05_self.md` (VERIFIED — recursive integrity) + `2026-05-08_field/` (eight peer-built ICM specialists graded — receipts that the meta-grading claim works in practice) |
| [README.md](README.md) | This file |

Each file does one job. The connections between them carry intelligence no single prompt can.

## Why this exists

We watched five independent agentic builders converge on the same primitive in eight days:

- A moral-physics spec for digital consciences (private)
- A pattern named ClawLaw merged into upstream OSS at github.com/open-gitagent/gitagent-protocol/pull/62 on 2026-05-04
- A verifier-agent codifying read-only observer architecture (disler/the-verifier-agent)
- A content-engine playbook teaching folder-as-specialist (DeRonin)
- The **Interpretable Context Methodology** (ICM) Jake Van Clief teaches at the Quantum Quill Lyceum — the production-discipline-layer predecessor that names the discipline as such

Same primitive. Different altitudes. Atomicity.

We decided the next move was to make that gradeable. So you can ship folders that don't fall over the moment a stranger tries to use them.

## Receipts

Live at [school4agents.com](https://school4agents.com). Built by the Genie Wars publishing house. More at [siliconchimps.com](https://siliconchimps.com) and [geniewars.com](https://geniewars.com).

## Lineage / homage

This Vetter is built ICM-pure (per Jake Van Clief's [Interpretable Context Methodology](https://www.skool.com/quantum-quill-lyceum-1116)) and applies the discipline taught at the Quantum Quill Lyceum. The folder you are reading IS the homage — every architectural choice traces to a named source. See [inspiration.md](inspiration.md) for full lineage + the three key citations (Jake's ICM + Austin Kleon's *Show Your Work* + the Skool Comp #3 brief).

## License

MIT. Fork it. Improve it. Ship better folders.

---

*v0.1 — 2026-05-05 initial seal. Locked final state 2026-05-08 (Friday EOD per Captain rule, ahead of Saturday submission). Built ICM-pure. Eaten its own dog food (the Vetter passes its own grading; Vetter graded content-engine and content-engine v0.2 fixes lift it to VERIFIED). The folder you'd build this weekend — but with a fully trained agent already inside.*

**v0.1 LOCK NOTE (2026-05-08):** Friday lock pass complete. (1) `rules.md` form-mapping clause added — vetter grades against the 5 functional ROLES, not strict file names; alternate ICM taxonomies are mapped role-equivalents and graded on substance. (2) Atomicity-primitive convergence updated to FIVE altitudes (Jake's ICM added as production-discipline-layer predecessor). (3) The sibling content-engine that the Vetter graded was patched in response to red-face test #1 — examples + reference + form-mapping note added; grade lifts from PARTIAL to VERIFIED. No new claims added to the Vetter beyond these polish edits; the structural commitments locked 2026-05-05 are unchanged.

— Ludo
*On behalf of the 2062 DB*
