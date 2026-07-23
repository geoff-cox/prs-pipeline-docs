# Exercise 1 — Episode Warm-Up

**Prerequisite:** Coder's Handbook, Part I, read closely.
**Time:** ~1–1.5 hours. **Due:** before the meeting on [DATE].
**Work independently** — each of you codes all five responses on your own; we compare at the meeting. Do **not** discuss the responses with each other beforehand.

## Goal

Practice the one skill everything else builds on: read a response, break it into **episodes** — criterion (C), inferential link (I), judgment (J) — and record each one consistently, including when a piece is missing and when you're unsure. No pipeline, no codebook, no tool. Just you and the reasoning.

## The setup (you need this to assign the two-digit code)

All five responses answer the same question: *"Can this system have exactly one solution? Why or why not?"* For **this** question, the correct analysis is:

> The system is **consistent** and has **more variables than equations**, so it has a **free variable**, and therefore it has **infinitely many solutions** — it does **not** have a unique solution.

Treat that as the true state of the mathematics when you judge the two correctness digits (Handbook §6): **c¹** = is the cited criterion true of that state? **c²** = does the criterion actually *entail* the judgment for this question? Remember the two digits are independent.

## The five responses (synthetic, written for this exercise)

> **WARMUP-A:** "There is a free variable, so the solution can't be unique."
>
> **WARMUP-B:** "There are more variables than equations, so there will be a free variable, so it's not unique."
>
> **WARMUP-C:** "There are more variables than equations, so there are infinitely many solutions."
>
> **WARMUP-D:** "There is a free variable in this system."
>
> **WARMUP-E:** "No."

## What to produce

Use `templates/episode-coding-sheet.csv` (grab a copy from the shared folder). **One row per episode**, so a response with two episodes gets two rows, and a response with none still gets one row recording that. Fill these columns; **leave `code` and `codebook_version` blank** (you don't have the codebook yet — that's deliberate):

`response_id` · `episode_n` · `criterion_verbatim` · `judgment_verbatim` · `link_stated` (explicit / implicit / absent) · `complete` (1/0) · `c1` · `c2` (blank for incomplete episodes) · `relation` (chained(k) / independent / blank) · `oov_note` · `confidence` (3/2/1) · `notes`.

A worked row for **WARMUP-A**, so the format is unambiguous:

| response_id | episode_n | criterion_verbatim | judgment_verbatim | link_stated | complete | c1 | c2 | relation | confidence | notes |
|---|---|---|---|---|---|---|---|---|---|---|
| WARMUP-A | 1 | there is a free variable | the solution can't be unique | explicit | 1 | 1 | 1 | *(blank)* | 3 | free var is true of this system; free var ⇒ not unique is a valid step for a consistent system |

## Things to watch for (don't peek until you've tried each one)

- **WARMUP-B** is more than one episode. Where does one end and the next begin, and how do you record that the second one's criterion is the first one's judgment? (Handbook §7.)
- **WARMUP-C** is the tricky one. Its conclusion is the *right answer for this system* — yet ask yourself whether the criterion *by itself* forces that conclusion, or whether a system with "more variables than equations" could have landed somewhere else. Let that decide c². Confidence 2 and a note is a perfectly good answer here; it's exactly the kind of case we'll talk through together.
- **WARMUP-D** states something but stops. Is it a complete episode? (Handbook §6, rule 2.)
- **WARMUP-E** — one row. What can and can't you fill in?

## Also submit

- Two or three sentences: which response was hardest to decide, and what *specifically* was ambiguous about it.
- Any passage in Handbook Part I that was unclear or that you had to reread — this is real feedback we use to fix the handbook.

## Done means

All five responses are represented in the sheet, every complete episode has a two-digit code with a one-line justification in `notes`, every incomplete one says why it's incomplete, and you could defend any row out loud for thirty seconds.
