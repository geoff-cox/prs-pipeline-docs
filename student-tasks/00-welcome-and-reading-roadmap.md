# Reading Roadmap & Ground Rules

## 1. What this project is

When students answer short-answer "explain why" questions in an online math textbook, their written justifications contain evidence about *how they decide they're done*. We call these **control structures**. Reading hundreds of responses and coding each one for the control structure it shows is slow, subjective, and hard to reproduce.

We are working on a pipeline that assists (not replaces) this human coding. It ingests real student responses from a textbook, screens out blanks and non-answers, extracts each response's reasoning as small structured steps, matches those steps against a codebook of known control structures, and routes everything ambiguous to a human reviewer. Every decision the pipeline makes is stored with its rationale, so a human can audit or override any of it.

**A tool like this is only publishable if we can show it agrees with careful human coders.** You are those coders. Your independent codes, your disagreements, your adjudicated final answers provide the gold standard the pipeline is measured against.

## 2. Your role, and what you will never need to do

You will read student responses, apply a coding framework to them, help refine the codebook and vocabulary the pipeline uses, and eventually review the pipeline's output. All of your work happens in **shared spreadsheets and short written memos**. You will never write, run, or edit code, and you will never edit files in the repository. The repository is read-only reference material for you.

You have one additional job that starts immediately: **you are the first outside readers of the project documentation.** Anywhere you get confused, that confusion is valuable data — log it (Section 6).

## 3. Where things live

- **The repository (read-only for you):** https://github.com/geoff-cox/proteus-rs-pipeline
  Documentation lives under `docs/source/sa/`. Files ending in `.ptx` are PreTeXt (an XML format); they are readable in the GitHub web view, but if a built HTML version is linked in the shared folder, prefer that — it renders the tables and math properly.
- **The shared drive folder:** [LINK] — contains this packet, your coding spreadsheets, the doc-feedback log, and the student response data.
- **Student data:** distributed by [PI NAME] through the shared folder only. It never goes in the repo, never in email attachments to anyone outside the group, and never into any AI chat tool.

## 4. Reading list — in this order

Read actively: keep the doc-feedback log open while you read. Estimated total: **4–6 hours**, split however your schedule allows.

| # | Document | Where | What to get out of it | Est. |
|---|----------|-------|----------------------|------|
| 1 | This document | packet | Ground rules, sequence | 15 min |
| 2 | **Automation Tool Roadmap** | `docs/source/sa/ch-automation-roadmap-report.ptx` | The five pipeline stages and the four sample responses (R001–R004) traced through them. This is the accessible overview of the whole system. | 60–90 min |
| 3 | **The Pipeline in Action** (demo chapter) | `docs/source/sa/ch-pipeline-demo.ptx` | Five *real* responses walked through every stage, table by table, ending at five different dispositions. The fastest way to *see* what each stage does. | 60–90 min |
| 4 | **Glossary** | `docs/source/sa/bookends/glossary.ptx` | Skim once; bookmark. Return to it whenever a term is unfamiliar. | 20 min |
| 5 | **Coder's Handbook, Part I** | packet: `01-coders-handbook.md` | The Episode Model — the actual rules you will code with. Read closely; this is your working manual. | 60 min |
| 6 | **Analytic Framework** section (optional but encouraged) | `docs/source/sa/ch-framing-models.ptx`, section "Analytic Framework" | The formal version of what the handbook says in plain language. If the math notation is heavy going, that itself is doc feedback. | 30–45 min |

### ⛔ Restricted until you are cleared (this matters)

Your first real coding exercise is a **blind pass**: you code responses *before* seeing the project's existing codebook, so that we can test whether the codebook's categories are ones fresh readers discover on their own. That test only works once. Until [PI NAME] explicitly clears you, do **not** read:

- `02-codebook-companion-SEALED.md` in this packet;
- the codebook CSV file(s) (`cbk2pivotquestionanalysis.csv` or similar);
- the "Controlled Vocabulary: First-Pass Draft" and "Codebook CSV" sections of `docs/source/sa/ch-technical-notes.ptx`.

You will inevitably see passing mentions of example criteria (like "there is a free variable") in the overview documents — that's fine and unavoidable. What we're protecting is the full list of codes and vocabulary terms. If you accidentally open a restricted document, don't panic; just tell [PI NAME] — honesty here is worth far more than pretending.

## 5. Ground rules for coding work

1. **Independence.** During any pass labeled "independent," do not discuss specific responses or your codes with the other coder. Comparing happens later, on purpose, in adjudication meetings — the disagreement between you two is one of the things we measure and publish.
2. **Questions about rules are always allowed.** If you're unsure how a *rule* applies (not what the other coder thinks), ask [PI NAME]. Answers get shared with both coders and logged, because every clarification is a candidate revision to the handbook.
3. **Record uncertainty instead of hiding it.** Every coding sheet has confidence and notes columns. A low-confidence code with a good note is more valuable than a silently forced high-confidence one.
4. **Verbatim means verbatim.** When a column asks for the student's words, copy-paste; do not paraphrase or fix spelling.
5. **Nothing is graded.** Student responses are anonymized research data. You are describing reasoning, not scoring students.

## 6. The doc-feedback log

Use `templates/doc-feedback-log.csv` (a shared copy lives in the drive folder). Log anything that slowed you down: a term used before it's defined, a table you couldn't parse, a cross-reference that goes nowhere, a sentence you had to read three times, jargon missing from the glossary. One row per issue. Aim for *at least five entries per document* — if a document genuinely has fewer, say so in your weekly memo, but experience says fresh eyes always find more.

## 7. Weekly memo

Every week, even a slow one, send [PI NAME] five bullets: (1) what you did, (2) roughly how long it took, (3) what confused you, (4) what you'll do next, (5) anything you're blocked on. Two minutes to write; it keeps the project honest about where time actually goes, and "time spent coding" is literally one of our research measurements (RQ: efficiency).

## 8. How to ask questions

Small/factual → [CHANNEL: email/Slack/Discord]. Conceptual or "I think the handbook is wrong about X" → put it in your weekly memo or bring it to the group meeting; those are exactly the discussions we want on record.

## 9. Your first deliverable

Exercise 1 (`03-exercise-1-pipeline-trace.md`): hand-trace three practice responses through the five pipeline stages, on paper/spreadsheet, imitating the demo chapter's tables. Details in that document. Target: complete before the next meeting on [DATE].
