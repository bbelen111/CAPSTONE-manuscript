# Drafting Queue — ScholarPath AdDU

Ordered by structural dependency: items 1–3 repair foundations that later chapters build on; items 4–8 add new prose. Compile after every item (`latexmk -pdf -interaction=nonstopmode main.tex`).

> **Capstone 2 migration applied (status update).** Items 1, 2, and 7 below were completed while migrating the manuscript to the revised (Capstone 2) draft: Tables 1, 2, 4, 5, 6, 7 rebuilt as `booktabs` (plus the Table 3 RBAC matrix added); §1.1/§1.2 reframed to the three internal scholarship tracks; §2.6 added; §3.4.1 converted to `enumerate`; notification APIs updated to Iprogsms/Resend. Build verified clean. Figures 1–4 were regenerated from the revised source diagrams, and the Chapter 3 flow figure (Figure 3.2) is now the revised end-to-end application process flow.

> **Unified Admin Dashboard pass (status update).** The manuscript was aligned with the committee decision that all evaluator functions run in a single **Unified Admin Dashboard** (role-scoped by PostgreSQL RLS): legacy role names (OSA staff/administrators, Admissions administrators, Department Chairs/Coordinators) were replaced across Chapters 1–4 with the six Table 3.1 roles; the §1.2 RQ2 "Data-Feeding Committee Portal" was renamed to the Unified Admin Dashboard; a unification-rationale paragraph was added after the RBAC matrix (§3.3.3); a new Synthesis-of-Gaps row (Kayanja \cite{ref46}; Orgianus \cite{ref36}) was added to Table 2.1; and stale "pipelines" terminology was swept to "internal scholarship tracks." Migration artifacts resolved in the same pass: the duplicated §2.6 block was removed from the §2.5 paragraph, the stray "3.3.4" literal in §3.3.3 was deleted, the §3.3.2 `$O(n)$` fragment was restored, and the §1.5 "User Base Limitation" was corrected to include incoming Grade 12 applicants. Build verified clean (`latexmk -pdf -g`, 56 pp.).
> **Em-dash cleanup (status update).** A PDF audit found 159 em dashes across Chapters 1–4 and Appendices B–C; all were removed and recast as commas, colons, parentheses, or split sentences, with `\cite{}`/`\ref{}` keys and quotes preserved. Numeric ranges (`--`) were left intact. `pdftotext` now reports zero em dashes in `main.pdf`. The "no em dash" rule was propagated to `context/style_guide.md`, `AGENTS.md`, `CLAUDE.md`, and `.clinerules`. Build verified clean (`latexmk -pdf`).


> **Participant-revision pass (status update).** The evaluation was restructured to 11 participants in two separately reported groups (10 student participants on the applicant portal; 1 expert administrative evaluator, a head of the Office of Admission and Aid, on the Unified Admin Dashboard). Appendices D (Pre-Study Administrative Process Validation Survey) and E (Post-Prototype Administrative Evaluation Survey) were added and wired into `main.tex`; `references.bib` gained `ref51` (Davis, 1989). Citation keys were mapped by author identity, not the revision brief's numeric guesses: Tullis & Stetson is `ref42` and Bangor et al. is `ref13` (`ref22`/`ref23` are unrelated works). A note: RQ2 (§1.2) references a `Lifecycle Test Case Matrix`, but Chapter 3 still defines only the Smart Eligibility Checker test-case matrix, so the proposed "Evaluator Roles Not Covered by Usability Testing" limitation was omitted until such a matrix exists. Build verified clean (`latexmk -pdf -g`, 67 pp.).


## Foundation Repairs (do before any new prose)
- [x] **1. Reconstruct Table 2 — Synthesis of System Gaps and Design Responses** (`chapters/02_related_works.tex`, §2.10). Done: 3-column `booktabs` table (Reviewed Work | Gap | ScholarPath Design Response) with `\label{tab:synthesis}`.
- [x] **2. Reconstruct Tables 1, 4, 5, 6, 7** Done: Table 1 rebuilt (AdDU Internal Scholarship Selection Tracks); Tables 4–7 reconstructed as `booktabs` with labels `tab:anomalies`, `tab:vault`, `tab:conflict`, `tab:eda`; Table 3 (RBAC matrix) added; Table 8 retained.
- [ ] **3. Curate `references.bib`.** For each of the 50 entries: correct entry type (`@article`/`@inproceedings`/`@book`/`@misc`+`url`), parse author name lists properly (remove the double-brace literal workaround), attach real DOIs/URLs, then delete the `needs-manual-curation` keyword. Verified by clean biber run.

## Structural Cleanup (before Chapters 5–6 are drafted)
- [~] **4. Convert hardcoded cross-references to `\ref{}`.** *Partially done:* prose now uses `Figure~\ref{fig:...}` and `Table~\ref{tab:...}` (labels already existed; the legacy hardcoded numbers displayed incorrectly because `report` numbers floats per chapter). *Resolved (Unified Admin Dashboard pass):* the stray inline "3.3.4 Role-Based Access Control" heading label in §3.3.3 was removed. *Remaining:* the hardcoded `Section 2.3/2.4/2.5/3.1/3.4.1–3.4.3` strings (currently rendering correctly) and `Task 1`/`Appendix B/C` mentions.
- [ ] **5. Add §3.4 edge-case evaluation protocol for RQ2** — a table of test profiles exercising the Exclusion Flag Hierarchy (concurrent government grants, clinical-program exclusions, boundary QPI/income, expired grants) with expected outputs. *Blocks Chapter 5.3.*
- [ ] **6. Add statistical procedure detail to §3.4.2** — name the paired test (state Wilcoxon signed-rank as the ordinal-safe option alongside the paired t-test), the significance level, and the reliability plan (Cronbach's α) for the Likert grids. *Blocks Chapter 5.2/5.5.*
- [x] **7. Proofreading pass over migrated prose** — done: spacing blemishes fixed ("Hierarchy .", "undergraduate -specific"), Problem Statement/objectives/RQs as `enumerate`, count standardized to the three internal scholarship tracks.

## New Prose (requires data or user approval)
- [ ] **8. Chapter 5 — Results and Discussion** (scaffold exists in `outline.md`). Draft 5.1 demographics → 5.4 RQ3 → 5.2 RQ1 (paired pre/post) → 5.3 RQ2 (edge-case outcomes) → 5.5 RQ4 (SUS benchmark vs. Bangor et al. curves) → 5.6 qualitative themes. *Blocked until testing executes; sections 5.2/5.5 can be drafted with placeholder tables once item 6 lands.*
- [ ] **9. Chapter 6 — Summary, Conclusions, and Recommendations.** Per-RQ conclusions mirroring §1.2; future work: registrar integration, weighted award-allocation support, PWA/native push evaluation. *Draft after Chapter 5.*
- [ ] **10. Abstract** (150–250 words: problem, platform, method, headline results, contribution). *Write last.*
- [ ] **11. Add `\listoftables` + `\listoffigures`** to front matter once items 1–2 exist.

## Immediate Top 3
1. **Table 2 reconstruction** (item 1) — unblocks the argument of the entire RRL.
2. **Bibliography curation** (item 3) — the only remaining build-level liability; required before any submission.
3. **§3.4 edge-case protocol** (item 5) — the prerequisite for RQ2, the study's central technical claim.
