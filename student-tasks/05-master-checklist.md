# PROTEUS Undergraduate RA — Master Checklist

Every item has an ID for delegation. Convention: check the box, and fill `@who` / `due` inline as [PI NAME] assigns. Items marked **(each)** are done separately by *both* students; unmarked items can be done by either/one as assigned. Phases must be done in order **within** a track, but tracks C–D can start as soon as their prerequisites clear. Items in Phase X are [PI NAME]'s blockers — students: if you're stalled, check whether an X item is the reason and say so in your memo.

---

## Phase B — Reading & Handbook feedback *(target: week 1; ~1.5–2 h each)*

- [ ] **B1** (each) Read `00-orientation.md` (the one-page orientation). `@___ due:___`
- [ ] **B2** (each) Read Coder's Handbook Part I closely — this is the one substantive read. Log anything ambiguous as you go; ambiguity in the *handbook* is the most urgent feedback there is. `@___ due:___`
- [ ] **B3** (each) Keep the Glossary open as a reference *while* you read (don't read it end to end); note any term whose definition you couldn't follow (feedback log). `@___ due:___`
- [ ] **B4** (each) Self-check: define criterion / inferential link / judgment in your own words; check against Handbook §2. `@___ due:___`
- [ ] **B5** (each) Self-check: explain to a rubber duck why (1,0) is a meaningful two-digit code (Handbook §6). `@___ due:___`
- [ ] **B6** (each) Self-check: state what makes an episode *incomplete* and what you do with one (Handbook §6, §8). `@___ due:___`
- [ ] **B7** (each) Submit your Handbook feedback + your 3 best questions for the meeting. `@___ due:___`

*(The tool chapters — roadmap, demo, and the pipeline-baseline section — are deliberately deferred to Phase I, where reviewing tool output makes them useful. Reading them now can nudge you toward coding the way the tool does, which independence needs you to avoid.)*

## Phase C — Exercise 1: episode warm-up *(target: before next meeting; ~1–1.5 h each)*

- [ ] **C1** (each) Decompose WARMUP-A–E into episodes in `templates/episode-coding-sheet.csv`, per `03-exercise-1-episode-warmup.md` (one row per episode; leave `code` and `codebook_version` blank). `@___ due:___`
- [ ] **C2** (each) For every complete episode assign (c¹, c²) with a one-line justification in `notes`; mark `relation` on the multi-episode response. `@___ due:___`
- [ ] **C3** (each) Write the 2–3 sentence "hardest response" note and list any unclear Handbook passages. `@___ due:___`
- [ ] **C4** (each) Submit Exercise 1 to [PI NAME]. `@___ due:___`
- [ ] **C5** Meeting: compare both students' episode codings; discuss every divergence to consensus or open-question status (especially WARMUP-B's relation and WARMUP-C's c²). `@___ due:___`
- [ ] **C6** Log any handbook rule clarified during C5 into the handbook change-log queue. `@___ due:___`

## Phase D — Exercise 2, Part A: blind pass *(gate: C4–C5 done; ~2–3 h each)*

- [ ] **D1** (each) Receive your batch assignment (see X4) and confirm the response count. `@___ due:___`
- [ ] **D2** (each) Copy `templates/blind-pass-sheet.csv` to `blindpass-<yourname>.csv`; add a `legend` tab. `@___ due:___`
- [ ] **D3** (each) Code responses 1–5: one row per episode; `own_words_rule` + invented `my_category` per row. `@___ due:___`
- [ ] **D4** (each) Code responses 6–10. `@___ due:___`
- [ ] **D5** (each) Code responses 11–15 (and 16–20 if assigned). `@___ due:___`
- [ ] **D6** (each) Reconcile your category legend: merge duplicate labels *of your own*, finalize one-line definitions, add use-counts. `@___ due:___`
- [ ] **D7** (each) Sweep for hygiene: every `confidence`=1 row has a note; every incomplete episode has `complete`=0; verbatim columns are actually verbatim. `@___ due:___`
- [ ] **D8** (each) Record total coding time (sittings, start/stop) in your memo. `@___ due:___`
- [ ] **D9** (each) Submit sheet + legend; **stop and wait for clearance.** `@___ due:___`
- [ ] **D10** (each) Write 3 sentences: the hardest response in your batch and why (goes in memo). `@___ due:___`

## Phase E — Exercise 2, Part B: reveal & recode *(gate: both D9s in + X5 clearance)*

- [ ] **E1** (each) Read the sealed companion (`02-codebook-companion-SEALED.md`), twice. `@___ due:___`
- [ ] **E2** (each) Read the codebook CSV (`[FILENAME]`), all ten entries, twice. `@___ due:___`
- [ ] **E3** (each) Read the now-unrestricted vocabulary-draft and codebook-CSV sections of `ch-technical-notes.ptx`; log feedback as usual. `@___ due:___`
- [ ] **E4** (each) Recode your Part A batch: fill `code` per companion §4 (single / ALT / NONE / squint). Do not alter Part A columns. `@___ due:___`
- [ ] **E5** (each) Write the comparison memo (½–1 page) per companion §4. `@___ due:___`
- [ ] **E6** (each) Submit updated sheet + memo. `@___ due:___`
- [ ] **E7** Debrief meeting: side-by-side comparison of both coders' sheets; catalog agreements, divergences, and all `NONE`s. `@___ due:___`
- [ ] **E8** From E7, draft the list of proposed codebook clarifications and candidate new codes for the group. `@___ due:___`
- [ ] **E9** Update Handbook to v0.2 with rules clarified in C6/E7; both students re-read the diff. `@___ due:___`

## Phase F — Vocabulary & codebook review prep *(gate: Phase E; feeds the group meeting)*

- [ ] **F1** (each) Written position (2–4 sentences) on merging `vars_gt_eqs` / `vars_gt_rows`, grounded in your batch. `@___ due:___`
- [ ] **F2** (each) Written position on merging `no_solution` / `system_inconsistent`. `@___ due:___`
- [ ] **F3** (each) Written position on folding `more_than_one_solution` into `infinite_solutions`. `@___ due:___`
- [ ] **F4** (each) List vocabulary terms you *needed* during recode that don't exist (with the response IDs that needed them). `@___ due:___`
- [ ] **F5** (each) List vocabulary terms you never used once. `@___ due:___`
- [ ] **F6** (each) Flag every paraphrase in your batch that the listed surface forms would *miss* (verbatim phrase + the term it should map to). `@___ due:___`
- [ ] **F7** Merge both students' F1–F6 into one review-prep document for the group meeting. `@___ due:___`
- [ ] **F8** (each) Note any response in your batch citing a theorem/proposition by number → feeds the open theorem-reference policy question. `@___ due:___`
- [ ] **F9** (each) Check your batch for any evidence of the currently-unattested codes (CS2 rightmost-column, CS8 parametric form, CS10 degrees of freedom); report presence/absence. `@___ due:___`
- [ ] **F10** Present F7 at the group vocabulary-review meeting; record decisions. `@___ due:___`

## Phase G — Pattern authoring for the codebook *(gate: F10 decisions recorded; spreadsheet work)*

- [ ] **G1** Confirm which vocabulary version the patterns are written against (post-F10). `@___ due:___`
- [ ] **G2** Split the seven unauthored codes between the two students (suggested: alternate). `@___ due:___`
- [ ] **G3** For each assigned code: harvest `example_response_ids` from the coded sets. `@___ due:___`
- [ ] **G4** For each assigned code: draft `surface_markers` from verbatim student phrases. `@___ due:___`
- [ ] **G5** For each assigned code: draft `patterns` in `premise=… AND conclusion=…` syntax; log any vocabulary gap instead of inventing terms. `@___ due:___`
- [ ] **G6** For each assigned code with zero attested examples: record "no surface evidence in [set]" explicitly. `@___ due:___`
- [ ] **G7** Swap: each student reviews the *other's* drafted rows and marks anything they'd match differently. `@___ due:___`
- [ ] **G8** Resolve swap comments; deliver the filled six-column codebook CSV to [PI NAME]. `@___ due:___`
- [ ] **G9** One-paragraph confidence note per code: how solid are these patterns and what would improve them? `@___ due:___`

## Phase H — Independent coding of the held-out set *(gate: X6 frozen codebook + X7 question selection; question count pending [DEC-4] — H5–H7 flex accordingly; this is the gold standard)*

- [ ] **H1** (each) Confirm in writing which handbook version and codebook version you are coding under (they are frozen for this phase). `@___ due:___`
- [ ] **H2** (each) Calibration pass: code a shared 5-response calibration set — a fresh set, distinct from the Exercise 1 warm-up; quick sync meeting to confirm the protocol is stable *before* the real batch. `@___ due:___`
- [ ] **H3** (each) Code held-out question 1, batch 1, fully independently, full episode + CS coding. `@___ due:___`
- [ ] **H4** (each) Code held-out question 1, batch 2. `@___ due:___`
- [ ] **H5** (each) Code held-out question 2, batch 1. `@___ due:___`
- [ ] **H6** (each) Code held-out question 2, batch 2. `@___ due:___`
- [ ] **H7** (each) Code held-out question 3 (if assigned). `@___ due:___`
- [ ] **H8** (each) Hygiene sweep (as D7) + total-time report per question. `@___ due:___`
- [ ] **H9** (each) Submit sheets; do not discuss until agreement stats are computed. `@___ due:___`
- [ ] **H10** Adjudication meeting 1: walk every disagreement on question 1; record the resolution *and the reason* per item in the disagreement log. `@___ due:___`
- [ ] **H11** Adjudication meeting 2: same for question 2 (and 3). `@___ due:___`
- [ ] **H12** (each) Post-adjudication memo: the 3 disagreement patterns you noticed and what handbook rule (if any) would have prevented each. `@___ due:___`
- [ ] **H13** Compile the disagreement log into draft error-taxonomy categories with [PI NAME]. `@___ due:___`
- [ ] **H14** (each) Sanity re-read of 5 of your own earliest rows from H3 — did your standards drift? Report honestly. `@___ due:___`

## Phase I — Reviewer-role work *(stretch — in-scope-this-term pending [DEC-12]; gate: pipeline runs on the held-out set)*

- [ ] **I1** (each) Now read the tool chapters deferred from onboarding: the Automation Tool Roadmap (`ch-automation-roadmap-report.ptx`) and the demo chapter (`ch-pipeline-demo.ptx`), end to end. Log ≥ 5 feedback entries across the two. `@___ due:___`
- [ ] **I2** (each) Read the `sec-student-guide-pipeline` section (how the deterministic baseline actually runs); it predicts the shallow behavior you'll see in the tool's output, and is more accurate than the demo's polished chains. `@___ due:___`
- [ ] **I3** (each, optional) Read the Analytic Framework section of `ch-framing-models.ptx` — the formal version of the Episode Model you've been applying. `@___ due:___`
- [ ] **I4** (each) Guided tour of the review UI with [PI NAME] (screen-share; you drive). `@___ due:___`
- [ ] **I5** (each) Review the pipeline's output on 10 responses you personally coded: confirm / add / remove / replace / reject-all, with a rationale note each time. `@___ due:___`
- [ ] **I6** (each) Flag every pipeline decision that surprised you (right or wrong) — one line each. `@___ due:___`
- [ ] **I7** Joint memo: the 5 most common ways the pipeline's reading differed from yours. `@___ due:___`
- [ ] **I8** (each) UI feedback: 5 things that slowed you down in the review interface. `@___ due:___`

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
