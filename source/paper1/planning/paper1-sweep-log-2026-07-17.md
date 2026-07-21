# Literature Sweep Log — 2024–2026 Comparator Pass, 2026-07-17

Fulfills (in approximation) the matrix checklist item: "Run the systematic
database pass … add rows for anything the web search missed, especially
EDM/LAK/ICER 2024–2026 papers."

**Method and honest scope note.** Web-search pass (Anthropic search index)
run 2026-07-17, seven queries, snowballing from hit reference lists.
This approximates Google Scholar/ERIC coverage; it is **not** a PRISMA-grade
pass of Scopus/WoS/ACM DL with logged result counts. Before the manuscript
claims a "systematic" related-work search, either (a) run the library-database
queries below with documented counts (VMI access), or (b) soften the claim to
"structured search." The strongest remaining lever is (c): the *C&E* 2025
review screened 2,548 → 330 studies under PRISMA — scanning its included-study
table for drag-and-drop/sorting rows effectively piggybacks on their
systematic pass and should be done during the full-text read.

## Query log and dispositions

| # | Query | Outcome |
|---|---|---|
| 1 | drag-and-drop items process data analysis 2025 | Noise (BI software); discarded, rephrased |
| 2 | drag-and-drop technology-enhanced items process data log assessment study | Confirmed known comparators (Gong 2022, Jiang 2021, Ponce 2021, CEP 2026, C&E 2025 review); no new close comparator |
| 3 | "systematic review" "log-based process data" "computer-based assessments" … | C&E review details (PRISMA, 2548→330); authors NOT resolved → library task. New candidates: Chen/Liu/Mao 2024 protocol; arXiv 2403.14908 |
| 4 | Parsons problems process data interaction log analysis 2024 2025 | Active 2024–2026 Parsons literature is intervention-focused (fading, adaptivity, LLM-era variants; SIGCSE'26, Koli'25, ITiCSE'25); **no trace-to-state reconstruction methodology found** |
| 5 | reconstructing response states event logs replay validation educational assessment | Education hits already in matrix (Goldhammer 2021). Replay-with-validation lives in software engineering/forensics (event sourcing, program-state replay) — cross-domain color, no educational comparator |
| 6 | card sorting task process data log trajectory analysis education | Endpoint-only pattern confirmed; one new candidate (Sizemore et al., chemistry card sorts + ML on written justifications — still final sorts) |
| 7 | Runestone Academy log data analysis study ebook interactions research | **Same-platform collision check: clear.** Runestone research = platform papers + adaptive-Parsons line (already in matrix). Found citable log-schema source (SPLICE 2021) |

## Verdict on the gap statement

**No 2024–2026 work found that reconstructs complete response states from
incremental logs and validates them against independently recorded
configurations.** The gap statement survives the sweep unchanged. Recent
activity adjacent to the gap (Hwangbo tutorial; C&E review; format-comparison
experiments) consistently terminates at action sequences or endpoints.

## Candidate additions (verify details before citing)

1. **arXiv:2403.14908 (2024)** — multi-state survival modeling of reaction
   times between/across action sequences, international online assessment.
   → Section B candidate row: timing-aware modeling on *given* sequences;
   sits beside Chen et al. (2019) event-history line. `[verify authors/venue]`
2. **Sizemore et al., chemistry card sort + ML** (OSTI copy located) —
   final sorts augmented with free-form written justifications, unsupervised
   clustering. → Section F candidate row: modernizes the endpoint-only
   pattern; strengthens "sorting analyzes final sorts only." `[verify venue/year]`
3. **Ericson (2021), SPLICE@SIGCSE, "Runestone's Question Bank, Exam
   Generator, and Log Data"** — documents the log-entry schema (timestamp,
   sid, event, act, div_id, course_id, chapter, subchapter) in print.
   → Section G candidate: authoritative citation for the exact export format
   `sec-data-canonical` decodes. `[verify pages]`
4. **Du, Luxton-Reilly, & Denny (2020), ACE'20, "A review of research on
   Parsons problems"** — review anchor for the Parsons lineage sentence.
   `[verify pages]`
5. **Chen, Liu, & Mao (2024), PLOS ONE** — scoping-review *protocol* on log
   file data (pre-processing, methods, frameworks). Context citation at
   most; screened out as comparator (protocol, not results).

## Notable detail worth exploiting (verify first)

The Runestone research-platform paper states the platform records, for
Parsons problems, **every block move plus the contents of the source and
solution areas** (state-bearing entries like `start|6_05_0-4_0-2_3_0-0_1_0|…`),
whereas cardsort logs record incremental moves with complete configurations
only at checks. If verified against the platform paper and your exports, this
per-widget logging contrast is a crisp motivating sentence: *on the very same
platform*, the sibling widget logs state snapshots while card-to-zone items
require reconstruction — the problem is real, local, and not hypothetical.

## Remaining verification items (updated)

- [ ] *C&E* 2025 review: resolve authors + scan the 330 included studies for
  drag-and-drop/sorting rows (library full-text; highest-value remaining item)
- [ ] CEP 2026 (S0361476X26000196): resolve `[verify authors]` (library)
- [ ] Formal Scopus/WoS/ACM DL queries with logged counts, if the
  "systematic search" claim is kept
- [ ] Mechanical `[verify]` batch (Bergner pages, Ponce volume, Smith
  trailing authors, TPL-KATS authors/year, Arslan full citation, Ericson
  2018 venue/pages, He & von Davier page range, Chen 2019 venue, Kovanović
  2015 details, new candidates 1–4 above)
- [ ] References consolidation into `references.ptx` (last)
