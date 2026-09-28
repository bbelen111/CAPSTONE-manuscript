# Drafting Queue — ScholarPath AdDU

Compile after every item (`latexmk -pdf -interaction=nonstopmode main.tex`).

> **2026-09-28 — ISO audit revision applied** (user-authorized ahead of the foundation items). It absorbed the former items 1 (Table 2), 2 (Tables 1, 4–8), 5 (RQ2 test protocol, now the Lifecycle Test Case Matrix) and most of 7 (structural proofreading of Ch1–4 and the appendices). Details are in `iso_revision_tracker.md`.

## Before the code freeze (Oct 10, 2026)
- [ ] **1. Resolve OPEN-1 … OPEN-10 with the University Scholarship Office.** For each answer, replace the configurable wording with the confirmed rule, delete the `% TODO(OPEN-n)` comment, and mark it resolved in `iso_revision_tracker.md`. Find the markers with `grep -rn "TODO(OPEN-" chapters/`.
- [ ] **2. Resolve local items L-1 … L-6** (Scholarship Office vs. OSA, Form 230-SCH, Appendix B administration status, minor consent, title wording, decision-support sources).
- [ ] **3. Draw the figures** (PNG to `figures/`): the new `figure_lifecycle.png` replaces the placeholder in §3.3.2, and `figure4_architecture.png` and `figure1_issm.png` must be redrawn. Specs are in `iso_revision_tracker.md`.
- [ ] **4. Add decision-support / human-oversight sources** (L-6) as `ref53`+ and cite them in §2.3 and §4.5.

## Foundation (carried over)
- [ ] **5. Curate `references.bib`** (now 52 entries): correct entry types, parse author lists, attach DOIs/URLs, then remove `needs-manual-curation`. `ref51`/`ref52` are internal documents; confirm the SOP's year and issuing office.
- [ ] **6. Add statistical procedure detail to §3.4.2**: name the paired test (Wilcoxon signed-rank as the ordinal-safe option alongside the paired t-test), the significance level, and the reliability plan (Cronbach's α) for the Likert grids. *Blocks Chapter 5.2/5.5.*
- [ ] **7. Remaining proofreading**: bibliography "Retrieved from" titles; the three cosmetic overfull lines (Ch1 scope list, Ch3 indexing list).
- [ ] **8. Add `\listoftables` + `\listoffigures`** to front matter (tables now exist).

## New Prose (requires data)
- [ ] **9. Chapter 5 — Results and Discussion.** 5.1 demographics → 5.4 RQ3 → 5.2 RQ1 (paired pre/post) → 5.3 RQ2 (a: Lifecycle Test Case Matrix pass rates, with the human-confirmation cases reported separately; b: Appendix D means) → 5.5 RQ4 (SUS vs. Bangor et al.) → 5.6 qualitative themes. *Blocked until testing executes.*
- [ ] **10. Chapter 6 — Summary, Conclusions, and Recommendations.** Per-RQ conclusions; future work such as entrance-exam system integration and Academic Trajectory Path analytics. (Weighted award allocation is no longer future work: no algorithm selects scholars.)
- [ ] **11. Abstract** (150–250 words). *Write last.*

## Immediate Top 3
1. **OPEN items with the Scholarship Office** (item 1): the manuscript cannot be finalized for the audit without them.
2. **Figures** (item 3): the lifecycle figure is required by the report's action plan.
3. **Bibliography curation** (item 5): required before submission.
