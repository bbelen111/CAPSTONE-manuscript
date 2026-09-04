# Master Outline & Completion Tracker — ScholarPath AdDU

Status legend: `[Complete]` full prose in legacy draft, migrated · `[Draft/Partial]` present but structurally broken or thin · `[Missing]` not yet written.

## Front Matter
- [x] Title page (rebuilt in `main.tex` titlepage) `[Complete]`
- [ ] Abstract `[Missing]` — write last, after results
- [ ] List of Tables / List of Figures `[Missing]` — add `\listoftables`/`\listoffigures` when tables exist

## Chapter 1 — Introduction (`chapters/01_introduction.tex`) `[Complete]`
- 1.1 Background of the Study `[Complete]` — ⚠ Table 1 (AdDU Financial Aid Programs) embedded as flattened text; reconstruct as `booktabs`
- 1.2 Problem Statement `[Complete]` — contains the numbered problems + RQ1–RQ4 as flattened enumerations; convert to `enumerate`
- 1.3 Objectives of the Study `[Complete]`
- 1.4 Significance of the Study `[Complete]`
- 1.5 Scope and Limitations `[Complete]` — scope bullets + 8 limitation bullets migrated as `itemize`

## Chapter 2 — Review of Related Works (`chapters/02_related_works.tex`) `[Complete]`
- 2.1 Digital Transformation in Higher Education Administration `[Complete]`
- 2.2 Web-Based Scholarship Management Systems `[Complete]`
- 2.3 Data Organization and Automated Matching in Information Systems `[Complete]`
- 2.4 Search and Filtering Mechanisms for Financial Aid Discovery `[Complete]`
  - 2.4.1 Policy Desynchronization in Manual Systems `[Complete]`
- 2.5 Rule-Based Matching and Faceted Search in Deployed Systems `[Complete]` — note: legacy numbering was inconsistent (TOC vs body); renumbered by LaTeX
- 2.6 Usability and User Experience in Educational Platforms `[Complete]`
- 2.7 Policy, Data Privacy, and Access Control in Financial Aid Information Systems `[Complete]`
- 2.8 Theoretical Framework (DeLone & McLean; Figure 1) `[Complete]`
- 2.9 Synthesis of RRL and Research Gaps `[Complete]` — ⚠ Table 2 (Synthesis of System Gaps and Design Responses) flattened; reconstruct — this is the chapter's most load-bearing table

## Chapter 3 — Methodology (`chapters/03_methodology.tex`) `[Complete]`
- 3.1 Research Design `[Complete]` — within-subjects comparative design
- 3.2 System Development Life Cycle (SDLC) `[Complete]` — Figure 2 (Agile SDLC flowchart) restored
- 3.3 System Architecture and Algorithmic Logic `[Complete]`
  - 3.3.1 The "Smart Eligibility Checker" (Automated Matching Engine) `[Complete]` — pseudocode restored as Listing 1
  - 3.3.2 Dynamic Faceted Search and Backend Indexing Strategy `[Complete]`
  - 3.3.3 System Architecture and Cloud Infrastructure `[Complete]` — Figure 4 restored
  - 3.3.4 Role-Based Access Control `[Complete]`
  - 3.3.5 Automated Notification Subsystem `[Complete]`
- 3.4 Testing & Evaluation Procedures (ISO/IEC 25010 Task-Based Usability Protocol) `[Complete]`
  - 3.4.1 Step-by-Step Testing Procedure (Tasks 1–4) `[Complete]`
  - 3.4.2 Data Analysis and Statistical Tools `[Complete]`
  - 3.4.3 Pre-Study / Post-Prototype Survey Instruments `[Complete]`
- 3.5 Ethical Considerations `[Complete]`

## Chapter 4 — Theoretical Background (`chapters/04_theoretical_background.tex`) `[Complete]`
- 4.1 Introduction `[Complete]`
- 4.2 Relational Database Theory and Normalization `[Complete]` — ⚠ Table 4 (Anomalies & Resolutions) flattened
  - 4.2.1 The Relational Model and Anomaly Prevention · 4.2.2 Progression Through Normal Forms
- 4.3 Centralized Information Systems and Cloud Infrastructure Theory `[Complete]` — ⚠ Table 5 (Paper vs. Document Vault comparison) flattened
- 4.4 Metadata-Driven Document Management `[Complete]`
- 4.5 Rule-Based Expert Systems Theory `[Complete]` — ⚠ Table 6 (Conflict Resolution Strategies) flattened
  - 4.5.1 Knowledge Representation and the Inference Engine · 4.5.2 Conflict Resolution and the Exclusion Flag Hierarchy
- 4.6 Information Foraging Theory and Faceted Search `[Complete]`
- 4.7 Event-Driven Architecture for Asynchronous Notification `[Complete]` — ⚠ Table 7 (EDA Trigger Mapping) flattened
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
- Appendix A — Financial Aid Pipelines Listed at AdDU `[Complete]` — reconstructed as `longtable` (54 rows × 4 cols) with `\url{}` sources
- Appendix B — Pre-Study Student Problem Validation Survey `[Complete]`
- Appendix C — Post-Prototype Perceived Effort Survey `[Complete]`
