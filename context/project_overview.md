# Project Overview — ScholarPath AdDU

## Working Title
**ScholarPath AdDU: A Web-Based Centralized Scholarship Discovery and Application Tracking System for Ateneo de Davao University Students**

## Team & Venue
- Authors: Raphael Miguel Operario, Brendon Justine Belen, Eriel John Espinosa
- Adviser: Adrian Ablazo, MSc.
- Institution: Computer Studies Cluster, School of Arts and Science, Ateneo de Davao University (AdDU), Davao City
- Requirement: Capstone Project and Research 1, 2nd Semester, SY 2025–2026 (target: April 2026)

## Core Thesis
AdDU's 54-pipeline financial aid ecosystem is administered through decentralized, largely paper-based processes (Form 230-SCH, sealed letters, static announcements), causing discovery friction, eligibility mismatch, and missed deadlines. A centralized, web-based platform — unifying **discovery (faceted search), eligibility automation (rule-based matching with conflict resolution), document management (one-time-upload vault), and proactive notification (event-driven SMS/email)** — measurably reduces the time and effort students spend securing financial aid, while remaining compliant with RA 10173 (Philippine Data Privacy Act of 2012).

## Technical Domain
- Web + hybrid mobile application (Vite JS bundle wrapped via Capacitor)
- Supabase/PostgreSQL backend: normalized relational schema, compound B-Tree + range indexing, row-level role-governed access
- Rule-based expert system ("Smart Eligibility Checker") with an Exclusion Flag Hierarchy conflict-resolution mechanism
- Dynamic faceted search over four metadata facets (funding origin taxonomy)
- Event-driven notification subsystem via serverless Edge Functions (Twilio SMS, SendGrid email)
- NIST RBAC for data privacy enforcement

## Research Questions (from §1.2 Problem Statement)
1. **RQ1 (Time/effort):** What is the perceived reduction in time AdDU students spend discovering and applying for financial aid using ScholarPath AdDU vs. the current manual process?
2. **RQ2 (Matching accuracy):** How does the Smart Eligibility Checker perform in (a) functional correctness — does the Exclusion Flag Hierarchy produce expected outputs across edge-case profiles — and (b) accuracy of eligibility matching?
3. **RQ3 (Deadline management):** How does the automated notification subsystem affect students' ability to track multiple simultaneous deadlines?
4. **RQ4 (Usability):** What is the perceived usability of the platform (SUS + ISO/IEC 25010 functional suitability, performance efficiency)?

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
Chapters 1–4 exist as a revised draft (source PDF). **Results/Discussion and Conclusion chapters do not yet exist** — the evaluation is scheduled/prospective in the text ("will be administered"), consistent with a Research 1 manuscript mid-stream. See `outline.md` and `drafting_queue.md`.
