# Literature Verification — Mechanical `[verify]` Batch + He & Cui Review, 2026-07-17

Companion to `paper1-litverify-2026-07-17.md` (Helminen/Hwangbo full-text reads)
and `paper1-sweep-log-2026-07-17.md`. Apply these corrections during the
references-consolidation pass.

---

## 1 · He & Cui (2025) — resolved from full text (PDF on file)

**Citation (replaces the `[verify authors]` placeholder `bib-log-review-2025`):**
He, S., & Cui, Y. (2025). A systematic review of the use of log-based process
data in computer-based assessments. *Computers & Education, 228*, 105245.
https://doi.org/10.1016/j.compedu.2025.105245 (open access, CC BY)

**Matrix row updates (Section C):** PRISMA; 6,093 identified → 2,548 screened
→ 466 full-text → 330 included; searches Nov 2022 + Mar 2024, coverage through
2023-12-31; WoS, ProQuest Education, Scopus, EBSCO (incl. ERIC); single
reviewer; scope restricted to mouse clicks, keystrokes, and timing data.
Indicators categorized as time (in 82% of studies), count (32%), sequence
(25%); four inference levels adapted from Bergner & von Davier.

**Findings that strengthen Paper 1 (quote-check at drafting time):**
1. The review **explicitly declines to cover low-level feature construction**
   because it is "highly platform-specific" and generalizes poorly — and names
   as its own limitation that it "did not provide a detailed summary of
   pre-processing procedures," calling them "important topics" for future work.
   The field's systematic review thus certifies Paper 1's preprocessing
   territory as un-summarized.
2. Future recommendation #4: "very few studies have discussed how the results
   of log-based process data have been validated." Their inventory of proposed
   validation approaches — ECD theory-driven formulation, multimodal
   triangulation (eye-tracking/think-aloud/self-report), construct
   association, experimental designs — **contains no comparison of derived
   data against independently recorded platform records.** Check-anchor
   validation is absent from the surveyed repertoire.
3. Level-3/level-5 uses (holistic and measurement-model treatment of process)
   are "largely overlooked" per their Bergner-framework analysis — consistent
   with Paper 1's substrate framing.
4. Drag-and-drop presence in the review runs through Arslan et al. (2020) and
   Gong et al. (2022) — both already in the matrix; no missed close comparator
   visible in the main text.

**Remaining action:** scan the included-study spreadsheet (public OSF link in
the article, osf.io/tk46w) for any drag-and-drop/sorting rows beyond
Arslan/Gong/Jiang. This piggybacks their PRISMA pass and, once done, licenses
the "systematic search" claim by extension.

---

## 2 · Resolved citations (paste-ready facts)

| xml:id / matrix entry | Resolved citation | Flag closed |
|---|---|---|
| `bib-log-review-2025` | He, S., & Cui, Y. (2025). *C&E, 228*, 105245 | `[verify authors]` |
| `bib-anghel-2024` | Anghel, E., Khorramdel, L., & von Davier, M. (2024). *LSAE, 12*, Article 13. doi:10.1186/s40536-024-00202-1 | `[verify article number]` |
| `bib-bergner-vondavier-2019` | *JEBS, 44*(6), 706–732 | `[verify pages]` |
| `bib-chen-2019` | Chen, Y., Li, X., Liu, J., & Ying, Z. (2019). Statistical analysis of complex problem-solving process data: An event history analysis approach. *Frontiers in Psychology, 10*, Article 486. doi:10.3389/fpsyg.2019.00486 | `[verify title and venue]` |
| `bib-ponce-2021` | *J. Educational Computing Research, 59*(4), 713–739 | `[verify volume/pages]` |
| `bib-smith-2013` | Smith, J. I., Combs, E. D., Nagami, P. H., Alto, V. M., Goh, H. G., Gourdet, M. A. A., Hough, C. M., Nickell, A. E., Peer, A. G., Coley, J. D., & Tanner, K. D. (2013). *CBE—LSE, 12*(4), 628–644 | `[verify trailing authors]` |
| `bib-tpl-kats` | **Harper, M. E., Jentsch, F. G., Berry, D., Lau, H. C., Bowers, C. A., & Salas, E. (2003).** TPL—KATS-card sort: A tool for assessing structural knowledge. *Behavior Research Methods, Instruments, & Computers, 35*(4), 577–584. doi:10.3758/BF03195536 | `[verify authors and year]` |
| `bib-arslan-emip` | Arslan, B., Jiang, Y., Keehner, M., Gong, T., Katz, I. R., & Yan, F. (2020). The effect of drag-and-drop item features on test-taker performance and response strategies. *EM:IP, 39*(2), 96–106. doi:10.1111/emip.12326 | `[verify full citation]` |
| `bib-ericson-2018` | ICER '18 (Espoo), pp. 60–68. ACM. doi:10.1145/3230977.3231000 | `[verify pages]` |
| `bib-helminen-2012` | *(previous session)* ICER '12, pp. 119–126. ACM. doi:10.1145/2361276.2361300 — **not Koli Calling** | `[verify pages]` + venue error |
| `bib-hwangbo-2026` | *(previous session)* Hwangbo, Park, Jeon, & Jin (2026). arXiv:2604.16900 | `[verify authors]` |
| Matrix: "Investigating the Affect and Effect of Adaptive Parsons Problems" | **Ericson & McCall, ICER 2024** | `[verify venue/year]` (pages pending, §3) |
| Matrix: Kovanović et al. (2015) | Cite the **journal version**: Kovanović, V., Gašević, D., Dawson, S., Joksimović, S., Baker, R. S., & Hatala, M. (2015). Does time-on-task estimation matter? Implications for the validity of learning analytics findings. *Journal of Learning Analytics, 2*(3), 81–110. doi:10.18608/jla.2015.23.6 | venue confirmed |
| Matrix: Ericson & Miller (2020) SIGCSE | pp. 1012–1018 (from sweep results) | `[verify pages]` |
| Matrix: Du, Luxton-Reilly, & Denny (2020) | ACE '20, pp. 195–202 (from sweep results) | new-candidate details |

### Traps caught in this batch (worth a note in the verification log)
1. **TPL-KATS authorship**: the card-sort paper at doi BF03195536 is
   **Harper et al. (2003)** in *BRMIC*; **Hoeft et al. (2003)** is the
   *concept-map* sibling in *Computers in Human Behavior* 19, 653–657. Citing
   "Hoeft et al." for the card sort — as several secondary sources do — would
   be wrong.
2. **Kovanović dual versions**: the LAK '15 conference paper shows
   conflicting page numbers across sources (64–68 on the author's site,
   184–193 in a JLA reference list). The extended *JLA* 2(3) journal version
   sidesteps the conflict and is the stronger citation for the RQ4 argument
   (bigger dataset, more scenarios).
3. **Helminen venue** *(prior session)*: ICER '12, not Koli Calling — the
   same group's *mobile Parsons app* paper is the Koli Calling 2012 one.

---

## 3 · Remaining one-click items (need library/DL access — user)

- [ ] **CEP 2026** (doi 10.1016/j.cedpsych… S0361476X26000196): author list —
  ScienceDirect blocks automated access; visible on the article page.
- [ ] **He & von Davier (2016)** chapter pages: secondary sources split
  between 749–776 and 750–777; majority usage is **749–776** — confirm once
  against the IGI Global chapter page and adopt.
- [ ] **Ericson & McCall (2024)**, ICER '24: first name + pages + DOI (one
  ACM DL click).
- [ ] **He & Cui OSF spreadsheet scan** for missed D&D/sorting comparators
  (see §1).
- [ ] Sweep candidates if adopted: arXiv:2403.14908 author list; Sizemore et
  al. venue/year; Ericson SPLICE 2021 pages.

---

## 4 · Verification checklist — state after this batch

- [x] 2026 arXiv tutorial read + row replaced (2026-07-17)
- [x] Helminen et al. (2012) full text read + row replaced + citation
  corrected (2026-07-17)
- [x] He & Cui (2025) full text read + citation resolved + gap-relevant
  findings extracted (2026-07-17)
- [x] 2024–2026 comparator sweep (documented in the sweep log; no gap threat)
- [x] Mechanical `[verify]` batch — **14 of 18 items resolved**; 4 one-clicks
  remain (§3)
- [ ] OSF included-study scan (§1)
- [ ] Formal Scopus/WoS queries **or** soften "systematic search" wording
- [ ] References consolidation into `references.ptx` — now unblocked for all
  resolved entries; do after the §3 one-clicks land
