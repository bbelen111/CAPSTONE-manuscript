# Audit Report — ScholarPath AdDU (Migration + Editorial Critique)

Audit date: 2026-04 (on migrated build, `main.pdf`, 58 pp., compiles clean with `latexmk -pdf`).

## 1. Migration Integrity (structural)
**Done well**
- All 4 chapters, 3 appendices, and all 33 numbered sections/subsections from the legacy PDF were recovered and split into modular files; none lost (verified against the legacy TOC).
- The matching-engine pseudocode was restored to its true line structure as Listing 1 (`lst:matching`).
- All 4 body figures (Figures 1–4) were extracted from the PDF as PNGs and re-attached with captions and labels; all four were later regenerated from the revised source diagrams (Figures 2.1, 3.1, 3.2, and 3.3), so no legacy raster exports remain.
- All ~130 numeric citation markers `[n]` were converted to `biblatex` keys (`refN`) with numbers preserved via `sorting=none`.
- Appendix A was fully reconstructed as a 54-row `longtable` with URLs repaired (the PDF reflow had split them).
- Build is clean: zero LaTeX errors, zero undefined references, zero missing glyphs.

**Migration artifacts to fix (tracked in `drafting_queue.md`)**
1. **Flattened tables.** Tables 1, 2, 4, 5, 6, 7 survive only as run-on prose inside paragraphs (a PDF-extraction loss). Table 2 (Synthesis of Gaps) is the most damaging — it is the RRL's argumentative keystone.
2. **Hardcoded cross-references.** Strings like "see Task 1, Section 3.4.1" and "detailed in Section 3.4.3" are literal text; they will silently rot when sections shift. Convert to `\ref{}`. *(Partially fixed: every figure and table reference now uses `\ref{}` — the legacy "Figure 1–4" / "Table 2, 5–8" strings were also displaying the wrong numbers because `report` numbers floats per chapter. Section, Task, and Appendix strings remain literal.)*
3. **Legacy numbering inconsistencies normalized away.** The source's TOC and body disagreed (body: "2.5 Rule-Based Matching…", "2.8 Policy…"; TOC: "2.5 Accessibility…", "2.7 Policy…"). LaTeX renumbering fixed the structure, but any prose that references the old numbers must be checked.
4. **Extraction blemishes.** Stray spaces before punctuation ("Exclusion Flag Hierarchy .", "college undergraduate -specific"); bibliography "Retrieved from" link-titles are mangled. A proofreading pass over the `.tex` sources is needed.
5. **Figure quality.** *(Resolved: Figures 2.1, 3.1, 3.2, and 3.3 are now the regenerated source diagrams with crisp text; no legacy raster exports remain.)* Figure 3.2 (end-to-end application process flow) is rendered at the largest size a letter page permits, so its smallest node labels print small; split it into two plates if larger type is required.

## 2. Content Strengths
- **§1.2 Problem Statement** is genuinely strong: three crisply enumerated problems, each traceable into RQ1–RQ4 and into instrument items (Appendix B/C sub-task mapping is explicit and impressive).
- **§3.3 System Architecture** is the manuscript's core contribution: each design decision is explicitly derived from a named gap in a named reviewed work (e.g., Exclusion Flag Hierarchy ← Bilog's conflict-resolution gap). This evidence-grounding pattern is consistent and defensible.
- **Chapter 4** does real theoretical work — every theory is operationalized ("in the DeLone & McLean model, X operationalizes dimension Y"), not name-dropped.
- **Ethics (§3.5)** and **Scope & Limitations (§1.5)** are unusually thorough for a capstone (8 explicit limitations, including the self-reported-QPI weakness and the no-award-allocation constraint).

## 3. Content Weaknesses & Gaps
1. **The entire empirical half is missing** (Chapters 5–6). The methodology is prospective ("will be administered"); no results, no SUS scores, no discussion. This is expected for Research 1 but is the manuscript's dominant gap.
2. **No instrument validity argument.** Appendix B/C items are well-designed and mapped to RQs, but there is no pilot test, no reliability analysis plan (e.g., Cronbach's α for the Likert grids), and no justification for the paired mean-comparison statistic (is a paired t-test appropriate for 5-point ordinal data? Consider Wilcoxon signed-rank).
3. **Sampling fragility.** n = 10–15 is defended only via Tullis & Stetson [42] (SUS-specific); the pre/post perception instruments have no such sample-size defense. State this limitation explicitly in 5.x when written.
4. **RQ2 "functional correctness" has no stated test protocol.** §1.2 promises edge-case evaluation of the Exclusion Flag Hierarchy, but Chapter 3 never defines the test-suite profiles or oracle. A table of edge-case profiles (concurrent grants, clinical-program exclusions, boundary QPI/income) must be added to §3.4 before testing.
5. **FitScore formula under-specified.** `margin_Income / 10000` assumes a fixed peso scale; the normalization is asserted, never justified, and income ceilings across pipelines differ in magnitude. One paragraph of justification (or normalization by the grant's own ceiling) is needed.
6. **Citation hygiene.** Several load-bearing claims rest on grey literature (Ateneo web pages, Atenews, World Bank report). Acceptable, but the mangled URLs in the auto-generated `references.bib` make them unverifiable — manual curation is mandatory before submission.
7. **Tone inconsistencies are minor** (future vs. present tense drift in Ch. 3; occasional marketing-adjacent phrasing such as "drastically reducing server load").

## 4. Consistency Checks (notation/citation)
- Citation numbering: text now renders `[n]` consistent with `refN` keys ✓
- "54 pipelines" vs "over 50 programs" — both used; standardize on 54 for the inventory, "over 50" only in loose prose ✓ acceptable
- Facet taxonomy names: consistent across §2.4, §3.3.2, §4.6, Appendix A ✓
- Table/figure numbering: LaTeX auto-numbers; Appendix A table renders as "Table A.1" ✓

## 5. Verdict
The manuscript is a **solid, well-architected draft of Chapters 1–4 plus instruments** with a clean modular LaTeX foundation. The critical path to a defensible Research 1 submission is: (1) repair the six flattened tables, (2) curate the bibliography, (3) define the RQ2 edge-case protocol in Chapter 3, then (4) execute testing and draft Chapters 5–6.
