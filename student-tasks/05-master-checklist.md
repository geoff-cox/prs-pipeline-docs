# PROTEUS Undergraduate RA — Master Checklist


## Aug 8 Meeting

- [ ] Compare both students' episode codings
- [ ] Discuss every divergence to consensus or open-question status.

## Exercise 2, Part 1: blind pass

- [ ] **D1** (each) Receive your batch assignment (see X4) and confirm the response count.
- [ ] **D2** (each) Copy `templates/blind-pass-sheet.csv` to `blindpass-<yourname>.csv`; add a `legend` tab.
- [ ] **D3** (each) Code responses 1–5: one row per episode; `own_words_rule` + invented `my_category` per row.
- [ ] **D4** (each) Code responses 6–10.
- [ ] **D5** (each) Code responses 11–15 (and 16–20 if assigned).
- [ ] **D6** (each) Reconcile your category legend: merge duplicate labels *of your own*, finalize one-line definitions, add use-counts.
- [ ] **D7** (each) Sweep for hygiene: every `confidence`=1 row has a note; every incomplete episode has `complete`=0; verbatim columns are actually verbatim.
- [ ] **D8** (each) Record total coding time (sittings, start/stop) in your memo.
- [ ] **D9** (each) Submit sheet + legend; **stop and wait for clearance.**
- [ ] **D10** (each) Write 3 sentences: the hardest response in your batch and why (goes in memo).

## Phase E — Exercise 2, Part B: reveal & recode *(gate: both D9s in + X5 clearance)*

- [ ] **E1** (each) Read the sealed companion (`02-codebook-companion-SEALED.md`), twice.
- [ ] **E2** (each) Read the codebook CSV (`[FILENAME]`), all ten entries, twice.
- [ ] **E3** (each) Read the now-unrestricted vocabulary-draft and codebook-CSV sections of `ch-technical-notes.ptx`; log feedback as usual.
- [ ] **E4** (each) Recode your Part A batch: fill `code` per companion §4 (single / ALT / NONE / squint). Do not alter Part A columns.
- [ ] **E5** (each) Write the comparison memo (½–1 page) per companion §4.
- [ ] **E6** (each) Submit updated sheet + memo.
- [ ] **E7** Debrief meeting: side-by-side comparison of both coders' sheets; catalog agreements, divergences, and all `NONE`s.
- [ ] **E8** From E7, draft the list of proposed codebook clarifications and candidate new codes for the group.
- [ ] **E9** Update Handbook to v0.2 with rules clarified in C6/E7; both students re-read the diff.

## Phase F — Vocabulary & codebook review prep *(gate: Phase E; feeds the group meeting)*

- [ ] **F1** (each) Written position (2–4 sentences) on merging `vars_gt_eqs` / `vars_gt_rows`, grounded in your batch.
- [ ] **F2** (each) Written position on merging `no_solution` / `system_inconsistent`.
- [ ] **F3** (each) Written position on folding `more_than_one_solution` into `infinite_solutions`.
- [ ] **F4** (each) List vocabulary terms you *needed* during recode that don't exist (with the response IDs that needed them).
- [ ] **F5** (each) List vocabulary terms you never used once.
- [ ] **F6** (each) Flag every paraphrase in your batch that the listed surface forms would *miss* (verbatim phrase + the term it should map to).
- [ ] **F7** Merge both students' F1–F6 into one review-prep document for the group meeting.
- [ ] **F8** (each) Note any response in your batch citing a theorem/proposition by number → feeds the open theorem-reference policy question.
- [ ] **F9** (each) Check your batch for any evidence of the currently-unattested codes (CS2 rightmost-column, CS8 parametric form, CS10 degrees of freedom); report presence/absence.
- [ ] **F10** Present F7 at the group vocabulary-review meeting; record decisions.

## Phase G — Pattern authoring for the codebook *(gate: F10 decisions recorded; spreadsheet work)*

- [ ] **G1** Confirm which vocabulary version the patterns are written against (post-F10).
- [ ] **G2** Split the seven unauthored codes between the two students (suggested: alternate).
- [ ] **G3** For each assigned code: harvest `example_response_ids` from the coded sets.
- [ ] **G4** For each assigned code: draft `surface_markers` from verbatim student phrases.
- [ ] **G5** For each assigned code: draft `patterns` in `premise=… AND conclusion=…` syntax; log any vocabulary gap instead of inventing terms.
- [ ] **G6** For each assigned code with zero attested examples: record "no surface evidence in [set]" explicitly.
- [ ] **G7** Swap: each student reviews the *other's* drafted rows and marks anything they'd match differently.
- [ ] **G8** Resolve swap comments; deliver the filled six-column codebook CSV to [PI NAME].
- [ ] **G9** One-paragraph confidence note per code: how solid are these patterns and what would improve them?

## Phase H — Independent coding of the held-out set *(gate: X6 frozen codebook + X7 question selection; question count pending [DEC-4] — H5–H7 flex accordingly; this is the gold standard)*

- [ ] **H1** (each) Confirm in writing which handbook version and codebook version you are coding under (they are frozen for this phase).
- [ ] **H2** (each) Calibration pass: code a shared 5-response calibration set — a fresh set, distinct from the Exercise 1 warm-up; quick sync meeting to confirm the protocol is stable *before* the real batch.
- [ ] **H3** (each) Code held-out question 1, batch 1, fully independently, full episode + CS coding.
- [ ] **H4** (each) Code held-out question 1, batch 2.
- [ ] **H5** (each) Code held-out question 2, batch 1.
- [ ] **H6** (each) Code held-out question 2, batch 2.
- [ ] **H7** (each) Code held-out question 3 (if assigned).
- [ ] **H8** (each) Hygiene sweep (as D7) + total-time report per question.
- [ ] **H9** (each) Submit sheets; do not discuss until agreement stats are computed.
- [ ] **H10** Adjudication meeting 1: walk every disagreement on question 1; record the resolution *and the reason* per item in the disagreement log.
- [ ] **H11** Adjudication meeting 2: same for question 2 (and 3).
- [ ] **H12** (each) Post-adjudication memo: the 3 disagreement patterns you noticed and what handbook rule (if any) would have prevented each.
- [ ] **H13** Compile the disagreement log into draft error-taxonomy categories with [PI NAME].
- [ ] **H14** (each) Sanity re-read of 5 of your own earliest rows from H3 — did your standards drift? Report honestly.

## Phase I — Reviewer-role work *(stretch — in-scope-this-term pending [DEC-12]; gate: pipeline runs on the held-out set)*

- [ ] **I1** (each) Now read the tool chapters deferred from onboarding: the Automation Tool Roadmap (`ch-automation-roadmap-report.ptx`) and the demo chapter (`ch-pipeline-demo.ptx`), end to end. Log ≥ 5 feedback entries across the two.
- [ ] **I2** (each) Read the `sec-student-guide-pipeline` section (how the deterministic baseline actually runs); it predicts the shallow behavior you'll see in the tool's output, and is more accurate than the demo's polished chains.
- [ ] **I3** (each, optional) Read the Analytic Framework section of `ch-framing-models.ptx` — the formal version of the Episode Model you've been applying.
- [ ] **I4** (each) Guided tour of the review UI with [PI NAME] (screen-share; you drive).
- [ ] **I5** (each) Review the pipeline's output on 10 responses you personally coded: confirm / add / remove / replace / reject-all, with a rationale note each time.
- [ ] **I6** (each) Flag every pipeline decision that surprised you (right or wrong) — one line each.
- [ ] **I7** Joint memo: the 5 most common ways the pipeline's reading differed from yours.
- [ ] **I8** (each) UI feedback: 5 things that slowed you down in the review interface.

## Phase J — Ongoing habits *(every week, no gate)*

- [ ] **J1** (each) Weekly 5-bullet memo sent (done / time / confusions / next / blockers). *recurring*
- [ ] **J2** (each) Feedback log kept current — log at the moment of confusion, not from memory. *recurring*
- [ ] **J3** (each) Coding-time sittings recorded. *recurring*
- [ ] **J4** (each) Rules questions routed to [PI NAME], never to each other, during independent passes. *recurring*
- [ ] **J5** (each) No repo edits, no data leaves the shared folder, no responses pasted into AI tools. *recurring*
- [ ] **J6** Meeting notes: rotate who takes them; file in the shared folder within 24 h. *recurring*

## Phase X — [PI NAME]'s blockers *(students: this is what you may be waiting on)*

- [ ] **X1** Fill all [BRACKETED] placeholders in this packet; distribute. `due:___`
- [ ] **X2** Set up shared folder structure + share data subfolder. `due:___`
- [ ] **X3** Link/attach built HTML docs (or confirm GitHub-view reading) — [DEC-8]. `due:___`
- [ ] **X4** Select and distribute blind-pass batches ([DEC-2: batch size] responses each; batch design per [DEC-1: identical vs. disjoint]). `due:___`
- [ ] **X5** Review Part A submissions; issue Part B clearance. `due:___`
- [ ] **X6** Freeze codebook + vocabulary version for Phase H; record the version label — [DEC-6]. `due:___`
- [ ] **X7** Select held-out questions for Phase H (data inventory: which ULA short-answer questions have 30+ non-blank responses; must exclude the pivots calibration question) — [DEC-4: count + selection]. `due:___`
- [ ] **X8** Decide the nesting policy π with the group before Phase H coding is *analyzed* (coding can proceed under the record-everything rule) — [DEC-5]. `due:___`
- [ ] **X9** Compute agreement statistics after H9; prepare adjudication meeting materials. `due:___`
- [ ] **X10** Stand up pipeline runs on the held-out questions before Phase I. `due:___`
- [ ] **X11** Resolve the pending decisions in `06-decision-register.md` (DEC-1 – DEC-12) and update the packet's placeholders before distribution or as each decision lands. `due:___`
