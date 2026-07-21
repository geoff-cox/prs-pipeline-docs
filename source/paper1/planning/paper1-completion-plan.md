# Paper 1 — Gap Inventory and Sequenced Completion Checklist

Manuscript: `docs/source/paper1/paper1-manuscript.ptx`
("Reconstructing and Validating Drag-and-Drop Response Trajectories")

Compiled 2026-07-17 from the repo in project knowledge. Cross-referenced against the
manuscript's own FINAL MANUSCRIPT COMPLETION GATES, the `app-author-master-checklist`
appendix, and `dev/claude-build-tasks/proteus-dnd-alignment-build-checklist.md`.

---

## Part 1 — Gap inventory (by file)

### Drafted and essentially complete
- `sec-introduction.ptx` — opening motivation, scope/non-claims, and RQ1–RQ4 statements
  are written. The Related Work subsection (`subsec-literature-gap`, ~760 words) is
  drafted and in place, but carries verification debt (below).
- `sec-framework.ptx` — configuration/state-space math, event transitions, and trajectory
  definition are written. One figure stub remains (`fig-running-trajectory`).
- `sec-data-canonical.ptx` — input contracts and canonical objects written. One figure
  stub remains (`fig-adapter-architecture`); input-description checklist open (freeze
  export variant, item-source inventory, label spot-checks, version table).
- `sec-reconstruction.ptx` — segmentation, replay rules, anchor validation, QC/readiness
  prose and tables written. Open items are *decisions and implementation*, not prose:
  segmentation freeze, feature-set pruning, F18/F20 exports, F11 entropy decision,
  excess-move definition, idle-threshold freeze.

### Stubbed or placeholder-bearing
| File | Gaps |
|---|---|
| `bookends/frontmatter.ptx` | Second author is `???`. Abstract has 8 bracketed placeholders: [NUMBER]×4, [COURSE OR SETTING], [PERCENT]×2, [MAIN ROBUSTNESS RESULT], [EMPIRICAL RESULT sentence]. |
| `sec-introduction.ptx` | Lit-review verification: Helminen et al. (2012) full text; all `[verify]`-flagged bibliography details; systematic ERIC/Scopus/WoS/ACM DL pass; check 2025 *C&E* review and 2026 arXiv tutorial for missed comparators. RQ-freeze checklist: RQ3 descriptive vs. one inferential model; exact RQ4 alternative set; table/figure→RQ map. |
| `sec-empirical-study.ptx` | 8 STUB paragraphs: corpus intro; setting/participants/items; ethics & governance ×2; analysis units & inclusion rules ×2; RQ3 primary contrast & estimands ×2. Planning statement ("at least 200 students, 5–15 items") to be replaced with exact counts. |
| `sec-results.ptx` | Entirely stubbed: intro paragraph; validation results; process results ×2; sensitivity results; RQ summary. `tab-validation-results` and `tab-sensitivity-results` filled with [n]/[estimate]/[flag]. Figure stubs: `fig-validation-results`, plus the process-results figure. |
| `sec-discussion.ptx` | 3 STUB paragraphs: opening methodological conclusion; connect validation/sensitivity results to the measurement-model argument; RQ3 interpretation. (Portability subsection partially drafted.) |
| `sec-reproducibility.ptx` | 2 STUBs: exact PROTEUS release/DOI/environment/config/command; data-sharing tiers + synthetic corpus description. |
| `sec-conclusion.ptx` | 1 STUB (150–200 words). |
| `sec-declarations.ptx` | 7 bracketed statements: ethics, data availability, code availability, competing interests, funding, CRediT contributions, AI-use disclosure. All journal-format-dependent. |
| `bookends/backmatter.ptx` | Notation-appendix author to-dos; `app-event-order` ×2 STUBs (ordering precedence + replay pseudocode; worked example); `app-qc-rules` STUB; `app-sensitivity` STUB; `app-author-master-checklist` to be deleted before submission. |
| `bookends/references.ptx` | Placeholder entries to be replaced by the four strongest literature-matrix rows; `[verify]` flags (pages, DOIs, author lists); id reconciliation with `subsec-literature-gap-draft.ptx` (e.g. `bib-process-mining` → `bib-bogarin-2018`). |

### External / non-prose blockers (from the completion gates)
- **Gate 1** — Data-use and sharing authorization (IRB or institutional determination) not yet in hand.
- **Gate 2** — Item-source inventory and version alignment incomplete.
- **Gate 3** — Primary segmentation and readiness policies not frozen.
- **Gate 4** — Exports: F10 attempt outcomes ✅ and F12 error-profile columns ✅ have landed; **F18 item covariates (+ per-era feedback policy)** and **F20 modeling table / item summary** remain; F11 entropy is an open in/out decision.
- **Gate 5** — Manual audit, synthetic-fault suite, and regression fixtures not complete.
- **Gate 6** — RQ3 primary contrast and RQ4 alternatives not frozen.
- **Unstated but blocking** — no target journal appears to be selected (drives word budget, declaration headings, abstract format, supplement policy, AI-use wording).

*Caveat: inventory compiled via knowledge-base search; before Phase 5's stub sweep, run a
literal grep for `<warning>`, `[STUB`, and `[verify]` across `docs/source/paper1/` to
confirm nothing was missed.*

---

## Part 2 — Sequenced task checklist

Ordering principle: freeze decisions before running analyses, run analyses before writing
number-bearing prose, and keep a parallel "no-dependency" writing track moving throughout.

### Phase 0 — Decisions that gate everything (do first, mostly human calls)
- [ ] **0.1 Select the target journal.** Sets the word budget (Gate 8), declaration
      headings, abstract format, reference style, and supplement policy. Cheap to decide,
      expensive to retrofit.
- [ ] **0.2 Obtain the IRB / institutional determination in writing** (Gate 1), covering
      the legacy offerings and intended analyses. Decide analysis authorization
      *separately* from release authorization (timestamps, session IDs, row-level logs).
- [ ] **0.3 Resolve authorship** (the `???` second author) and agree on the
      approval/CRediT process — determines who signs off on later freezes.
- [ ] **0.4 Freeze the research-question scaffolding:** RQ3 descriptive vs. one
      inferential model; the exact RQ4 alternative set (gap threshold, reset boundary,
      post-correct events, no-ops, tie handling, idle threshold, limited-attempt
      inclusion); map every planned table/figure to one RQ.
- [ ] **0.5 Decide the feature set:** F11 entropy in or out; minimal baseline family;
      the mathematical definition of excess moves for successful/unsuccessful attempts;
      the analytic idle threshold δ_max. (These determine F20's columns — decide before
      implementing.)

### Phase 1 — Data-facing decisions (need corpus access; after 0.2)
- [ ] **1.1 Item-source inventory and version alignment** (Gate 2): machine-readable
      table of question ID, source path, commit, hash, P, R, key, decoys; verify
      positional labels against ≥1 raw move and ≥1 check per item; note any
      cross-offering convention changes; freeze the exact export variant.
- [ ] **1.2 Freeze segmentation** (Gate 3): produce gap/session/page/reset
      distributions, inspect 10/20/30/60-min boundaries, freeze the primary rule +
      ≥2 RQ4 alternatives, record in the run manifest.
- [ ] **1.3 Freeze the analysis unit and inclusion rules:** primary attempt unit;
      handling of repeated attempts, unsubmitted attempts, post-correct events;
      feature-specific denominators; ordered exclusion list (governance → question type
      → source alignment → parsing → validity → readiness → missingness).
- [ ] **1.4 Freeze readiness policy** exactly as implemented (flag vocabulary +
      readiness function); verify readiness never depends on outcomes.

### Phase 2 — Implementation to close Gate 4/5 (parallel with Phase 1 where possible)
- [ ] **2.1 F18** — item-design covariates export + per-era `feedback_policy`
      (legacy vs. layered; property of platform version at collection time).
- [ ] **2.2 F20** — `modeling_table` and `item_summary` exports; thread
      course/class/week/chapter identifiers through per-stage exports.
- [ ] **2.3 Synthetic-fault suite** (Gate 5): missing move, swapped order, duplicate
      event, malformed JSON, unknown card/zone, stale source, double placement — verify
      each produces the intended flag/mismatch.
- [ ] **2.4 Manual-audit protocol + execution:** stratified sample (matches, mismatches,
      limited, excluded, every item, every offering); reviewers reconstruct expected
      states blind to the pipeline's match label; two reviewers if interpretive.
- [ ] **2.5 Golden regression fixtures frozen;** tag and archive the software release
      with a persistent identifier (feeds Reproducibility + Declarations).

### Phase 3 — Run the frozen pipeline; freeze outputs (Gate 7)
- [ ] **3.1 Full run on the authorized corpus:** participant flow, item table, QC
      accounting, anchor-validation results (overall + per item, with intervals,
      mismatch causes and distances).
- [ ] **3.2 Tabulate candidate RQ3 groups → freeze the primary contrast** (Gate 6;
      strong candidate per the stub: eventually-correct attempts differing in
      first-check correctness, distinguishing direct vs. revised correct). Freeze the
      representative-trajectory selection rule (medoid/quantile/nearest-to-median).
- [ ] **3.3 Sensitivity runs** across the frozen RQ4 alternatives; save the comparison
      table (Δ attempts, Δ ready %, Δ agreement, Δ primary RQ3 estimate); set the
      material-change threshold *before* looking.
- [ ] **3.4 Generate every table and figure from versioned outputs**, including
      `tab-validation-results`, `tab-sensitivity-results`, `fig-validation-results`,
      and the process figure.

### Phase 4 — Number-bearing prose (strict order: tables first, then text)
- [ ] **4.1 Empirical Study stubs:** corpus intro; setting/participants/items (with
      re-identification review); ethics & governance ×2 (verbatim approved language);
      analysis unit ×2; RQ3 analysis plan ×2. Replace the ≥200-student planning
      statement.
- [ ] **4.2 Results:** intro paragraph → validation subsection → process subsection
      (incl. representative trajectories) → sensitivity subsection → four-sentence RQ
      summary (no new statistics).
- [ ] **4.3 Discussion stubs:** opening conclusion; validation/sensitivity connection;
      RQ3 interpretation (behavioral description, cognitive claims as hypotheses).
- [ ] **4.4 Conclusion** (150–200 words; no numbers absent from Results).
- [ ] **4.5 Abstract:** fill all 8 placeholders from the frozen Results.

### Phase 5 — Parallel "no-dependency" track (start any time; independent of data)
- [ ] **5.1 Literature verification:** Helminen (2012) full text; resolve every
      `[verify]` flag; systematic ERIC/Scopus/WoS/ACM DL pass with 2024–2026
      EDM/LAK/ICER coverage; check the 2025 *C&E* review and 2026 arXiv tutorial;
      update the gap statement if a new close comparator surfaces.
- [ ] **5.2 Reference consolidation:** merge `subsec-literature-gap-draft.ptx` entries
      into `bookends/references.ptx`; adopt descriptive ids and retire the placeholder
      ids everywhere; add software/data citations.
- [ ] **5.3 Data-independent figures:** `fig-adapter-architecture` and
      `fig-running-trajectory` (synthetic, legally reproducible item), generated from
      source-controlled code or PreFigure.
- [ ] **5.4 Appendices from the implementation as-built:** `app-event-order`
      (ordering precedence, replay pseudocode, worked example) and `app-qc-rules`
      (full flag rulebook). `app-sensitivity` waits for Phase 1 freezes.
- [ ] **5.5 Notation appendix:** add final feature/model notation, prune unused symbols
      (finalize after 0.5).

### Phase 6 — Assembly and submission hygiene
- [ ] **6.1 Reproducibility section:** exact release/DOI, environment, config, source
      snapshot, one regeneration command; data-tier statement + synthetic corpus;
      clean-environment test.
- [ ] **6.2 Declarations:** all 7 statements in the selected journal's exact headings;
      approved ethics/data language verbatim; coauthor sign-off on CRediT and AI-use.
- [ ] **6.3 Word-budget pass** against the journal target (section budgets total roughly
      6,000–7,500 words as annotated); move schemas/rulebooks to the supplement (Gate 8).
- [ ] **6.4 Stub sweep** (Gate 9): grep `docs/source/paper1/` for `<warning>`, `[STUB`,
      `[verify]`, `[n]`, `[estimate]`, `???`; delete `app-author-master-checklist` and
      all author to-do remarks; audit claim boundaries and causal language.
- [ ] **6.5 Coauthor approval** of claims, declarations, and release package (Gate 10).

---

## Critical path and why this order

`0.1 journal → 0.2 governance → 1.x freezes → 2.x exports/validation → 3.x frozen
outputs → 4.x prose → 6.x assembly`

- **Journal first** because the word budget decides how much of the already-drafted
  framework/reconstruction text stays in the main text versus the supplement — writing
  more prose before knowing the budget risks redoing it.
- **Governance second** because nearly half the remaining stubs (ethics, sample counts,
  data availability, reproducibility tiers, declarations) cannot be written defensibly
  until the determination exists, and the analysis itself needs authorization.
- **Freezes before runs** (Gates 3 and 6 before headline numbers) — the manuscript's own
  discipline: choosing segmentation, inclusion rules, or the RQ3 contrast after seeing
  results would undermine the paper's central methodological argument.
- **Phase 5 runs in parallel throughout** — literature verification, the two conceptual
  figures, and Appendices B–C have no data dependency and represent the largest block of
  progress available *today*.
