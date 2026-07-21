# Exercise 1 — Trace Three Responses Through the Pipeline

**Prerequisites:** Reading-list items 1–4 (roadmap report, demo chapter, glossary skim).
**Time:** ~2–3 hours. **Deliverable due:** [DATE]. **Work independently** — each of you traces all three responses; we compare at the meeting.

## Goal

Prove to yourself (and show us) that you can predict what each pipeline stage *does to a response* — before you ever code real data. This also stress-tests the documentation: everywhere you get stuck, the docs failed, and that goes in the feedback log.

## The three practice responses

These are **synthetic practice items written for this exercise** (not real student data — real data comes later). Assume the same setup as the demo chapter's pivots question: a linear system where the correct analysis shows a free variable exists, so a unique solution is impossible.

> **P1:** "Since every column has a pivot there are no free variables, so the solution has to be unique."
>
> **P2:** "I solved it and got x = 2, y = 3, z = 1, so yes there is exactly one solution."
>
> **P3:** "The determinant isn't zero so it works out to one answer."

(Yes, P1's claim about the matrix is factually wrong for our assumed setup, and P2 leans on a computation. That's deliberate.)

## What to produce

For **each** response, imitating the demo chapter's tables, fill out:

1. **Stage 2 — Screening.** `INCLUDE` or `EXCLUDE`, a confidence (0–1), and a one-sentence rationale in the style of the demo's screening table (mention connectors and named criteria if present).
2. **Stage 3 — Extraction.** The reasoning steps as *premise → conclusion* rows. Use your own words for the propositions (you don't have the official vocabulary yet — that's expected). Flag any step whose key term feels outside how this course talks about the topic (`oov_flag = 1`).
3. **Stage 4 — Matching.** You don't have the codebook, so answer in prose: does this look like it should match *some* codebook entry cleanly, several, or none? One sentence why.
4. **Stage 5 — Disposition.** Predict which of the five terminal dispositions from the demo chapter this response lands in (`auto_accept`, `standard_review`, `terminology_flag`, `no_match`, or the excluded/`escalate` path), and why.
5. **Episode reading (Handbook Part I).** Separately from the pipeline tables: list the episode(s) as (C, I, J), mark complete/incomplete, chained/independent, and — for complete episodes — assign the two-digit code (c¹, c²) given our assumed setup. *Hint: at least one of these responses has a true-feeling inference resting on a false criterion, and at least one is mostly operation.*

Format: a small spreadsheet or a plain document with one section per response — whatever is fastest for you. Neatness doesn't matter; explicit reasoning does.

## Also submit

- Your doc-feedback log entries so far (aim: ≥ 5 per document read).
- Up to three questions you'd most like answered at the meeting.

## Done means

All three responses have all five parts filled in, every judgment has at least a one-sentence rationale, and you can defend any row out loud for thirty seconds.
