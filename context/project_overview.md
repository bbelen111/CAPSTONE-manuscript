# Project Overview — ScholarPath AdDU

## Working Title
**ScholarPath AdDU: A Web-Based Scholarship Application Processing and Committee Decision-Support System for Ateneo de Davao University's Internal Scholarship Tracks**

## Team & Venue
- Authors: Raphael Miguel Operario, Brendon Justine Belen, Eriel John Espinosa
- Adviser: Adrian Ablazo, MSc.
- Institution: Computer Studies Cluster, School of Arts and Science, Ateneo de Davao University (AdDU), Davao City
- Requirement: Capstone Project and Research 1, 2nd Semester, SY 2025–2026 (target: April 2026)

## Core Thesis
AdDU administers three **internal scholarship tracks** (Jubilee, Grant-in-Aid, Working Scholars) — handling roughly 1,326 paper applications per cycle — through decentralized, largely paper-based processes (Form 230-SCH, sealed letters, static announcements), causing discovery friction, eligibility mismatch, and missed deadlines. A centralized, web-based platform — unifying **two-stage digital application processing, first-pass eligibility screening (the "Smart Eligibility Checker" with the Exclusion Flag Hierarchy), document management (the two-stage Document Vault with Conditional Revert), a Data-Feeding Committee Portal, and proactive notification (event-driven SMS/email)** — reduces the time and effort applicants spend, while remaining compliant with RA 10173 (Philippine Data Privacy Act of 2012).

## Technical Domain
- Web + hybrid mobile application (Vite JS bundle wrapped via Capacitor)
- Supabase/PostgreSQL backend: normalized relational schema, compound B-Tree + range indexing, row-level role-governed access
- Rule-based expert system ("Smart Eligibility Checker") with an Exclusion Flag Hierarchy conflict-resolution mechanism
- Dynamic faceted search over four metadata facets (funding origin taxonomy)
- Event-driven notification subsystem via serverless Edge Functions (Iprogsms SMS, Resend email)
- Two-stage Application Lifecycle with a 5-calendar-day Conditional Revert window and a Data-Feeding Committee Portal
- NIST RBAC for data privacy enforcement

## Research Questions (from §1.2 Problem Statement)
1. **RQ1 (Time/effort):** What is the perceived reduction in the time and effort AdDU scholarship applicants spend on the application process when using the two-stage digital submission of ScholarPath AdDU compared to the current paper-based process?
2. **RQ2 (Application Lifecycle + committee portal):** How does the Application Lifecycle workflow perform in (a) functional correctness — do status transitions (including Conditional Revert and Lapsed) match a structured Lifecycle Test Case Matrix with no status change lacking a recorded human actor — and (b) perceived usefulness of the Data-Feeding Committee Portal to University Scholarship Office staff and School Scholarship Subcommittee members?
3. **RQ3 (Deadline management):** To what extent does the automated notification subsystem reduce missed submission deadlines and uncorrected incomplete files among applicants?
4. **RQ4 (Usability):** What is the overall system usability and performance efficiency of ScholarPath AdDU (SUS + ISO/IEC 25010 functional suitability)?

## Methodology Summary
- **Design:** Within-subjects comparative usability evaluation; pre-study baseline (Appendix B) vs. post-prototype (Appendix C) paired instruments on the same cohort.
- **Development:** Agile SDLC, five iterative phases (requirements via Key Informant Interviews → design → development → testing → deployment/refinement).
- **Evaluation:** Task-based observational testing (completion rates, time-on-task) with a purposive sample of ~10–15 AdDU students, OSA staff, and Department Chairs/Coordinators; SUS (Bangor et al.; Tullis & Stetson sample-size rationale) + ISO/IEC 25010 framework; descriptive statistics for item-to-item mean comparison.
- **Ethics:** RA 10173 compliance, informed consent, pseudonymized mock data, secure disposal.

## Theoretical Anchors (Chapter 4)
DeLone & McLean IS Success Model (umbrella) · Relational theory/normalization (Codd) · Cloud infrastructure (NIST; Tanenbaum) · Metadata-driven organization (Glushko) · Rule-based expert systems (Buchanan & Duda) · Information Foraging Theory (Pirolli & Card) · Event-driven architecture (IBM) · RBAC (Ferraiolo & Kuhn; Sandhu) · Empirical process control/Agile (Schwaber & Beedle) · HCI & ISO/IEC 25010 (Dix et al.)

## Target Audience
- Primary: Capstone defense panel and Computer Studies Cluster faculty
- Secondary: AdDU OSA administrators and similar Philippine HEI offices seeking a replicable paper-to-digital migration blueprint
- Tertiary: Philippine higher-education information-systems researchers (RRL conversation: Al-Ayyubi & Maulana; Daluyon & Bilog; Amer; Orgianus et al.)

## Manuscript Status Snapshot
Chapters 1–4 and Appendices A–C exist as a compiling LaTeX draft, now migrated to the **revised (Capstone 2) manuscript**: committee decision-support framing, the three internal scholarship tracks (Jubilee, Grant-in-Aid, Working Scholars), Iprogsms/Resend notification APIs, the RBAC matrix (Table 3), and the Smart Eligibility Checker test-case matrix. **Results/Discussion and Conclusion chapters do not yet exist** — the evaluation is scheduled/prospective in the text ("will be administered"), consistent with a Research 1 manuscript mid-stream. See `outline.md` and `drafting_queue.md`.
