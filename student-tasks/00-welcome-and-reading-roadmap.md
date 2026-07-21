# Reading Roadmap & Ground Rules

## What this project is

When students answer short-answer "explain why" questions, their written justifications contain evidence about how they decide they're done. In the Balacheff (cK¢) framework, we refer to these as **control structures**. Mapping control structures to student responses is called **coding**. When there are hundreds of students, this process is slow, subjective, and hard to reproduce.

The goal of this project is to develop a computational tool that assists (not replaces) this human coding. The tool ingests real student responses from a textbook, screens out blanks and non-answers, extracts each response's reasoning as small structured steps, matches those steps against a codebook of known control structures, and routes everything ambiguous to a human reviewer. Every decision the tool makes is stored with its rationale, so a human can audit or override any of it.

## Reading list

Read actively: keep the doc-feedback log open while you read. Estimated total: **4–6 hours**, split however your schedule allows.

| Document | Where | What to get out of it |
|----------|-------|----------------------|
| **Automation Tool Roadmap** | [??](https://github.com/geoff-cox/proteus-rs-pipeline) | The five pipeline stages and the four sample responses (R001–R004) traced through them. This is the accessible overview of the whole system. |
| **The Pipeline in Action** (demo chapter) | [??](https://github.com/geoff-cox/proteus-rs-pipeline) | Five *real* responses walked through every stage, table by table, ending at five different dispositions. The fastest way to *see* what each stage does. |
| **Glossary** | [??](https://github.com/geoff-cox/proteus-rs-pipeline) | Skim once; bookmark. Return to it whenever a term is unfamiliar. |
| **Coder's Handbook, Part I** | [??](https://github.com/geoff-cox/proteus-rs-pipeline) `01-coders-handbook.md` | The Episode Model — the actual rules you will code with. Read closely; this is your working manual. |
| **Analytic Framework** section (optional but encouraged) | [??](https://github.com/geoff-cox/proteus-rs-pipeline)`, section "Analytic Framework" | The formal version of what the handbook says in plain language. If the math notation is heavy going, that itself is doc feedback. |

## Ground rules for coding work

1. **Independence.** During any pass labeled "independent," do not discuss specific responses or your codes with the other coder. Comparing happens later, on purpose, in adjudication meetings — the disagreement between you two is one of the things we measure and publish.
2. **Questions about rules are always allowed.** If you're unsure how a *rule* applies (not what the other coder thinks), ask me. Answers get shared with both coders and logged, because every clarification is a candidate revision to the handbook.
3. **Record uncertainty instead of hiding it.** Every coding sheet has confidence and notes columns. A low-confidence code with a good note is more valuable than a silently forced high-confidence one.
4. **Verbatim means verbatim.** When a column asks for the student's words, copy-paste; do not paraphrase or fix spelling.
5. **Nothing is graded.** Student responses are anonymized research data. You are describing reasoning, not scoring students.

## The doc-feedback log

Use `templates/doc-feedback-log.csv` (a shared copy lives in the drive folder). Log anything that slowed you down: a term used before it's defined, a table you couldn't parse, a cross-reference that goes nowhere, a sentence you had to read three times, jargon missing from the glossary. One row per issue. Aim for *at least five entries per document* — if a document genuinely has fewer, say so in your weekly memo, but experience says fresh eyes always find more.

## Weekly memo

Every week, even a slow one, send five bullets: (1) what you did, (2) roughly how long it took, (3) what confused you, (4) what you'll do next, (5) anything you're blocked on. Two minutes to write; it keeps the project honest about where time actually goes, and "time spent coding" is literally one of our research measurements (RQ: efficiency).

## Your first deliverable

Exercise 1 (`03-exercise-1-pipeline-trace.md`): hand-trace three practice responses through the five pipeline stages, on paper/spreadsheet, imitating the demo chapter's tables. Details in that document. Target: complete before the next meeting on [DATE].
