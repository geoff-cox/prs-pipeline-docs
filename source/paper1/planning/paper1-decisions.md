# Paper 1 — Phase 0 Decisions Record

Manuscript: `docs/source/paper1/paper1-manuscript.ptx`
Recorded: **2026-07-17** (Geoffrey Cox). Style follows the `Decisions record`
convention in `dev/claude-build-tasks/important-references.md`.

Status legend: **FROZEN** (change only with a dated amendment below) ·
**PENDING** (blocked on a named event) · **DEFERRED** (out of scope for Paper 1
by decision, with its future home named).

---

## D1 · Target journal — FROZEN

**Primary: Journal of Educational Data Mining (JEDM). Fallback: Journal of
Learning Analytics (JLA).**

Basis: JEDM is diamond OA (no APC), offers optional double-blind review,
strongly encourages public data/code/intermediate results, emphasizes
methodological rigor, and expects a demonstration of cross-context
generalizability — the adapter-architecture argument answers that expectation
directly, so it stays prominent in the framing. JEDM imposes no hard length
cap. JLA (also no-fee) caps research papers at ~8,000 words; if the fallback
is ever invoked, the D4 exclusions and supplement moves are what make the
manuscript fit.

Consequences adopted with this decision:
- Length target: the annotated section budgets (~7,000–9,000 words main text)
  are the working budget; JEDM's flexibility is not license to expand.
- The AI-use declaration (`sec-declarations.ptx`) must quote JEDM's generative-AI
  policy language; pull the current text from the JEDM submission page at
  drafting time.
- Declarations, reference style, and abstract format follow JEDM author
  guidelines (APA where the guidelines are silent).
- Public release of the software, synthetic corpus, and aggregate results is
  not just permitted but advantageous at this venue — factor into the D5
  governance requests.

## D2 · Authorship — FROZEN

**Sole author: Geoffrey Cox (VMI), corresponding.**

- CRediT statement: all roles held by the sole author; drafted at Phase 6.
- Coauthor-approval gates (completion Gate 10, declaration sign-offs) reduce
  to self-review plus any data-provider approvals under D5.
- **PENDING sub-item:** PI credit (acknowledgment vs. authorship) — raised in
  the 2026-07 email to the PI; resolve by ICMJE/CRediT criteria once her
  involvement is known. If authorship, reopen this decision with an amendment.

## D3 · Research-question scaffolding

### D3.1 RQ3 analytic form — FROZEN

**Descriptive only.** RQ3 is answered with distributional summaries and
contrasts of baseline process features across endpoint-equivalent groups,
with student-clustered (bootstrap) uncertainty. **No inferential crossed
student×item model in Paper 1** — with 5–15 items, item effects would control
dependence, not support design generalization, and the model belongs to the
process-modeling paper (see D4). Representative trajectories are selected by
a reproducible rule (nearest-to-group-median feature vector; exact rule
recorded in the analysis manifest at Phase 3).

**PENDING sub-item:** the *specific* primary contrast (completion Gate 6)
cannot be frozen until candidate-group attempt counts exist (Phase 3.2).
Leading candidate, recorded now to constrain later choice: among
eventually-correct attempts, first-check-correct ("direct") vs.
first-check-incorrect ("revised"). Any other contrast adopted instead must be
justified by sample size, not by results.

### D3.2 RQ4 sensitivity knobs — FROZEN

Design: **one knob varied at a time** against the primary configuration; no
factorial grid. Each run reports Δ attempts, Δ ready %, Δ anchor agreement,
and Δ primary RQ3 estimate (`tab-sensitivity-results`). Material-change
threshold is set before inspection, at Phase 3.3.

| # | Knob | Primary (frozen) | Alternatives (frozen) | Source of primary |
|---|------|------------------|----------------------|-------------------|
| 1 | Attempt-gap threshold | 30 min | 10 min; 60 min | `sec-reconstruction` default; `SegmentationConfig` |
| 2 | Reset semantics | Reset restores s₀ *within* the attempt | Reset starts a new attempt | `reconstruct.py` default |
| 3 | Events after first correct check | Retained in the attempt (post-check-revision span kept) | Truncate at first correct check | as-built segments |
| 4 | No-op drops | Retained + flagged; excluded from effective-move counts | Included in move counts | F1 decision, `qc.py` |
| 5 | Row-order tie handling | Time → problem-view → stable file order; `row_order_ambiguous` flagged | Exclude flagged attempts from the primary analysis | F2, `reconstruct.py` |
| 6 | Analytic idle threshold δ_max | 300 s | 120 s; 600 s | `qc.DEFAULT_IDLE_THRESHOLD_S` |
| 7 | Readiness inclusion | `ready` attempts only | `ready` + `limited` (named sensitivity condition) | `subsec-qc-readiness` |

Total: primary + 9 alternative runs. Anything not in this table analyzed
later is labeled post hoc in the manuscript. Note knobs 1–3 change
*reconstruction* (attempt counts and states); knobs 4–7 change only
*features/inclusion* — report the two groups separately per the
sensitivity-results checklist.

Justifications to write at Phase 1.2 (from platform semantics and observed gap
distributions, never from results): the 10/60-min bracket around the 30-min
default; 120/600 s bracketing δ_max = 300 s.

### D3.3 Table/figure → RQ map — FROZEN

Rule: every main-text display maps to exactly one RQ or to required
sample/methods reporting; a display that maps to neither is cut or moved to
the supplement. Appendix tables are exempt.

| Display | Location | Maps to |
|---|---|---|
| `tab-input-contracts` | sec-data-canonical | RQ1 |
| `fig-adapter-architecture` | sec-data-canonical | RQ1 |
| `fig-running-trajectory` | sec-framework | RQ1 |
| `tab-replay-rules` | sec-reconstruction | RQ1 |
| `tab-readiness-policy` | sec-reconstruction | RQ2 |
| Participant-flow (CONSORT-style) table | sec-empirical | Sample reporting |
| Item table (topic, P, R, decoys, version, policy, counts) | sec-empirical | Sample reporting |
| `tab-validation-results` | sec-results | RQ2 |
| `fig-validation-results` | sec-results | RQ2 |
| Process-contrast table/figure (id TBD at Phase 3) | sec-results | RQ3 |
| `tab-sensitivity-results` | sec-results | RQ4 |

Budget consequence: this is the complete main-text display set — roughly six
tables and three or four figures. New displays require a dated amendment here.

## D4 · Feature set and scope exclusions — FROZEN

Paper 1 carries only the features that RQ1–RQ4 consume: checked-state
outcomes (F10: first/final-check distance, first-check correct, eventual
correct, correct-check ordinal), the flat error profile (F12: omissions,
wrong-slot, decoy leaks, per-card score), movement counts with excess moves,
check cadence, and the time features under the frozen δ_max.

Excluded from Paper 1, with future homes:

| Item | Decision | Future home |
|---|---|---|
| F11 card-placement entropy | Out (no RQ consumes it); sweep `subsec-baseline-features` for any mention | Item-design/diagnostics paper |
| F8/F8b repeated states, occupancy/rank | Out | Item-design/diagnostics paper |
| Inferential crossed model; Markov/transition networks (F21) | Out (per D3.1) | Process-modeling paper |
| Grouping partition metrics (Rand/ARI/VI) | Out (already declared out of scope) | Trajectory-level sorting-assessment paper |
| Cross-era feedback-policy comparison | Out — corpus is entirely legacy-era; policy recorded as a constant covariate only | Feedback-policy natural-experiment paper (once layered-era data accumulates) |
| Weighted/semantic distances (F15) | Out | As needed, with a stated cost matrix |
| Full field mapping, complete QC rulebook, per-configuration sensitivity tables, machine-readable feature dictionary | Supplement, not cut | Paper 1 supplementary material |

Guard against salami-slicing: each deferred paper is organized around a
question Paper 1 explicitly declares out of scope, not around leftover
features.

## D5 · Governance — PENDING (email sent to PI, 2026-07)

Awaiting: written IRB/determination and its secondary-use basis; analysis
authorization; release constraints (row-level logs, timestamps, session IDs);
corpus scope (Fall 25, Spring 26, any others); PreTeXt source-history access;
permission to reproduce one item; institution-naming preference; credit
expectations. Record outcomes as a dated amendment here; they unblock
Phases 1–4 of `paper1-completion-plan.md`.

---

## Immediate edits triggered by this record

2. `sec-introduction.ptx` — RQ freeze checklist items 2–5 now resolved; the
   comment block can be trimmed to point here.
3. `subsec-baseline-features` (sec-reconstruction) — confirm no entropy
   mention survives in main text (D4).
4. `docs/source/paper1/` — commit this file (suggested name
   `paper1-decisions.md`, beside `paper1-literature-matrix.md`).

## Amendments

*(none yet — add dated entries below; never edit a frozen decision in place)*
