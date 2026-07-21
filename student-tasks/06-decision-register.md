# PROTEUS Packet — Decision Register (PI-facing; not for students)

Every choice deliberately left open in the packet, in one place. Each entry lists where the decision bites, the options, considerations surfaced in planning, and a **safe default** — the behavior the packet exhibits if the decision is still unresolved when you hit send. Nothing in Phases A–C depends on any of these, so the packet can go out with all twelve unresolved.

Legend: 🔴 must be resolved before the phase it gates · 🟡 resolve when convenient · 🟢 cosmetic/logistical.

---

### DEC-1 🔴 Blind-pass batch design: identical or disjoint batches?
- **Bites:** X4; Exercise 2; the value of the E7 debrief.
- **Options:** (a) both students code the *same* batch — yields a free early agreement measurement and a much richer debrief; (b) *disjoint* batches — doubles coverage of the response set but removes the agreement read.
- **Considerations:** (a) was the lean during planning; the pivots question has only 39 non-blank responses, so coverage isn't scarce.
- **Safe default:** identical batches.
- **Deadline:** before X4 (batch distribution). — *Resolved: ______*

### DEC-2 🟡 Blind-pass batch size
- **Bites:** X4; Exercise 2 header `[BATCH SIZE]`; D3–D5 chunking.
- **Options:** 15–20 was the planning estimate (~2–3 h of coding). Smaller if the students' A8 hours come back low.
- **Safe default:** 15.
- **Deadline:** before X4. — *Resolved: ______*

### DEC-3 🟡 Exercise 1 items: synthetic (as written) or real responses?
- **Bites:** `03-exercise-1-pipeline-trace.md` (P1–P3 are synthetic, labeled as such).
- **Considerations:** synthetic keeps data governance out of the first week and the three items were engineered to hit specific branches (false criterion + valid link; operations-heavy; OOV). Real responses are more authentic but require selecting equally instructive ones.
- **Safe default:** synthetic, as written (no edit needed).
- **Deadline:** before sending the packet only if you swap. — *Resolved: ______*

### DEC-4 🔴 Held-out questions: which ones, and how many?
- **Bites:** X7; Phase H (H5–H7 flex with the count); the RQ1 gold standard.
- **Considerations:** requires the data inventory (which ULA short-answer questions have 30+ non-blank responses); must exclude the pivots calibration question; should jointly cover the stratification targets (clean, bare-answer, multi-control, nested, OOV, right-answer-wrong-link).
- **Safe default:** none — this genuinely blocks Phase H, but nothing earlier.
- **Deadline:** before H1. — *Resolved: ______*

### DEC-5 🔴 Nesting policy π (parent-only / child-only / both)
- **Bites:** X8; analysis of Phase H output. Coding itself proceeds under the Handbook §7 record-everything rule, so this blocks *analysis*, not coding.
- **Considerations:** group-level decision per the framing chapter ("the group must fix π before producing a validation dataset"). The framing chapter's worked example illustrates parent-only.
- **Safe default:** record-everything continues; no analysis of nested cases until fixed.
- **Deadline:** before H10 (adjudication) at the latest. — *Resolved: ______*

### DEC-6 🔴 Codebook + vocabulary freeze label for Phase H
- **Bites:** X6; H1; the `codebook_version` / `handbook_version` columns of `episode-coding-sheet.csv`.
- **Considerations:** should incorporate the F10 vocabulary-review decisions and E8/E9 codebook clarifications; label it in the repo's `codebook_versions` convention (e.g., `codebook3-<month><year>`).
- **Safe default:** none — hard gate on Phase H.
- **Deadline:** before H1. — *Resolved: ______*

### DEC-7 🟡 ULA-primary confirmation from the research group
- **Bites:** the packet's framing throughout (welcome doc §1 names ULA).
- **Status:** email sent; approval expected. If the group surprises you, the packet's Phases A–E survive intact (the pivots calibration work stands regardless); Phases F–H would re-target.
- **Safe default:** proceed as written.
- **Deadline:** before Phase F. — *Resolved: ______*

### DEC-8 🟢 Reading surface: built HTML or GitHub view of the `.ptx` docs
- **Bites:** X3; welcome doc §3.
- **Considerations:** built HTML renders tables/math properly and materially improves the doc-feedback signal (students critique the real reading experience, not XML noise).
- **Safe default:** GitHub view (works today, degrades feedback quality somewhat).
- **Deadline:** with X1–X2. — *Resolved: ______*

### DEC-9 🟢 Meeting cadence + weekly-memo day
- **Bites:** A5, A7, J1, and every `[DATE]` placeholder.
- **Safe default:** none needed structurally, but the first meeting date must be in the email.
- **Deadline:** before sending the email. — *Resolved: ______*

### DEC-10 🟢 Communication channel
- **Bites:** A4; welcome doc §8; `[CHANNEL]`.
- **Safe default:** email.
- **Deadline:** before sending the email. — *Resolved: ______*

### DEC-11 🟡 Part B clearance: joint or individual?
- **Bites:** Phase E gate (currently "both D9s in + X5"); pacing coupling between the two students.
- **Options:** (a) joint (as written) — protects the debrief's symmetry; the faster student may idle briefly (point them at Phase B leftovers / feedback log); (b) individual — no idling, but the cleared student must not discuss Part B material until both are through, which is a discipline risk.
- **Safe default:** joint, as written.
- **Deadline:** before the first D9 lands. — *Resolved: ______*

### DEC-12 🟡 Is Phase I (reviewer-UI work) in scope this term?
- **Bites:** Phase I header; expectations-setting in the email (currently the email doesn't promise it).
- **Considerations:** depends on X10 (pipeline running on the held-out set) and remaining student hours after Phase H.
- **Safe default:** treated as stretch; decide after H11.
- **Deadline:** none. — *Resolved: ______*

---

**Placeholder index** (find-and-replace targets across the packet): `[PI NAME]`, `[DATE]`, `[LINK]`, `[CHANNEL]`, `[FILENAME]` (codebook CSV), `[BATCH SIZE]`, plus every `@___` / `due:___` slot in the checklist.
