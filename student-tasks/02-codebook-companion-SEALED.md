# PROTEUS Coder's Handbook — Part II: Codebook Companion

# ⛔ SEALED — do not read until [PI NAME] clears you

Opening this document before completing the blind pass (Exercise 2, Part A) invalidates a one-time measurement the project needs. If you're reading this sentence and haven't been cleared: close the file, tell [PI NAME] you got this far, and no harm done.

---

**Version:** 0.1 — [DATE] · Companion to Handbook Part I; same change-log discipline applies.

## 1. What this document adds

Part I taught you to find and score episodes without naming them. This companion introduces the two naming layers the pipeline uses:

1. The **codebook** — ten named control structures, `CS1`–`CS10`, each describing a *kind of criterion-to-judgment move* students make on this topic. Matching an episode to a CS code is the central interpretive act of the whole project.
2. The **controlled vocabulary** — a fixed list of canonical propositions (short machine-readable names like `free_var_exists`) that the pipeline's extraction stage writes student reasoning in, so that paraphrases ("infinite solutions," "infinitely many solutions," "not unique") collapse to one matchable form.

Roughly: vocabulary terms are the *nouns* reasoning steps are written in; codebook entries are the *named moves* built out of them.

## 2. The codebook of record

The authoritative artifact is the group's codebook CSV (**attached in the shared folder as [FILENAME]** — currently `cbk2pivotquestionanalysis.csv`), which defines `CS1`–`CS10` with a name and description each. Read it now, twice: once straight through, once against your own blind-pass categories.

Three entries have been worked up to the full six-column format the pipeline will eventually consume. They're reproduced here because they are also the best teaching examples of what a mature codebook entry looks like:

### CS7 — Free variables
- **Description:** Uses the presence or absence of a free variable to classify the solution set of a consistent system.
- **Surface markers** (phrases that signal it in student writing): *free variable; free variables; at least one free variable; no free variables*
- **Patterns** (machine rules over vocabulary terms): `premise=free_var_exists AND conclusion=no_unique_solution | premise=free_var_exists AND conclusion=infinite_solutions`

### CS6 — Pivot structures for solution set
- **Description:** Uses the existence or count of pivots to justify the cardinality of the solution set.
- **Surface markers:** *at most n pivots; maximum number of pivots; pivot in every column; pivot per variable; need 5 pivots; only 4 pivot positions*
- **Patterns:** `premise=pivots_lt_vars AND conclusion=no_unique_solution | premise=pivot_in_every_col AND conclusion=unique_solution`

### CS9 — Relating two countable features
- **Description:** Compares two countable components of the system (variables vs. equations, variables vs. rows) to draw a conclusion.
- **Surface markers:** *more variables than equations; more variables than rows*
- **Patterns:** `premise=vars_gt_eqs AND conclusion=infinite_solutions | premise=vars_gt_eqs AND conclusion=free_var_exists | premise=vars_gt_rows AND conclusion=free_var_exists`

The remaining seven codes have only `code_id` / `name` / `description` — filling in their surface markers, patterns, and example responses is one of *your* upcoming tasks (Section 6).

## 3. The controlled vocabulary (draft v0.1 — 17 terms)

Drafted against the pivots-question response set (46 responses, 39 non-blank); every attested term is backed by at least one real response. Full rationale lives in the "Controlled Vocabulary: First-Pass Draft" section of `docs/source/sa/ch-technical-notes.ptx` (now unrestricted for you).

| Canonical form | Meaning |
|----------------|---------|
| `vars_gt_eqs` | More variables than equations. |
| `vars_gt_rows` | More columns (variables) than rows in the matrix. |
| `pivots_lt_vars` | Fewer pivots than variables. |
| `pivot_in_every_col` | Every column has a pivot (every variable is a pivot variable). |
| `eqs_eq_vars` | Number of equations equals number of variables. |
| `free_var_exists` | At least one free variable in the (consistent) RREF. |
| `inconsistent_row_exists` | RREF contains a row [0 0 … 0 \| c], c ≠ 0. |
| `pivot_in_rightmost_col` | The augmented column contains a pivot. *(not attested in the pivots question; kept for CS2 coverage)* |
| `zero_row_exists` | RREF contains an all-zero coefficient row. *(not attested; kept for CS4 coverage)* |
| `unique_solution` | Exactly one solution. |
| `no_unique_solution` | *Not* exactly one solution — rules out the unique case without committing further. |
| `infinite_solutions` | Infinitely many solutions. |
| `no_solution` | No solution. |
| `system_consistent` | At least one solution. |
| `system_inconsistent` | No solution, stated in consistency vocabulary. |
| `more_than_one_solution` | More than one solution, without committing to infinitude. |
| `solution_depends_on_b` | Answer underdetermined by the coefficient matrix; depends on the augmented column. |

The vocabulary is **descriptive of student writing, not a correctness rubric** — some entailments students assert between these propositions are only valid under extra assumptions, and that's exactly what digit c² catches.

## 4. Recoding with the codebook (Exercise 2, Part B)

Return to your blind-pass batch. For each episode row, now fill the `code` column:

- Exactly one CS code fits → enter it.
- Two or more genuinely fit → enter the best fit, list the runner(s)-up in `notes` prefixed `ALT:`, confidence ≤ 2.
- Nothing fits → enter `NONE`, and describe in `notes` what kind of move it is. **`NONE` entries are treasure** — they are candidate new codes or evidence of codebook gaps.
- The episode fits a code only if you squint → enter the code with confidence 1 and say what the squint was.

Then write the **comparison memo** (½–1 page): Which of your invented blind-pass categories map cleanly onto CS codes? Which CS codes did you converge on without knowing they existed? Which codes never appeared in your batch? What did you find that the codebook has no home for? This memo goes to [PI NAME] before the reveal-debrief meeting.

## 5. Preparing for the vocabulary review (group discussion prep)

The vocabulary draft flags open questions for the group. Come to the review meeting with a written position (a few sentences each) on the proposed **merge candidates**:

1. Merge `vars_gt_eqs` and `vars_gt_rows` into one term? (Cost: loses whether the student thought in equations or matrix rows. Benefit: one fewer near-duplicate.)
2. Merge `no_solution` and `system_inconsistent`? (Logically equivalent; kept apart because some students explicitly use consistency vocabulary.)
3. Fold `more_than_one_solution` into `infinite_solutions`? (The weaker claim is occasionally what students actually commit to — is that distinction worth a term?)

Ground every position in responses you actually coded — "in my batch, N students said X" beats intuition. Also flag any term you *needed* during recoding that doesn't exist, and any listed term you never once used.

## 6. Pattern authoring (your highest-leverage tool contribution)

Seven codebook entries have no surface markers or patterns yet. Authoring them is spreadsheet work with real downstream impact: the pipeline's matching stage runs on these rules.

**Pattern syntax primer.** A pattern is a rule over vocabulary terms: `premise=<term> AND conclusion=<term>`. Multiple alternative rules for one code are separated by `|` (each becomes its own matching rule). Surface markers are semicolon-separated short phrases lifted from *actual student writing*.

**Procedure per code:**
1. Read the code's description in the codebook CSV.
2. Search the coded response sets (your batches + the calibration set) for episodes matching that description; collect their `response_id`s → these become `example_response_ids`.
3. Harvest the phrases students actually used → `surface_markers` (verbatim fragments, semicolon-separated).
4. Express the criterion→judgment shape in vocabulary terms → `patterns`. If the needed term doesn't exist in the vocabulary, **do not invent one silently** — log it as a vocabulary-gap proposal for the review meeting.
5. If you find *zero* attested examples for a code, that's a finding, not a failure: record "no surface evidence in [batch]" — the group tracks which codes are unattested and why (it has already noticed this for CS2, CS8, and CS10 on the pivots question).

Deliverable: the six-column codebook CSV with your drafted rows, plus a short note per code on how confident the patterns are.
