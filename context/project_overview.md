# Project Overview — ScholarPath AdDU

> **Revised 2026-09-28** to follow the *Revised ISO Audit Preparation Report* (post-KII with the admissions office). See `iso_revision_tracker.md`. The earlier "Smart Eligibility Checker / 54-pipeline discovery" framing is retired.

## Working Title
**ScholarPath AdDU: A Data-Feeding Scholarship Application Lifecycle and Committee Decision-Support System for Ateneo de Davao University** (wording to confirm with the adviser — L-5)

## Team & Venue
- Authors: Raphael Miguel Operario, Brendon Justine Belen, Eriel John Espinosa
- Adviser: Adrian Ablazo, MSc.
- Institution: Computer Studies Cluster, School of Arts and Sciences (SAS), Ateneo de Davao University (AdDU), Davao City
- Requirement: Capstone Project and Research 1
- Key dates: code freeze + manuscript submission **Oct 10, 2026**; ISO audit **Oct 12–15, 2026**

## Core Thesis
AdDU's internal scholarship admission process handles approximately 1,326 applicants per cycle across three tracks (Jubilee Scholarship, Grant-in-Aid, Working Scholars). It follows an eight-step Standard Procedure for Scholarship Applications (SOP) with single-phase, paper-heavy document collection, and it relies on five School Scholarship Subcommittees (SON, SEA, SBG, SOE, SAS) that apply different selection criteria. ScholarPath AdDU is a **Data-Feeding Committee Portal**. It structures, verifies and presents applicant data, and a person makes and logs every status decision. Its components are:
- a two-stage digital submission into the Document Vault (Phase 1 Pre-qualification, Phase 2 Full Verification);
- a 5-calendar-day Conditional Revert for incomplete files;
- committee filtering partitioned by school;
- an audit log of every human status change;
- event-driven notifications.

External and government grants are outside selection; the university only processes their disbursement.

## Technical Domain
- Web + hybrid mobile application (Vite JS bundle wrapped via Capacitor)
- Supabase/PostgreSQL backend: normalized schema, compound B-Tree + range indexing for committee filtering, Row Level Security
- Application status state machine with human-confirmation guards (no module assigns, approves or disapproves without a recorded human action)
- Rule-based *screening flags* (baseline and subcommittee rule sets) that inform, never decide
- Event-driven notifications via Edge Functions (Twilio SMS, SendGrid email); applicant result notices only after the Office of Admission release
- NIST RBAC: Applicant/Scholar, University Scholarship Office staff, Interview Panel, School Subcommittee, Office of Admission, System Administrator

## Research Questions
1. **RQ1 (Time/effort):** Perceived reduction in applicant time and effort under the two-stage digital process versus the paper process.
2. **RQ2 (Lifecycle correctness + committee usefulness):**
   - (a) Do status transitions, including Conditional Revert and Lapsed, match the Lifecycle Test Case Matrix, with zero status changes lacking a recorded human actor?
   - (b) How useful do Scholarship Office staff and subcommittee members find the Committee Portal?
3. **RQ3 (Deadlines/corrections):** Effect of notifications on missed phase deadlines and uncorrected files.
4. **RQ4 (Usability):** SUS + ISO/IEC 25010 functional suitability and performance efficiency.

## Methodology Summary
- **Requirements:** KII with the admissions office/University Scholarship Office; the SOP (`ref51`); the ISO audit preparation report (`ref52`).
- **Design:** Within-subjects comparative usability evaluation (Appendix B pre, Appendix C post) plus a staff/committee instrument (Appendix D).
- **Development:** Agile SDLC, five phases. The audit-driven redesign counts as an Adaptation cycle.
- **Evaluation:**
  - Task-based testing (T1 registration, T2 two-phase upload and Revert response, T3 staff verification and lapse confirmation, T4 subcommittee review and reallocation confirmation).
  - The Lifecycle Test Case Matrix.
  - SUS and ISO/IEC 25010.
- **Ethics:** RA 10173, informed consent (parental/guardian consent for minors), mock data, secure disposal.

## Theoretical Anchors (Chapter 4)
- DeLone & McLean IS Success Model (umbrella)
- Relational theory/normalization (Codd)
- Cloud infrastructure (NIST)
- Metadata-driven organization (Glushko)
- Rule-based screening with human-in-the-loop decision support (Buchanan & Duda; decision-support sources to be supplied — L-6)
- Information Foraging Theory, applied to committee filtering
- Event-driven architecture
- RBAC (Ferraiolo & Kuhn; Sandhu)
- Empirical process control/Agile
- HCI & ISO/IEC 25010

## Manuscript Status Snapshot
Chapters 1–4 and Appendices A–D are revised to the ISO audit framing. Open questions are tagged `% TODO(OPEN-n)` in the source. Figures 1 and 4 must be redrawn and the lifecycle figure drawn. Results/Discussion and Conclusion chapters do not exist yet.
