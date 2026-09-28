# Master Outline & Completion Tracker — ScholarPath AdDU

Status legend: `[Complete]` full prose, builds clean · `[Draft/Partial]` present but needs work · `[Missing]` not yet written · `[Pending-OPEN]` written as a configurable parameter pending an OPEN item (see `iso_revision_tracker.md`).

> **2026-09-28 — ISO audit revision applied to Chapters 1–4 and Appendices A–D.** The Smart Eligibility Checker, Exclusion Flag Hierarchy, FitScore, and 54-pipeline system scope are removed. The system is now framed as a Data-Feeding Committee Portal for the three internal tracks.

## Front Matter
- [x] Title page — retitled; wording pending adviser confirmation (L-5) `[Complete]`
- [ ] Abstract `[Missing]` — write last, after results
- [ ] List of Tables / List of Figures `[Missing]` — tables now exist; add `\listoftables`/`\listoffigures`

## Chapter 1 — Introduction (`chapters/01_introduction.tex`) `[Complete]`
- 1.1 Background of the Study `[Complete]` — Table 1 rebuilt as `tab:tracks` (Internal Scholarship Tracks); income/grant units `[Pending-OPEN-5]`
- 1.2 Problem Statement `[Complete]` — problems and RQ1–RQ4 as `enumerate`; RQ2 = lifecycle correctness + committee usefulness
- 1.3 Objectives of the Study `[Complete]` — `enumerate`
- 1.4 Significance of the Study `[Complete]`
- 1.5 Scope and Limitations `[Complete]` — separate Scope/Limitations lists; 9 limitations

## Chapter 2 — Review of Related Works (`chapters/02_related_works.tex`) `[Complete]`
- 2.1 Digital Transformation in Higher Education Administration `[Complete]`
- 2.2 Web-Based Scholarship Management Systems `[Complete]`
- 2.3 Automated Decision-Making versus Decision Support in Scholarship Selection `[Draft/Partial]` — needs team-supplied decision-support/human-oversight sources (L-6)
- 2.4 Search and Filtering Mechanisms for Committee Review `[Complete]`
  - 2.4.1 Policy Desynchronization in Manual Systems `[Complete]`
- 2.5 Eligibility Screening and Committee Workflows in Deployed Systems `[Complete]`
- 2.6 Accessibility and Remote Access in Web-Based Systems `[Complete]` — promoted from flattened text to a real section
- 2.7 Usability and User Experience in Educational Platforms `[Complete]`
- 2.8 Policy, Data Privacy, and Access Control `[Complete]`
- 2.9 Theoretical Framework (Figure 1) `[Draft/Partial]` — prose revised; **Figure 1 PNG must be redrawn**
- 2.10 Synthesis of RRL and Research Gaps `[Complete]` — Table 2 rebuilt as `tab:synthesis`

## Chapter 3 — Methodology (`chapters/03_methodology.tex`) `[Complete]`
- 3.1 Research Design `[Complete]`
- 3.2 SDLC (Figure 2) `[Complete]` — documents the audit-driven redesign as an Adaptation cycle
- 3.3 System Architecture and Algorithmic Logic `[Complete]`
  - 3.3.1 Scope: Internal Scholarship Tracks `[Complete]`
  - 3.3.2 Application Lifecycle Path and Two-Stage Submission `[Draft/Partial]` — **lifecycle figure is a text placeholder**; `tab:sop-alignment`, `tab:phases`
  - 3.3.3 Three-Layer Screening and Committee Governance `[Pending-OPEN-2/3/4/7]` — `tab:decision-boundary`, `tab:subcommittees`
  - 3.3.4 Conditional Revert Protocol `[Pending-OPEN-8]` — Listing `lst:lifecycle` (state machine)
  - 3.3.5 Scholar Movement, Track Realignment, and Slot Management `[Complete]` — `tab:movement`
  - 3.3.6 Committee Filtering and Backend Indexing Strategy `[Complete]`
  - 3.3.7 System Architecture and Cloud Infrastructure `[Draft/Partial]` — **Figure 4 PNG must be redrawn**
  - 3.3.8 RBAC and Data Privacy Compliance `[Complete]` — Table 3 rebuilt as `tab:rbac`
  - 3.3.9 Automated Notification Subsystem `[Complete]`
- 3.4 Testing & Evaluation Procedures `[Complete]`
  - 3.4.1 Step-by-Step Testing Procedure (Tasks 1–4, role-based) `[Complete]`
  - 3.4.2 Data Analysis and Statistical Tools `[Complete]` — Lifecycle Test Case Matrix `tab:lifecycle-tests` (TC-01…TC-16)
  - 3.4.3 Survey Instruments (Appendices B, C, D) `[Complete]`
- 3.5 Ethical Considerations `[Complete]` — minor-consent clause pending L-4

## Chapter 4 — Theoretical Background (`chapters/04_theoretical_background.tex`) `[Complete]`
- 4.1 Introduction · 4.2 Relational Database Theory (Table `tab:anomalies`) · 4.3 Centralized IS & Cloud · 4.4 Metadata-Driven Document Management (Table `tab:storage`) `[Complete]`
- 4.5 Rule-Based Screening and Human-in-the-Loop Decision Support (Table `tab:conflict`) `[Draft/Partial]` — needs L-6 sources
- 4.6 IFT and Committee Filtering · 4.7 EDA (Table `tab:eda`) · 4.8 RBAC · 4.9 Agile · 4.10 HCI & ISO/IEC 25010 (Table `tab:iso25010`) `[Complete]`

## References
- [x] `references.bib` — 52 entries (`ref51` SOP, `ref52` ISO audit report added 2026-09-28) `[Draft/Partial]` — all entries still `needs-manual-curation`

## Chapter 5 — Results and Discussion `[Missing]`
- 5.1 Participant Demographics `[Missing]`
- 5.2 RQ1: Perceived Time/Effort Reduction (paired pre/post) `[Missing]`
- 5.3 RQ2: (a) Lifecycle Test Case Matrix results; (b) Committee Portal usefulness (Appendix D) `[Missing]`
- 5.4 RQ3: Deadline and Correction Management `[Missing]`
- 5.5 RQ4: Usability (SUS + ISO/IEC 25010) `[Missing]`
- 5.6 Qualitative Findings `[Missing]`

## Chapter 6 — Summary, Conclusions, and Recommendations `[Missing]`
- 6.1 Summary · 6.2 Conclusions per RQ · 6.3 Recommendations & Future Work (e.g., integration with the entrance examination system, Academic Trajectory Path analytics) `[Missing]`

## Appendices
- Appendix A — Financial Aid Landscape at AdDU (Institutional Context) `[Complete]` — 54-row `longtable`, context only
- Appendix B — Pre-Study Student Problem Validation Survey `[Complete]` — revised; revert if already administered (L-3)
- Appendix C — Post-Prototype Perceived Effort Survey `[Complete]`
- Appendix D — Committee Portal Usefulness Survey `[Complete]` — new
