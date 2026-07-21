# Literature Matrix — Paper 1 (Drag-and-Drop Response Trajectories)

Fulfills Literature Synthesis Checklist item 2: columns for interaction type, raw data
unit, state representation, segmentation rule, validation method, and analytic goal.
A final column maps each study to Paper 1's positioning.

**How to read this matrix**

- `[?]` = not determinable from the abstract/snippet reviewed; **verify against the full
  text before citing.** Most rows were compiled from web search results (July 2026).
  **Exception — verified from full texts (2026-07-16):** Kroehne & Goldhammer (2018),
  Jiang et al. (2021), Gong et al. (2022), and Goldhammer et al. (2021) in Section A.
  Helminen et al. (2012) and all rows in Sections B–G remain abstract-level; citation
  details flagged `[verify]` still need confirmation.
- Sparse cells in *State representation*, *Segmentation rule*, and *Validation method*
  are not a defect of the matrix — they are the gap. Most studies leave these
  choices implicit; documenting that silence is part of the related-work argument.
- Suggested extensions as you read: add columns for BibTeX key, venue type
  (journal/conference/chapter), read status, and direct quotes with page numbers.

---

## A. Closest methodological comparators (checklist item 6 — the papers the gap statement must survive)

| Study | Interaction type | Raw data unit | State representation | Segmentation rule | Validation method | Analytic goal | Relevance to Paper 1 |
|---|---|---|---|---|---|---|---|
| Kroehne & Goldhammer (2018), *Behaviormetrika* 45(2):527–563 ✔ full text | Generic technology-based assessment; demonstrated on a PISA 2015 context-questionnaire item battery (12 questions on one screen; 5,736 students; 91,189 events) | Timestamped log-event tuples ⟨i,t,x,(e)⟩, situated in a paradata taxonomy (access-, response-, process-related) | FSM states = theoretically defined *phases of the response process* ("Reading stem & Q01", "Answering Q02"), defined top-down from an assessment framework — not complete answer configurations | Event-triggered transitions with guards, variables, and look-ahead operators (is_last_event, nearest_event_is); each test-taker's event stream replayed through the FSM from s₀ | Four completeness conditions (response-, progress-, replay-, state-completeness); **verification proposals (§6.2): compare substantive data re-derived from logs against independently stored responses, expecting a perfect match; use FSM acceptance to flag unexpected events**; empirical check = relation of extracted item-level times to responses (inverse u-shape) | Generic framework (+ LogFSM) for deriving indicators from reconstructed state sequences; empirical application extracts item-level response times from item batteries | **Closest framework comparator — sharper after full-text reading.** Articulates the *principle* of log-vs-record verification but does not implement it as a quantified validation study; states are process phases, not item configurations; no authored-source alignment; no readiness/QC policy. Bonus: §2.3.1 states that complex item formats log only incremental differences, so the full trace is required to reconstruct the response — direct support for Paper 1's premise |
| Jiang, Gong, Saldivia, Cayton-Hodges & Agard (2021), *Large-scale Assess. in Educ.* 9, Art. 2 ✔ full text | NAEP 2017 digital math drag-and-drop items (grade 4, n = 28,385; grade 8, n = 29,504) | Logged Add/Remove/Move/Clear actions with source–target labels (Add_s2_t1) plus timestamps | Action sequences and derived measures: sequence length, answer-change patterns, four strategy classes, nine time measures; no maintained board-state object between actions | Item visits (time on other items excluded); 90% winsorization of all time measures; strategy classification keeps only the first completed action per target and discards revisions | None for the preprocessing itself; exclusions for not-reached, unattempted, and improperly captured process data reported but not systematized; process measures framed as supplying validity evidence for item scores | Describe cognitive/metacognitive strategies, misconceptions, and efficiency by score group | **Closest same-interaction empirical study.** States that no published study had examined D&D problem-solving in large-scale math. Preprocessing is pragmatic and unvalidated (winsorization, first-action filtering) — precisely the seam Paper 1 opens |
| Gong, Jiang, Saldivia & Agard (2022), *Behavior Research Methods* 54(1):117–132 ✔ full text | Three NAEP 2017 math D&D items (matching decimals; classifying fractions; completing a multiplication; ~28k–30k students each) | Adding, removing, and clearing actions from process data | **Complete target configurations as states** (e.g., "0.20 \| 0.02 \| 2.5"), organized into stages by number of filled targets/sources; action sequences transcribed into transitions between these states | Stages defined by answer completeness; transcription performed "in a heuristic way"; infrequent transitions (thickness < 5) and resulting dead-end states pruned, acknowledged to break some students' sequences | None — transcribed states are not checked against any independent record; no admissibility or QC layer | Item-level Sankey visualization of step-by-step answer formulation; deduce response strategies | **Upgraded after full-text reading: the nearest thing to trajectory reconstruction on D&D items.** Reconstructs complete configurations, but heuristically, for display, without validation, segmentation policy, or QC. Note: NAEP logs carry self-contained source→target labels, so no authored-source alignment problem arises — unlike Runestone cardsort logs, where item semantics live in the PreTeXt source |
| Helminen, Ihantola, Karavirta & Malmi (2012), Koli Calling | Parsons problems (js-parsons) | Interaction traces: insert/remove/reorder events at statement level | Evolving program-construction states | Puzzle-construction sessions `[?]` | `[?]` | Characterize variation in solution paths among mostly-successful solvers | Nearest interaction sibling; Runestone also hosts Parsons → motivates cross-widget future work |
| Goldhammer, Hahnel, Kroehne & Zehner (2021), *Large-scale Assess. in Educ.* 9, Art. 20 ✔ full text | Generic; PIAAC Job Search item and a multiple-document-comprehension sourcing test as running examples | Log events → low-level features (*actions* at a point in time; *states* as assumed sub-processes, identified via FSMs per Kroehne & Goldhammer) | Two-step evidence identification: log events → low-level features → process indicators, within an ECD student/evidence/task-model structure | n/a (conceptual); granularity of states and actions explicitly left to the researcher | Argument-based validation of the **explanation inference** (construct representation + nomothetic span, with two worked examples); the prior **scoring inference** — that identification rules extract the targeted behavioral features correctly — is stated as an assumption | Framework for validating construct interpretations of process indicators | Measurement-theoretic backbone — and a precise slot for Paper 1: check-anchor validation supplies empirical evidence for the scoring/evaluation inference that this framework presupposes but does not itself test |

## B. Educational process mining and sequence methods (checklist item 3)

| Study | Interaction type | Raw data unit | State representation | Segmentation rule | Validation method | Analytic goal | Relevance to Paper 1 |
|---|---|---|---|---|---|---|---|
| Bogarín, Cerezo & Romero (2018), *WIREs DMKD* 8(1):e1230 | LMS / e-learning environments (survey) | Event logs | Discovered process models (Petri nets, fuzzy models, …) | Case/trace notion assumed given | Conformance checking (model vs. log, not log vs. ground truth) | Survey of discovery, analysis, visualization of educational processes | Assumes event semantics predefined; "validation" means model fit, not data fidelity — both points feed the gap statement |
| Trcka, Pechenizkiy & van der Aalst (2010), *Handbook of EDM*, 123–142 | Educational event data (chapter) | Event logs | Process models | Assumed given | Conformance checking | Introduce process mining to EDM | Foundational citation for the EPM lineage |
| van der Aalst (2016), *Process Mining* (2nd ed.), Springer | Generic business/education processes | Event logs (case, activity, timestamp) | Process models | Case identification assumed | Conformance checking, replay fitness | Textbook foundation | Already in references.ptx; note its replay-fitness concept differs from Paper 1's state-level anchor agreement |
| He & von Davier (2015, Springer vol.; 2016, IGI handbook) | PIAAC problem-solving (PSTRE) items | Coded action sequences per item | n-gram features of action sequences | Per-item sequences (given) | Association with performance; cross-country consistency of patterns | Detect action patterns tied to success/failure | Standard feature-level comparator; operates on sequences without reconstructing full states |
| Tang, Wang, He, Liu & Ying (2020), *Psychometrika* 85(2); Tang, Wang, Liu & Ying (2021), *BJMSP* 74(1); Tang et al. (2021), ProcData, *Psychometrika* 86(4) | PISA climate-control item and similar interactive items | Action sequences (autoencoder variant adds time) | Latent feature vectors (MDS embedding; seq2seq autoencoder) | Per-item sequences (given) | Sequence reconstruction accuracy; outcome-prediction performance | Generic automated feature extraction from process data | The "learned features" alternative to Paper 1's interpretable baseline features; useful contrast on interpretability and item-semantics awareness |
| Chen, Li, Liu & Ying (2019) `[verify venue]` | Interactive problem-solving items | Action sequences with timestamps | Event-history representation | `[?]` | `[?]` | Event-history analysis of process data | Timing-aware modeling comparator |
| Ulitzsch, He & Pohl (2022), *JEBS* 47(1):3–35 | Interactive assessment tasks | Action sequences | Mined subsequences | `[?]` | `[?]` | Sequence mining to understand incorrect behavioral patterns | Overlaps RQ3's error-profile interest at the sequence level |
| arXiv 2604.16900 (2026), tutorial on process-data preprocessing, feature extraction, model-based inference `[verify authors]` | Computer-based assessment items | Log events / action sequences | n-grams with boundary tokens; model-based features | Discussed as preprocessing step `[?]` depth | `[?]` | Tutorial standardizing the process-data pipeline | **Near-direct competitor for the preprocessing discussion.** Read closely: what does it formalize vs. leave implicit? |

## C. Process data in large-scale assessment — context and reviews

| Study | Interaction type | Raw data unit | State representation | Segmentation rule | Validation method | Analytic goal | Relevance to Paper 1 |
|---|---|---|---|---|---|---|---|
| Bergner & von Davier (2019), *JEBS* 44(6) `[verify issue]` | NAEP digital assessments (review) | Log/process data | Five-level hierarchy of process-data use (outcome-only → process-as-outcome) | n/a | n/a | Historical review + taxonomy | Ready-made positioning device: Paper 1 builds the validated substrate that levels 2–5 presuppose |
| Anghel, Khorramdel & von Davier (2024), *Large-scale Assess. in Educ.* 12 | PISA/TIMSS/NAEP (review) | Log-file data; notes contested definition of "process data" | n/a | n/a | n/a | Literature review of process-data use in LSAs | One-stop citation for scale of the field + definitional disputes worth echoing in the introduction |
| *Computers & Education* (2025) systematic review, doi 10.1016/j.compedu.2025.105245 `[verify authors]` | LSAs + game-, scenario-, simulation-based and LMS-embedded assessments | Log-based process data | n/a | n/a | n/a | Systematic review of log-based process data in computer-based assessment | Most recent field map; check its identified gaps against Paper 1's claims |
| Greiff, Wüstenberg & Avvisati (2015), *Computers & Education* 91:92–105 | PISA 2012 complex problem-solving items | Log files | Strategy indicators (e.g., exploration behavior) `[verify]` | `[?]` | `[?]` | Show log files reveal problem-solving behavior ("window into students' minds") | Influential early study; its title embodies the interpretive overreach ch-validity warns against — citable as a foil, respectfully |

## D. Response-process validity (checklist item 4)

| Study | Interaction type | Raw data unit | State representation | Segmentation rule | Validation method | Analytic goal | Relevance to Paper 1 |
|---|---|---|---|---|---|---|---|
| AERA/APA/NCME (2014), *Standards for Educational and Psychological Testing* | All assessment | n/a | n/a | n/a | Response processes as one of five sources of validity evidence | Professional standards | Anchor citation for response-process evidence |
| Ercikan & Pellegrino, eds. (2017), *Validation of Score Meaning…*, Routledge/NCME | Assessment broadly; response processes via verbalizations, eye movements, response times, clicks | Varies by chapter | Varies | Varies | Argument-based validation using response-process evidence | Establish response-process validation practice | Frames why validated trajectories matter; notes such data are rarely used in validation — supports the paper's motivation |
| Zumbo & Hubley, eds. (2017), *Understanding and Investigating Response Processes in Validation Research*, Springer | As above | Varies | Varies | Varies | Varies | Companion volume on response-process research | Cite alongside Ercikan & Pellegrino; Newton (2019, *Assessment in Education* 26(2)) reviews both — efficient synthesis citation |
| Goldhammer & Zehner (2017), *Measurement* 15(3–4):128–132 | Process data generally | Log data | n/a | n/a | n/a | Commentary: what to make of and how to interpret process data | Compact citation for interpretive restraint (behavioral description ≠ cognitive inference) |

## E. Preprocessing sensitivity — RQ4's intellectual home

| Study | Interaction type | Raw data unit | State representation | Segmentation rule | Validation method | Analytic goal | Relevance to Paper 1 |
|---|---|---|---|---|---|---|---|
| Kovanović, Gašević, Dawson, Joksimović, Baker & Hatala (2015), *J. Learning Analytics* 2(3):81–110 | LMS activity (online + blended courses) | Trace data (timestamped actions) | Time-on-task estimates | **The manipulated variable:** alternative idle-threshold / last-action estimation schemes | Compare downstream model results across estimation schemes | Show time-on-task estimation choices shape findings | Direct ancestor of RQ4's analytic-idle-threshold sensitivity; also notes estimation details are rarely reported |
| Knobbout, Everaert & van der Stappen (2019), Bled eConference | Moodle courses (6-course minor program) | LMS log data (79% of activities not linked to a course) | Time-on-task per course | **The manipulated variable:** 12 cleaning variants from reasonable assumptions about unlinked activities | Compare outcomes across the 12 cleaned datasets | Show cleaning choices produce "multiple versions of truth" | Second preprocessing-sensitivity exemplar; widely varying per-student estimates parallel RQ4's readiness-inclusion comparisons |
| Romero, Romero & Ventura (2014), "A survey on pre-processing educational data," in *Educational Data Mining*, Springer, 29–64 | Educational data broadly | Raw educational datasets | n/a | Surveyed as one preprocessing step among many | n/a | Survey preprocessing practice in EDM | Establishes preprocessing as a recognized stage; Paper 1's move is elevating it to measurement |
| Steegen, Tuerlinckx, Gelman & Vanpaemel (2016), *Perspectives on Psych. Science* 11(5):702–712; Gelman & Loken (2014), *American Scientist* 102 | Any empirical analysis | Raw data | The multiverse: all datasets arising from reasonable processing choices | **The manipulated variable:** every defensible processing decision | Report results across the full multiverse; identify choices conclusions hinge on | Transparency about researcher degrees of freedom | Framing device: RQ4 = a prespecified processing multiverse for trajectory reconstruction |

## F. Drag-and-drop, sorting, and construction item family (checklist item 5)

| Study | Interaction type | Raw data unit | State representation | Segmentation rule | Validation method | Analytic goal | Relevance to Paper 1 |
|---|---|---|---|---|---|---|---|
| Arslan et al. (~2020), *Educ. Measurement: Issues & Practice* `[verify citation]` | Experimental drag-and-drop items (matching, categorizing, ranking, sequencing) | Process data incl. pauses | `[?]` | `[?]` | Experimental manipulation of item layouts | Effect of D&D design features on performance and response strategies; notes design rests on judgment, not evidence | Item-design covariates (P, R, decoys, layout) matter — supports treating item structure as first-class metadata |
| Ponce, Mayer & Loyola (2021), *J. Educational Computing Research* `[verify volume]` | Drag-and-drop response interactions | `[?]` | `[?]` | `[?]` | `[?]` | Test performance and efficiency effects of D&D interactions | Secondary comparator on the interaction format |
| *Contemporary Educ. Psychology* (2026), doi 10.1016/j.cedpsych… S0361476X26000196 `[verify authors]` | D&D vs. drop-down vs. click-on-grid; ordering and categorization tasks | Process data | `[?]` | `[?]` | Format comparison (experimental) | Response formats differ in construct-irrelevant cognitive processes elicited | Recent evidence that interaction format shapes process data — relevant to portability and item-covariate discussions |
| Smith et al. (2013), *CBE—Life Sciences Education* 12(4):628–644 (Biology Card Sorting Task) | Physical/computerized card sorting | **Final sorts only** | Surface- vs. deep-feature category structures | n/a (endpoint analysis) | Expert–novice contrast on sorting measures | Measure conceptual organization via sorting | The sorting-assessment literature analyzes endpoints — trajectory-level card-sort data is unexamined territory |
| TPL-KATS card sort, *Behavior Research Methods* `[verify authors/year]` | Computerized card sorting for structural knowledge | Final sorts | Category structures vs. referent structure | n/a | Comparison to expert referent | Structural-knowledge assessment tool | Same endpoint-only pattern; strengthens the gap for sorting tasks specifically |
| Ericson et al. — adaptive Parsons line: Ericson, Foley & Rick (2018, ICER); "Investigating the Affect and Effect of Adaptive Parsons Problems" (log analysis of 8,000+ users) `[verify venue/year]`; Haynes & Ericson (2021, CHI) | Parsons problems on Runestone | Runestone event logs | Solved/attempt outcomes; help-use behaviors | `[?]` | `[?]` | Effects of adaptation on correctness, efficiency, cognitive load | Same platform, sibling widget; their log analyses use outcome/count features, not reconstructed trajectories |

## G. Platform and data infrastructure (for the data-canonical section)

| Study | Interaction type | Raw data unit | State representation | Segmentation rule | Validation method | Analytic goal | Relevance to Paper 1 |
|---|---|---|---|---|---|---|---|
| Ericson, YeckehZaare & Guzdial (2019), ICER | Runestone ebook interactions (all widget types) | Logged interaction records (timestamp, user, event, act, item id) | n/a | n/a | n/a | Describe Runestone as a research platform and its recorded data | Authoritative description of the event source Paper 1 decodes |
| Ericson & Miller (2020), SIGCSE, 1240 `[verify pages]` | Runestone platform | As above | n/a | n/a | n/a | Platform paper | Companion platform citation |
| Koedinger, Baker, Cunningham, Skogsholm, Leber & Stamper (2010), *Handbook of EDM*, 43–55; Koedinger et al. (2013), *Topics in Cognitive Science* 5 | Tutor/course software transactions | DataShop transaction format (student–software transactions) | Correctness-coded transactions mapped to knowledge components | Transaction/problem-view structure given by format | n/a (repository paper) | Shared repository + analysis tools | Defines the DataShop-format lineage of Runestone's `.tab` export; contrast: transactions are pre-interpreted, whereas cardsort rows need decoding + replay |
| Leijten & Van Waes (2013), *Written Communication* 30(3):358–392 | Keyboard text composition | Keystroke log (all keystrokes, deletions, timing) | Evolving text state; S-notation for revision structure | Pauses/bursts/revision episodes | `[?]` (tool-internal consistency) | Register and reconstruct writing processes (Inputlog) | Cross-domain twin: state reconstruction from incremental input events; shows the problem recurs beyond D&D and lends the framing external weight |

---

## What the matrix already shows (seed observations for the gap statement)

1. **State representation.** Full-text reading corrects the first draft of this
   observation: Gong et al. *do* reconstruct complete target configurations from action
   sequences — heuristically, for Sankey visualization, with infrequent transitions
   pruned. Kroehne & Goldhammer reconstruct sequences of theoretically defined process
   phases. What remains absent across the matrix is reconstruction of complete,
   item-semantics-aligned configurations treated as *validated measurement objects*
   rather than display artifacts or coarse phase labels.
2. **Segmentation.** Outside section E, segmentation is inherited from the platform or
   handled by unexamined pragmatic rules (Jiang et al.: 90% winsorization,
   first-action filtering; K&G: guards and look-ahead operators fixed once). Only the
   preprocessing-sensitivity literature treats these choices as reportable and variable;
   no study in sections A–D varies them systematically.
3. **Validation.** Where "validation" appears, it means model fit (conformance
   checking), outcome prediction (feature extraction), or construct validation
   (section D). **Important correction from the full texts:** Kroehne & Goldhammer
   explicitly articulate the *principle* of check-anchor-style verification — under
   response-completeness, responses re-derived from logs can be compared with
   independently stored responses, expecting a perfect match (§6.2). Paper 1 therefore
   cannot claim the idea is unprecedented. What remains unoccupied is its systematic
   empirical implementation: quantified anchor-agreement rates with uncertainty,
   mismatch-distance analysis, manual audit plus synthetic fault injection, and a
   readiness policy that gates downstream analyses. Cite K&G as the intellectual
   ancestor, then deliver what they propose. In Kane's terms (via Goldhammer et al.
   2021), this is empirical evidence for the *scoring inference* that the validity
   literature assumes.
4. **Interaction coverage.** The drag-and-drop rows analyze action sequences,
   heuristically transcribed state sequences (Gong et al.), or endpoints; the
   sorting-assessment rows analyze endpoints only. A validated, source-aligned
   trajectory representation for card-to-zone items still fills a visible hole at the
   intersection.

Draft gap statement implied by the matrix (revised after full-text reading of four
Section A comparators): existing sequence, process-mining, and feature-extraction
methods presuppose that event types, response states, and analysis units have been
correctly derived; the closest reconstruction frameworks articulate completeness and
verification in principle without implementing them as validation studies; and existing
drag-and-drop, sorting, and Parsons studies analyze action sequences, heuristically
transcribed states, or final configurations that are never checked against independent
records. Source-dependent card-to-zone logs therefore require — and currently lack — an
explicit, source-aligned, empirically validated, and sensitivity-tested transformation
from platform rows to complete response trajectories.

## Verification checklist before citing

- [ ] Confirm every remaining `[verify]` citation detail against the publisher page or DOI.
- [x] Read full texts for Section A rows 1–3 and 5 (K&G 2018; Jiang et al. 2021;
      Gong et al. 2022; Goldhammer et al. 2021); `[?]` cells filled 2026-07-16.
- [ ] Read the full text of Helminen et al. (2012) — the one Section A row still
      at abstract level.
- [ ] Run the systematic database pass (ERIC, Scopus/WoS, ACM DL, Google Scholar) per
      checklist item 1; add rows for anything the web search missed, especially
      EDM/LAK/ICER 2024–2026 papers.
- [ ] Check the 2025 *Computers & Education* review and the 2026 arXiv tutorial for
      comparators this matrix lacks.
- [ ] Replace the placeholder entries in backmatter references.ptx with the four
      strongest rows (process mining, sequence analysis, response-process validity,
      intermediate states in interactive assessment).
