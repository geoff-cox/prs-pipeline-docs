# Literature Verification — Full-Text Reads, 2026-07-17

Covers two items from the matrix's "Verification checklist before citing":
Helminen et al. (2012) — the last Section A row at abstract level — and the
2026 arXiv preprocessing tutorial flagged as a near-direct competitor.
Contents are paste-ready for `paper1-literature-matrix.md` and
`bookends/references.ptx`.

---

## 1 · Helminen et al. (2012) — read from full text (PDF on file)

### 1.1 CITATION ERROR FOUND — venue is wrong in both the matrix and references.ptx

Both currently cite *Koli Calling*. The paper's front matter and every ACM
record say **ICER '12**. The likely source of the confusion: the same group
published a *different* Parsons paper at Koli Calling 2012 (Karavirta,
Helminen, & Ihantola, "A mobile learning application for Parsons problems
with automatic feedback," Koli Calling '12, pp. 11–18 — do not conflate).

Corrected `references.ptx` entry (replaces `bib-helminen-2012`; resolves
`[verify pages]`):

```xml
<biblio type="raw" xml:id="bib-helminen-2012">
  Helminen, J., Ihantola, P., Karavirta, V., &amp; Malmi, L. (2012).
  How do students solve Parsons programming problems? An analysis of
  interaction traces.
  In <em>Proceedings of the Ninth Annual International Conference on
  International Computing Education Research (ICER '12)</em>
  (pp. 119&#x2013;126). ACM.
  <url href="https://doi.org/10.1145/2361276.2361300"/>
</biblio>
```

### 1.2 Replacement matrix row (Section A)

| Study | Interaction type | Raw data unit | State representation | Segmentation rule | Validation method | Analytic goal | Relevance to Paper 1 |
|---|---|---|---|---|---|---|---|
| Helminen, Ihantola, Karavirta & Malmi (2012), ICER '12:119–126 ✔ full text | 2D Parsons problems (js-parsons, Python): drag-and-drop code fragments; order **and** indentation; input area ↔ solution area | Full timestamped interaction trace: fragment insert / move (reorder, indent) / remove operations, plus all feedback requests | Solution modeled as a **graph over complete code states** (order + indentation); aggregate cross-student graphs; time-labeled individual paths; loop taxonomy (backtracking, circular loops, separate/concentrated sidetracks, jumbled combinations) | Per-assignment solving session, given by the environment (advance only after solving current); no segmentation policy stated | **None for the trace→state derivation** — preprocessing described in one sentence ("we implemented a tool that does preprocessing"); no independent-record comparison; findings informally cross-checked on a second course (CS2); a data fault (P1's non-unique solution) handled by omitting "a large portion" of that data | Visualize/explore solution paths; common patterns (linear top-down; control-structures-first); common incorrect states; feedback-use timing (>90% of first requests only after all lines placed; extremes to 62 requests); loops in 21–33% of paths | **Strongest state-level precedent in the interaction family.** Analyzes complete states and state revisits — but the environment records the trace directly, so reconstruction is never confronted as a problem; the derivation is undocumented and unvalidated; QC is ad hoc. Feedback-request analysis parallels Paper 1's checking features; the loop taxonomy is prior art for the deferred repeated-states work (F8/F21); their mid-study feedback redesign (minimal-set highlighting, chosen expressly to discourage trial-and-error) independently supports the feedback-policy-as-covariate stance |

### 1.3 Draft-claim verification

- "interaction traces reveal wide variation in solution paths" — **VERIFIED.**
  The paper reports notable cross-student variance: 453/444/781 distinct
  states on P3/P4/P5, with only 24/22/14 states appearing in ≥10% of
  solutions.
- Family claim "reconstructed intermediate states are absent, implicit, or
  heuristic, and never validated against independently recorded
  configurations" — **SURVIVES** (Helminen = "implicit": states present but
  derivation treated as given, unvalidated). However, the current sentence
  **undersells them**, and a reviewer who knows the paper could object that
  Helminen did analyze complete states. Recommended replacement in
  `sec-introduction.ptx` (and the draft file):

> For Parsons problems, the nearest construction-task sibling, interaction
> traces have even been analyzed as graphs over complete construction
> states, revealing wide variation in solution paths — yet the
> trace-to-state derivation is reported in a single sentence and compared
> against no independent record (<xref ref="bib-helminen-2012"/>); and
> large-scale log analyses evaluate adaptation with outcome and count
> features (<xref ref="bib-ericson-2018"/>).

### 1.4 Optional follow-on (new candidate row, not yet added)

Helminen, Ihantola, Karavirta, & Alaoutinen (2013), "How do students solve
Parsons programming problems? — Execution-based vs. line-based feedback"
— an experimental feedback-policy manipulation on the same task family;
candidate supporting citation for the feedback-policy-as-covariate
discussion. Verify venue/details before use.

---

## 2 · Hwangbo et al. (2026) — read from full text (LaTeX source on file)

### 2.1 Citation (resolves `[verify authors]`; replaces the draft's placeholder)

```xml
<biblio type="raw" xml:id="bib-hwangbo-2026">
  Hwangbo, D., Park, J., Jeon, M., &amp; Jin, I. H. (2026).
  Analyzing process data from computer-based assessments: A tutorial on
  preprocessing, feature extraction, and model-based inference.
  <em>arXiv:2604.16900</em> [stat.AP].
  <url href="https://doi.org/10.48550/arXiv.2604.16900"/>
</biblio>
```

### 2.2 The three questions from the abstract-level read — answered

1. **Does state reconstruction appear anywhere in their preprocessing?**
   No. The terminal preprocessing product is explicitly the action sequence
   s = (a₁, …, a_T) over a finite action alphabet — one row per meaningful
   action. "Sequence construction" is named among the consequential
   decisions, but complete response states are never built; their notation
   contains no state object at all.
2. **What do "cross-method consistency checks" compare?** Two things,
   neither of which is validation against independent ground truth:
   (a) LLM-generated preprocessing code is checked against the *authors'
   own* manually written reference scripts (executability + output match);
   (b) "cross-method consistency" means whether similar *substantive
   conclusions* emerge when different analytic families are applied to one
   common item. Nothing compares derived data to an independently recorded
   platform record — the exact role Paper 1's check anchors fill.
3. **Segmentation / case definition?** Inherited from the platform: logs
   are grouped by item and PIAAC's SEQID; only boundary events (the start
   marker, final submission clicks) are discussed, as choices to be
   "explicitly documented." Attempt segmentation never arises as a problem.

### 2.3 Replacement matrix row (Section B — replaces the abstract-level row)

| Study | Interaction type | Raw data unit | State representation | Segmentation rule | Validation method | Analytic goal | Relevance to Paper 1 |
|---|---|---|---|---|---|---|---|
| Hwangbo, Park, Jeon & Jin (2026), arXiv:2604.16900 ✔ full text | PIAAC PS-TRE items (Email / Spreadsheet / Web interfaces) | Event-level logs → one row per consolidated action | **Action sequences s = (a₁,…,a_T); no response states.** Coarser `merged_event` recoding for model-based methods | Per-item sequences given by platform SEQID; only boundary-event inclusion is a documented choice | LLM-generated code vs. authors' own reference scripts; "cross-method consistency" = agreement of conclusions across analytic families on one item — **no comparison against independently recorded ground truth** | Tutorial standardizing the sequence-level pipeline: timestamp correction, dedup, core–ancillary consolidation, LLM-assisted standardization → n-grams/TF-IDF, MDS, process-informed DIF; HMMs, subtask identification; reproducible R code | **Confirms rather than closes the gap.** The newest systematization still terminates preprocessing at the action sequence. Their own framing is direct 2026 authority for Paper 1's motivation and RQ4: many studies "provide little detail on how raw log events were cleaned"; "systematic evaluations of preprocessing workflows remain limited"; their time-threshold consolidation is, in their words, "inherently heuristic." Platform specificity acknowledged (core–ancillary rules must be re-derived per platform) — contrast with Paper 1's canonical-contract adapters. Their LLM-assisted standardization vs. Paper 1's deterministic, provenance-preserving replay is a clean philosophical contrast |

### 2.4 Suggested one-sentence use in the related-work subsection

Position it in the "traditions begin after the objects are defined"
paragraph: even the most recent tutorial systematizing process-data
preprocessing delivers analysis-ready *action sequences* as its end
product, validates generated code only against the authors' own reference
implementation, and inherits the platform's per-item case definition
(<xref ref="bib-hwangbo-2026"/>).

---

## 3 · Matrix checklist updates

- [x] Read the full text of Helminen et al. (2012) — **done 2026-07-17**;
  row replaced; venue corrected (ICER '12, not Koli Calling); pages 119–126;
  DOI 10.1145/2361276.2361300.
- [x] Check the 2026 arXiv tutorial for comparators this matrix lacks —
  **done 2026-07-17**; no missed comparator found; row replaced; citation
  completed (Hwangbo, Park, Jeon, & Jin).
- [ ] Check the 2025 *Computers & Education* review (needs full text —
  likely VMI library).
- [ ] Systematic database pass (ERIC / Scopus / WoS / ACM DL / Scholar),
  2024–2026 EDM/LAK/ICER emphasis.
- [ ] Remaining `[verify]` bibliographic flags (batchable via publisher
  pages).
- [ ] Replace placeholder entries in `references.ptx` (do last, after
  verification).
