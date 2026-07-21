# PROTEUS Coder's Handbook — Part I: The Episode Model

**Version:** 0.1 — [DATE]. This handbook will be revised as we code; every rule change is recorded in the change log (Section 12). When a rule changes, the version number changes, and your coding sheets record which version you coded under.
**Scope:** Part I contains everything you need for Exercises 1 and 2. Part II (the **sealed** Codebook Companion, `02-codebook-companion-SEALED.md`) contains the project codebook and controlled vocabulary — do not open it until cleared.

---

## 1. What you are coding

Students in a linear-algebra course answered short "explain why" reading questions embedded in their online textbook. Example question context (the *pivots question*, our calibration set): the student is shown information about a linear system and asked whether it can have exactly one solution, and why.

A response might read:

> "There is a free variable so it is not possible to have a unique solution."

Your job is to describe the *justification structure* of responses like this one, using a small formal model — the **Episode Model** — that both humans and the pipeline use, so that human codes and machine codes are directly comparable.

## 2. The unit of coding: the episode

An **episode** is one complete move of justification. It has three parts, always in this order:

| Part | Symbol | Plain meaning | In the example above |
|------|--------|---------------|----------------------|
| **Criterion** | C | The feature of the situation the student *cites* — what they point at | "There is a free variable" |
| **Inferential link** | I | The (usually unstated) inference connecting the criterion to the verdict — the *because-so* glue | free variable ⇒ solution not unique |
| **Judgment** | J | The verdict the student *draws* | "not possible to have a unique solution" |

We write an episode as e = (C, I, J). A response is coded as a *sequence* of episodes: possibly zero (nothing codable), often one, sometimes several.

**The single most important sentence in this handbook:** an episode is a **visible trace of justification in the writing** — it is *not* a claim about what the student understands, believes, or "has in their head." We code what is on the page. Nothing more.

### A worked example (from the project's framing chapter)

Question 1.4.6A shows a matrix in reduced form for a consistent system and asks whether the solution is unique. A student writes:

> "we only have 2 pivot points, so one variable will be free"

- **C** = "two pivots [among three variables]" — the cited feature.
- **I** = "fewer pivots than variables means some variable is unconstrained" — the inference, *implied by "so."*
- **J** = "one variable will be free" — the verdict drawn.

One episode. Note the student never actually answers whether the solution is unique — the episode is complete and locally sound, but the response doesn't reach the question's goal. Those are two different facts, and we keep them separate (Section 6).

## 3. Operations vs. controls — what does NOT get coded

Student writing contains two kinds of move:

- An **operation** is *generative*: it builds or transforms an object. Row-reducing a matrix, solving for x, computing a count ("I counted 2 pivots"). Operations are **not coded** as episodes.
- A **control** is *evaluative*: it reads a feature of the current state and returns a verdict ("there's a free variable, so it's not unique"). Controls **are** what episodes record.

In the worked example above, *counting* the pivots is an operation (it produces the count); the episode sits *on top of* that count. If a response is *all* operations — pure computation with no verdict-drawing — there may be zero episodes in it (see the edge-case playbook, Section 8).

## 4. Finding episodes in real writing

Practical signals:

- **Connector words** usually mark the I-joint of an episode: *so, because, since, therefore, which means, that's why*. "C, so J" and "J because C" are the two most common shapes. (Note "J because C" states the judgment *first* — the order on the page is not the C-I-J order of the model.)
- **One episode per criterion→judgment move.** If a student cites two different features and draws a verdict from each, that's two episodes.
- **Bare assertions** ("there is a free variable," full stop, with no verdict drawn from it) are not complete episodes — record them, but as incomplete (Section 6).
- The **same sentence** can contain several episodes chained together (Section 7).

## 5. What goes in your coding sheet

Column spec for episode-level coding (template: `templates/episode-coding-sheet.csv`). One **row per episode**, so a response with two episodes gets two rows.

| Column | What to enter |
|--------|---------------|
| `response_id` | The ID supplied with the data — copy exactly. |
| `episode_n` | 1, 2, 3, … within this response, in the order the *judgments* appear. |
| `criterion_verbatim` | The student's words for C, copy-pasted. |
| `judgment_verbatim` | The student's words for J, copy-pasted. |
| `link_stated` | `explicit` (a connector word is present), `implicit` (the move is clearly made but no connector), or `absent` (no verdict follows the criterion → episode is *incomplete*). |
| `complete` | 1 if the episode has both a criterion and a judgment; 0 otherwise. |
| `c1` | Correctness digit 1 (Section 6). Leave blank for incomplete episodes. |
| `c2` | Correctness digit 2 (Section 6). Leave blank for incomplete episodes. |
| `relation` | Blank for a lone episode; `chained(k)` if this episode's criterion is episode k's judgment; `independent` if it stands apart from the others (Section 7). |
| `code` | The control-structure code — **only used after the blind pass; leave blank until then.** |
| `oov_note` | Any terminology that feels outside the course's standard way of talking about this topic — copy the term verbatim (Section 8). |
| `confidence` | 3 = confident; 2 = plausible but arguable; 1 = genuinely unsure. |
| `notes` | Anything a future reader of this row needs. Never leave a `confidence`=1 row without a note. |

## 6. The two-digit correctness code

**Complete** episodes (criterion + judgment both present) get a pair of digits, each 0 or 1:

- **Digit 1 (c¹): is the criterion true?** Judged against the actual mathematical state of the problem. If the student says "there is a free variable" and, in fact, there is — c¹ = 1. If the matrix has no free variable, c¹ = 0, *even if their logic afterward is impeccable.*
- **Digit 2 (c²): is the inference valid?** Does the criterion genuinely entail the judgment *for this question*? "Free variable (in a consistent system) ⇒ not a unique solution" is a valid entailment: c² = 1. "More variables than equations ⇒ infinitely many solutions" is **not** valid in general (the system could be inconsistent): c² = 0, even when the conclusion happens to be right.

Three rules that keep this honest:

1. **The digits are independent.** (1,0) is a common and important code: true criterion, broken inference. Grade the link on its own merits.
2. **Incomplete episodes are never scored.** No judgment, or no criterion → leave c¹/c² blank, set `complete` = 0. Forcing a score onto a fragment destroys information.
3. **(1,1) certifies the justification, not the answer.** A response can be all-(1,1) episodes and still fail to answer the question (see the worked example). Conversely, a fully correct *answer* can be propped up by an invalid link. We are grading local reasoning moves, and only those.

## 7. Multiple and nested episodes

Consider (sample response R003 from the roadmap report):

> "One and only one solution is not possible because there will be a free variable since there are more variables than rows."

Two episodes, **chained**:

- e₁: C = "more variables than rows" → J = "there will be a free variable"
- e₂: C = "there will be a free variable" → J = "one and only one solution is not possible"

e₂'s criterion *is* e₁'s judgment — that's what `relation = chained(1)` records on e₂'s row. Contrast this with a response that gives two *separate*, non-interacting justifications; those are `independent`.

**The v0.1 nesting rule — read carefully.** The research group has *not yet fixed* the policy (called π in the framework docs) that decides whether chained/nested episodes ultimately count as one unit or several. Until it does: **record every episode you can identify, mark the relation, and do not collapse or drop anything.** Your job in v0.1 is to preserve the structure; the collapsing decision will be applied later, uniformly, by policy. If you find yourself wanting to merge two episodes into one, that impulse goes in the `notes` column, not into the rows.

## 8. Edge-case playbook

| You see… | Do this |
|----------|---------|
| **Blank / whitespace only** | One row: `complete`=0, note "blank." No episode content. |
| **Bare answer, no justification** ("No." / "Not possible.") | One row: `judgment_verbatim` filled, no criterion, `complete`=0, note "bare answer." |
| **Restates the question** or "I don't know" | One row, `complete`=0, note what happened. |
| **Pure computation, no verdict** ("I row reduced and got x=2, y=3") | Operations only — but watch for a hidden episode: "…so yes, there is one solution" turns the computation's *result* into a criterion. If genuinely no verdict: `complete`=0, note "operations only." |
| **Hedged/conditional reasoning** ("It depends what is in the augmented matrix") | This *is* often a codable move — the student's criterion is that the given information underdetermines the answer. Code it as an episode if a criterion and judgment are identifiable; confidence 1–2 and a note are expected here. |
| **Unfamiliar or off-standard terminology** (e.g., invoking determinants, kernels, or other machinery outside how the course discusses this topic) | Code the episode structure normally; copy the term into `oov_note` verbatim. Do not translate the student's term into more standard language. |
| **Citation of a theorem by number** ("by Proposition 1.4.4") | The citation is the criterion. Record it verbatim; put the proposition reference in `oov_note`; do not chase down the proposition's content unless instructed. |
| **Correct answer, invalid link** | Ordinary case: code it, expect c¹ and/or c²=0 per Section 6. Resist the halo effect of a right answer. |
| **Two readings both feel defensible** | Code your primary reading; describe the alternative in `notes`; confidence ≤ 2. |
| **You want to ask the other coder** | Don't (during independent passes). Ask [PI NAME] if it's a rules question; otherwise note it and move on. |

## 9. Uncertainty is data

The pipeline records a confidence value with every automated decision, and so do you. Patterns in *where humans hesitate* are one of the paper's research questions (auditability). Low confidence + clear note = good coding. There is no prize for false certainty.

## 10. Pacing and hygiene

- Code in sittings of ≤ 45–60 minutes; fatigue shows up in the data.
- Do not revisit and silently revise earlier rows after your standards drift; if you realize your early rows were coded differently, tell [PI NAME] — recalibration passes are normal and we log them.
- Timestamp your sittings (start/stop) in your weekly memo; coding time is one of our measured quantities.

## 11. What Part II will add (once you're cleared)

The sealed companion introduces the project's codebook of named control structures (CS codes) and the controlled vocabulary of canonical propositions the pipeline writes its extractions in. After the blind pass, you will recode with those codes in the `code` column — and compare what you invented against what the codebook says.

## 12. Change log

| Version | Date | Change | Affected sheets |
|---------|------|--------|-----------------|
| 0.1 | [DATE] | Initial draft. Nesting policy π deliberately open: record-everything rule in force (Section 7). | — |
