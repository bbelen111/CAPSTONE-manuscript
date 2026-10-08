# Master Outline & Completion Tracker — ScholarPath AdDU

Status legend: `[Complete]` full prose in legacy draft, migrated · `[Draft/Partial]` present but structurally broken or thin · `[Missing]` not yet written.

**Revision log (Capstone 2 migration).** Chapters 1–4 and Appendices A–C were migrated to the revised manuscript: committee decision-support framing, three internal scholarship tracks (Jubilee, Grant-in-Aid, Working Scholars), Iprogsms/Resend notification APIs, new Research Questions and objectives (§1.2–1.3), a rebuilt Table 1 (selection tracks), the reconstructed Table 2 (RRL keystone), the RBAC matrix (Table 3), the Smart Eligibility Checker test-case matrix (§3.4.2), and reconstructed `booktabs` tables 4–8. Build verified clean (`latexmk -pdf`, 58 pp.). Figures 1–4 were subsequently regenerated from the revised source diagrams; the legacy Chapter 3 eligibility-logic raster was retired in favor of the revised end-to-end application process flow, which now occupies the Chapter 3 flow-figure slot (Figure 3.2). Prose cross-references to floats were also rewired from the legacy hardcoded numbers to `\ref{}`, since `report` numbers figures and tables per chapter (Figures 2.1, 3.1–3.3; Tables 1.1, 2.1, 3.1, 4.1–4.5).

**Revision log (Unified Admin Dashboard pass).** The manuscript was brought into line with the committee decision that all evaluator functions run in a single **Unified Admin Dashboard** (roles scoped by PostgreSQL Row Level Security), matching Figures 3.2–3.3 and Table 3.1, which were already unified. Legacy role names (OSA staff/administrators, Admissions administrators, Department Chairs/Coordinators) were replaced throughout Chapters 1–4 with the six Table-3.1 roles; the §1.2 RQ2 "Data-Feeding Committee Portal" was renamed to the Unified Admin Dashboard for single-interface naming; a new rationale paragraph was inserted after the RBAC matrix in §3.3.3; a Synthesis-of-Gaps row (Kayanja \cite{ref46}; Orgianus \cite{ref36}) was added to Table~2.1; and the stale "pipelines" terminology was swept to "internal scholarship tracks." Migration artifacts were also repaired: the duplicated §2.6 block was removed from the §2.5 paragraph, the stray "3.3.4" literal in §3.3.3 was deleted, and the §3.3.2 "$O(n)$" fragment was restored. Build verified clean (`latexmk -pdf -g`, 56 pp.).
**Revision log (Em-dash cleanup).** All 159 em dashes (`---`) were removed from the Chapters 1–4 prose and Appendices B–C and recast as commas, colons, parentheses, or split sentences, preserving every `\cite{}`, `\ref{}`, and quotation. The compiled PDF now contains zero em dashes; numeric ranges (`--`) and the Appendix A `longtable` were left untouched. The "no em dash" rule was also recorded in `context/style_guide.md`, `AGENTS.md`, `CLAUDE.md`, and `.clinerules`. Build verified clean (`latexmk -pdf`).


**Revision log (participant and evaluation revision).** The empirical evaluation was restructured to eleven (11) purposively selected participants in two separately reported groups: ten (10) student participants who evaluate the applicant portal and one (1) expert administrative evaluator (a head of the Office of Admission and Aid) who evaluates the Unified Admin Dashboard. RQ2(b) (§1.2) now names the expert administrative evaluator; §1.3 Objective 4 covers the two paired instrument sets; the §1.5 `Evaluation Scope` bullet was rewritten and a new `Single Expert Administrative Evaluator` limitation was added (a second proposed bullet, `Evaluator Roles Not Covered by Usability Testing`, was omitted because Chapter 3 defines no Lifecycle Test Case Matrix covering the Interview Panel, School Scholarship Subcommittee, and Scholarship Director roles); §2.7 recasts the Tullis & Stetson claim (`\cite{ref42}`); §3.1 sample justification rewritten; a new Office-of-Admission-and-Aid clarification paragraph was added after the RBAC matrix (§3.3.3); §3.4 opening rewritten; §3.4.1 now assigns Tasks 1--3 to students and Task 4 to the evaluator (Task 4 now changes five statuses); §3.4.2 adds separate SUS reporting, an `Administrative Pre/Post Survey Analysis` bullet, and the evaluator edits to the notification metrics; §3.4.3 was renamed `Pre-Study and Post-Prototype Survey Instruments` and gained Appendix D/E descriptions; §3.5 gained the identifiable-evaluator ethics note and the `Appendices~B to~E` scope. New Appendix D (Pre-Study Administrative Process Validation Survey) and Appendix E (Post-Prototype Administrative Evaluation Survey) were added and wired into `main.tex`; both mirror the Appendices B/C formatting (plain non-bold `Question Type:`/`Options:`/`Scale Columns:`/`Row Sub-tasks:` labels, one top-level `itemize` with nested option/scale lists, run-on `1. ... 2. ...` row items, component titles and follow-on prompts merged inline, no `\section*` headers). `references.bib` gained `ref51` (Davis, 1989, MIS Quarterly, `needs-manual-curation`). Chapter 4's evaluation paragraph (§4.10) was updated to the 11-participant split. Build verified clean (`latexmk -pdf -g`, 66 pp.).


## Front Matter
- [x] Title page (rebuilt in `main.tex` titlepage; retitled to the revised manuscript) `[Complete]`
- [ ] Abstract `[Missing]` — write last, after results
- [ ] List of Tables / List of Figures `[Missing]` — add `\listoftables`/`\listoffigures` when tables exist

## Chapter 1 — Introduction (`chapters/01_introduction.tex`) `[Complete]`
- 1.1 Background of the Study `[Complete]` — reframed to the three internal scholarship tracks; Table 1 rebuilt as `booktabs` (AdDU Internal Scholarship Selection Tracks)
- 1.2 Problem Statement `[Complete]` — three problems + the new RQ1–RQ4 as `enumerate` (duplicated legacy RQ block removed)
- 1.3 Objectives of the Study `[Complete]`
- 1.4 Significance of the Study `[Complete]`
- 1.5 Scope and Limitations `[Complete]` — scope bullets + 8 limitation bullets migrated as `itemize`; the "User Base Limitation" bullet was corrected in the Unified Admin Dashboard pass to include incoming Grade 12 applicants (it previously named enrolled undergraduates only)

## Chapter 2 — Review of Related Works (`chapters/02_related_works.tex`) `[Complete]`
- 2.1 Digital Transformation in Higher Education Administration `[Complete]`
- 2.2 Web-Based Scholarship Management Systems `[Complete]`
- 2.3 Data Organization and Automated Matching in Information Systems `[Complete]`
- 2.4 Search and Filtering Mechanisms for Financial Aid Discovery `[Complete]`
  - 2.4.1 Policy Desynchronization in Manual Systems `[Complete]`
- 2.5 Rule-Based Matching and Faceted Search in Deployed Systems `[Complete]`
- 2.6 Accessibility and Remote Access in Web-Based Systems `[Complete]` — NEW (RWA/PWA/Capacitor architecture rationale); subsequent sections renumbered 2.7–2.10. *(A duplicate copy that had been pasted onto the end of the §2.5 paragraph was removed in the Unified Admin Dashboard pass.)*
- 2.7 Usability and User Experience in Educational Platforms `[Complete]`
- 2.8 Policy, Data Privacy, and Access Control in Financial Aid Information Systems `[Complete]`
- 2.9 Theoretical Framework (DeLone & McLean; Figure 2.1) `[Complete]` — figure regenerated from the revised IS Success Model diagram
- 2.10 Synthesis of RRL and Research Gaps `[Complete]` — Table 2 reconstructed as `booktabs` (keystone artifact repaired)

## Chapter 3 — Methodology (`chapters/03_methodology.tex`) `[Complete]`
- 3.1 Research Design `[Complete]` — within-subjects comparative design
- 3.2 System Development Life Cycle (SDLC) `[Complete]` — Figure 3.1 (Agile SDLC flowchart) regenerated from the revised diagram
- 3.3 System Architecture and Algorithmic Logic `[Complete]`
  - 3.3.1 The "Smart Eligibility Checker" (Automated Matching Engine) `[Complete]` — pseudocode restored as Listing 3.1; Figure 3.2 (end-to-end application process flow) follows the listing
  - 3.3.2 Dynamic Faceted Search and Backend Indexing Strategy `[Complete]`
  - 3.3.3 System Architecture and Cloud Infrastructure `[Complete]` — Figure 3.3 (three-layer architecture) regenerated from the revised diagram; the RBAC matrix (Table 3.1, `tab:rbac`), its unification-rationale paragraph, and the Data Privacy discussion follow inside this section (the stray "3.3.4" heading literal was removed in the Unified Admin Dashboard pass)
  - 3.3.4 Automated Notification Subsystem `[Complete]`
- 3.4 Testing & Evaluation Procedures (ISO/IEC 25010 Task-Based Usability Protocol) `[Complete]`
  - 3.4.1 Step-by-Step Testing Procedure (Tasks 1–4) `[Complete]`
  - 3.4.2 Data Analysis and Statistical Tools `[Complete]` — includes the 15-profile Smart Eligibility Checker test-case matrix and notification delivery metrics; §3.4.1 converted to `enumerate`
  - 3.4.3 Pre-Study and Post-Prototype Survey Instruments `[Complete]` — renamed in the participant-revision pass; now describes the student pair (Appendices B/C) and the administrative pair (Appendices D/E) via `\paragraph{}` blocks
- 3.5 Ethical Considerations `[Complete]`

## Chapter 4 — Theoretical Background (`chapters/04_theoretical_background.tex`) `[Complete]`
- 4.1 Introduction `[Complete]`
- 4.2 Relational Database Theory and Normalization `[Complete]` — Table 4 (Anomalies & Resolutions) reconstructed as `booktabs`
  - 4.2.1 The Relational Model and Anomaly Prevention · 4.2.2 Progression Through Normal Forms
- 4.3 Centralized Information Systems and Cloud Infrastructure Theory `[Complete]` — Table 5 (storage comparison) reconstructed as `booktabs`
- 4.4 Metadata-Driven Document Management `[Complete]`
- 4.5 Rule-Based Expert Systems Theory `[Complete]` — Table 6 (Conflict Resolution Strategies) reconstructed as `booktabs`
  - 4.5.1 Knowledge Representation and the Inference Engine · 4.5.2 Conflict Resolution and the Exclusion Flag Hierarchy
- 4.6 Information Foraging Theory and Faceted Search `[Complete]`
- 4.7 Event-Driven Architecture for Asynchronous Notification `[Complete]` — Table 7 (EDA Trigger Mapping) reconstructed as `booktabs`; APIs updated to Iprogsms/Resend
- 4.8 Role-Based Access Control and Data Privacy `[Complete]`
- 4.9 Empirical Process Control Theory in Agile Development `[Complete]`
- 4.10 Human-Computer Interaction and the ISO/IEC 25010 Model `[Complete]`

## References
- [x] `references.bib` generated from legacy reference list (50 entries) `[Draft/Partial]` — all entries `@misc` with literal author strings and `needs-manual-curation` keyword; must be upgraded to proper types/venues/DOIs

## Chapter 5 — Results and Discussion `[Missing]`
- 5.1 Participant Demographics `[Missing]`
- 5.2 RQ1: Perceived Time/Effort Reduction (paired pre/post comparison) `[Missing]`
- 5.3 RQ2: Smart Eligibility Checker Performance (correctness + accuracy) `[Missing]`
- 5.4 RQ3: Deadline Management & Notification Effectiveness `[Missing]`
- 5.5 RQ4: Usability (SUS score + ISO/IEC 25010 criteria) `[Missing]`
- 5.6 Qualitative Findings & Interface Feedback `[Missing]`

## Chapter 6 — Summary, Conclusions, and Recommendations `[Missing]`
- 6.1 Summary of the Study `[Missing]`
- 6.2 Conclusions per Research Question `[Missing]`
- 6.3 Recommendations & Future Work (e.g., weighted award-allocation algorithms, registrar integration) `[Missing]`

## Appendices
- Appendix A — Internal Financial Aid Pipelines Listed at AdDU `[Complete]` — revised to the three internal scholarship tracks (`longtable`, 3 rows × 4 cols) with `\url{}` sources
- Appendix B — Pre-Study Student Problem Validation Survey `[Complete]`
- Appendix C — Post-Prototype Perceived Effort Survey `[Complete]`
- Appendix D — Pre-Study Administrative Process Validation Survey `[Complete]` — added in the participant-revision pass (`chapters/08_appendix_d.tex`, `\label{app:pre-admin-survey}`)
- Appendix E — Post-Prototype Administrative Evaluation Survey `[Complete]` — added in the participant-revision pass (`chapters/09_appendix_e.tex`, `\label{app:post-admin-survey}`)
