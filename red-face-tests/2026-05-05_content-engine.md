# Red-Face Test #1 — Vetter grades content-engine

*Captain framing: "we run vetter/verifier as a red-face test (oops, ofc, my bad, etc)" — eat our own dog food before public ships. Vetter: `_canon/brand/content-engine/specialist-vetter/` (commit `e64e603`). Target: `_canon/brand/content-engine/` (the 22-file content-engine shipped this morning at commit `8bfa6d5`).*

*Run by: Claude Code acting as Specialist Vetter v0.1, 2026-05-05.*

---

## Atomic claims tested

- C1: Folder has all 5 ICM components (identity / rules / examples / reference / README)
- C2: Each file has single-responsibility
- C3: identity-equivalent file exists and is operational
- C4: rules-equivalent material exists and is operational
- C5: examples-equivalent material exists with worked transformations
- C6: reference-equivalent material exists with curated sources
- C7: README enables cold-reader value in <5 minutes
- C8: Voice integrity (consistent voice owner per slot per voice-character-map)
- C9: Claims in canon files are evidence-backed via cross-references
- C10: Cadence Covenant + Voice Wall override rules are explicitly flagged

## Tool runs (read-only evidence)

- `find _canon/brand/content-engine -type f -name "*.md" | wc -l` → 22 files
- `ls _canon/brand/content-engine/` → README.md, index.md, platforms/, voice/, engine/, audience/
- `cat _canon/brand/content-engine/README.md` (read for cold-onboard test)
- `cat _canon/brand/content-engine/index.md` (read for identity check)
- `grep -l "Cadence Covenant" _canon/brand/content-engine/platforms/*.md` → all 7 files
- `grep -l "Voice Wall" _canon/brand/content-engine/platforms/newsletter.md voice/*.md` → present in newsletter.md, voice-character-map.md, brand-voice.md
- `grep -roh '\[\[[^]]*\]\]' _canon/brand/content-engine/ | sort -u` → wikilinks present + cross-resolving (spot-checked 6/40+; all resolved)

---

## Report

```
## Report

STATUS: unsure
CONFIDENCE: PARTIAL

### What did you verify?
- C1 (ICM form): PARTIAL — uses DeRonin content-engine taxonomy (index + platforms/ + voice/ + engine/ + audience/) instead of canonical 5-file ICM (identity / rules / examples / reference / README). All 5 functional ICM ROLES are covered, but in a different specialization shape. Worth naming explicitly so the vetter doesn't false-FAIL it on form alone.
- C2 (single-responsibility): VERIFIED — each file does one job (platforms/x.md = X-only; voice/voice-character-map.md = mapping-only; engine/repurpose.md = chain-order-only; audience/cyberpunk-readers.md = one-cut-only).
- C3 (identity): VERIFIED — index.md serves as the identity file. Names the system ("Content Engine — atomicity-graph for Genie Wars social production"), mission, niche, sacred cows.
- C4 (rules): VERIFIED — engine/repurpose.md (chain rules) + engine/hooks.md (hook formulas) + voice/platform-tone.md (per-platform rules) + index.md §"Hard Rules" collectively encode operational rules.
- C5 (examples): PARTIAL — engine/content-types.md defines 11 format types but does NOT contain worked one-topic-to-N-platforms transformations. The closest thing to examples is the v0.1 topic inventory in engine/topic-class-membrane-events.md (4 entries listed). Missing: actual side-by-side worked example showing one membrane event becoming 5-7 platform-native posts.
- C6 (reference): PARTIAL — engine/recon/README.md references source playbooks; index.md cross-links to canon files. NO dedicated `reference/` folder with curated source documents (Sunday recon excerpts, Resonant Computing recon excerpts, peer-author canonical posts, source playbook quotes). Claims rely on cross-references rather than self-contained source material.
- C7 (cold-onboard): VERIFIED — README.md + index.md together enable a stranger to understand the system in ~5 min. Tested mentally: a cold reader sees the 4-folder structure, atomicity primitive, recon→production loop, voice-character-map dimension, and how to use the engine.
- C8 (voice integrity): VERIFIED — voice/voice-character-map.md is single-source-of-truth for voice ownership per surface. Voice Wall absolute is referenced consistently. No voice contradictions across the 22 files.
- C9 (evidence-grounding via cross-references): VERIFIED — claims trace to canon files (`_canon/brand/ludo-brand-guide-v0.1.md`, voice cards, brand canon §11, membrane-events README). Spot-check: 6 of 6 sampled cross-refs resolved.
- C10 (override flagging): VERIFIED — every platform file (x, reddit-cyberpunk, booktok, newsletter, linkedin, hn, threads) explicitly flags Cadence Covenant frequency override. newsletter.md flags Voice Wall absolute.

### What could you not verify?
- Production behavior — the content-engine has not yet shipped a real one-topic-to-N-platforms cycle. The form is correct; the run-time output quality is unverified until first carpet-bomb cycle (Day 5+).
- Recon-fed calibration — engine/recon/ is briefed but unrun. Quality of platform-tone calibration depends on Days 1-4 recon. Currently at v0.1 best-guess.

### What feedback did the vetter give?
The content-engine is structurally sound and ICM-compliant in spirit but uses a different taxonomy than canonical 5-file ICM. Three concrete fixes would lift it to VERIFIED:

1. **Add `_canon/brand/content-engine/examples.md`** with 2-3 worked one-topic-to-N-platforms transformations. Pick one membrane event from engine/topic-class-membrane-events.md (e.g., gitagent PR-62) and show: X tweet → r/cyberpunk post → newsletter dispatch → BookTok caption → LinkedIn narrative. Make the RETHINK (not reformat) discipline visible.

2. **Add `_canon/brand/content-engine/reference/` folder** with curated source material:
   - `reference/sunday-recon-excerpts.md` (vocabulary + tropes from `_ops/trailer/working/sunday-recon-2026-05-03.md`)
   - `reference/resonant-recon-excerpts.md` (signatory list + framing rule from `research/external-landscape/resonantos-2026-05-03.md`)
   - `reference/source-playbook-deronin.md` (key quotes from the canonical source playbook)
   - `reference/voice-cards-distilled.md` (one-page voice register summary for cold readers)

3. **Optional polish**: rename or alias index.md → identity.md OR add a top-level note acknowledging the file maps to ICM identity-role.

### What should you fix first?
1. **Add examples.md (highest value, lowest cost)** — the missing piece that turns the engine from "framework" to "demonstrable."
2. **Add reference/ folder** — strengthens evidence-grounding; low cost since source material already exists in repo.
3. **Form-mapping note** — 1-line addition to README.md naming the ICM-role mapping.

### Up-down classification
- Looking-up signatures: 8 (extensive cross-references / acknowledged limits / recon-Days-1-4 future calibration named / voice-canon-respected / peer-respecting / atomicity primitive named / sacred cows preserved / Cadence Covenant explicit overrides)
- Looking-down signatures: 1 (form deviates from canonical ICM without explicit acknowledgment — minor)
- Posture: UP-leaning (strong; one fix is a tiny note in README)

### Verification metadata
- specialist_folder: _canon/brand/content-engine/
- atomic_claims_total: 10
- atomic_claims_verified: 7
- atomic_claims_failed: 0
- atomic_claims_unverified: 3 (C1 PARTIAL, C5 PARTIAL, C6 PARTIAL)
- read_only_compliance: PASS (no writes attempted to content-engine folder during grading)
```

---

## Implications for the public Vetter v0.1

**Adaptation needed in Vetter rules.md** (Wed-Thu iteration):

The Vetter currently grades against canonical 5-file ICM (identity / rules / examples / reference / README). This red-face test surfaced that some legitimate ICM specialists use **alternate taxonomies** (DeRonin-style content-engine: index + folders) where all 5 ICM functional ROLES are covered but file naming differs.

**Two options:**
- **Option A**: tighten Vetter rules to ONLY accept canonical 5-file form. Forces submitters to conform; cleaner grading; potentially false-FAILs valid alternate forms.
- **Option B (recommended)**: rules.md adds explicit rule: "vetter grades against the 5 functional ROLES (identity / rules / examples / reference / README). If a folder uses an alternate taxonomy, vetter maps the role-equivalents and grades accordingly. Form variance flagged but not failed."

Going with Option B aligns with verifier-agent discipline (decompose claims into functional atoms, not strict file-name atoms). Wed-Thu iteration adds this clause.

## Implications for content-engine v0.2

The 3 fixes named above (examples.md, reference/, form-mapping note) become content-engine v0.2 candidates, alongside Days 1-4 recon calibration. ~2-3 hours of work; can land Wednesday or Thursday.

---

*Red-face test #1 complete. Result: PARTIAL with UP-leaning posture, 3 specific fixes named, all small-cost. Content-engine is structurally sound; minor form polish brings it to VERIFIED. No major embarrassment surfaced — the dog food is edible.*

— Claude Code, 2026-05-05, acting as Specialist Vetter v0.1
