# Drafting Queue — ScholarPath AdDU

Ordered by structural dependency: items 1–3 repair foundations that later chapters build on; items 4–8 add new prose. Compile after every item (`latexmk -pdf -interaction=nonstopmode main.tex`).

## Foundation Repairs (do before any new prose)
- [ ] **1. Reconstruct Table 2 — Synthesis of System Gaps and Design Responses** (`chapters/02_related_works.tex`, §2.9). Highest-value repair: the RRL's keystone artifact. Replace the flattened run-on paragraph with a 3-column `booktabs` table (Reviewed Work | Gap | ScholarPath Design Response). Content is recoverable from the legacy PDF text and §3.3.
- [ ] **2. Reconstruct Tables 1, 4, 5, 6, 7** in `01_introduction.tex` (Table 1: AdDU Financial Aid Programs), `04_theoretical_background.tex` (Table 4: anomalies; Table 5: paper-vs-Vault comparison; Table 6: conflict-resolution strategies; Table 7: EDA trigger mapping). Same method as item 1; add `\label{tab:...}`.
- [ ] **3. Curate `references.bib`.** For each of the 50 entries: correct entry type (`@article`/`@inproceedings`/`@book`/`@misc`+`url`), parse author name lists properly (remove the double-brace literal workaround), attach real DOIs/URLs, then delete the `needs-manual-curation` keyword. Verified by clean biber run.

## Structural Cleanup (before Chapters 5–6 are drafted)
- [ ] **4. Convert hardcoded cross-references to `\ref{}`.** Grep chapters for "Section 3.4", "Task 1", "Appendix B/C", "Figure", "Table" in prose; add `\label{sec:...}` where missing and rewire.
- [ ] **5. Add §3.4 edge-case evaluation protocol for RQ2** — a table of test profiles exercising the Exclusion Flag Hierarchy (concurrent government grants, clinical-program exclusions, boundary QPI/income, expired grants) with expected outputs. *Blocks Chapter 5.3.*
- [ ] **6. Add statistical procedure detail to §3.4.2** — name the paired test (state Wilcoxon signed-rank as the ordinal-safe option alongside the paired t-test), the significance level, and the reliability plan (Cronbach's α) for the Likert grids. *Blocks Chapter 5.2/5.5.*
- [ ] **7. Proofreading pass over migrated prose** — fix extraction blemishes ("Hierarchy .", "undergraduate -specific"), convert Problem Statement numbered items to `enumerate`, standardize "54 funding pipelines".

## New Prose (requires data or user approval)
- [ ] **8. Chapter 5 — Results and Discussion** (scaffold exists in `outline.md`). Draft 5.1 demographics → 5.4 RQ3 → 5.2 RQ1 (paired pre/post) → 5.3 RQ2 (edge-case outcomes) → 5.5 RQ4 (SUS benchmark vs. Bangor et al. curves) → 5.6 qualitative themes. *Blocked until testing executes; sections 5.2/5.5 can be drafted with placeholder tables once item 6 lands.*
- [ ] **9. Chapter 6 — Summary, Conclusions, and Recommendations.** Per-RQ conclusions mirroring §1.2; future work: registrar integration, weighted award-allocation support, PWA/native push evaluation. *Draft after Chapter 5.*
- [ ] **10. Abstract** (150–250 words: problem, platform, method, headline results, contribution). *Write last.*
- [ ] **11. Add `\listoftables` + `\listoffigures`** to front matter once items 1–2 exist.

## Immediate Top 3
1. **Table 2 reconstruction** (item 1) — unblocks the argument of the entire RRL.
2. **Bibliography curation** (item 3) — the only remaining build-level liability; required before any submission.
3. **§3.4 edge-case protocol** (item 5) — the prerequisite for RQ2, the study's central technical claim.
