# ISO Audit Revision Tracker — ScholarPath AdDU

Source: *Digital University Scholarship Admission System: Revised ISO Audit Preparation Report* (Sep 28, 2026), produced after the Key Informant Interview with the admissions office.

Key dates: **code freeze + manuscript submission Sat, Oct 10, 2026** · **ISO audit Oct 12–15, 2026**.

This revision supersedes the Smart Eligibility Checker framing. It takes priority over the foundation items in `drafting_queue.md` (user-authorized, 2026-09-28).

## Mandatory Revisions (REV)

| ID | Area | Required revision | Manuscript targets | Status |
|---|---|---|---|---|
| REV-01 | System Architecture | Remove the matching engine; describe a Data-Feeding Committee Portal with an audit log | Ch1 §1.1/§1.3, Ch3 §3.3, Ch4 §4.5, Fig. 3 (deleted), Fig. 4 | Done in text; Fig. 4 redraw pending |
| REV-02 | Use Case & Scope | Credential verification 100% inside the University Scholarship Office; no third-party verifier | Ch3 §3.3 architecture, Ch1 §1.5 | Done |
| REV-03 | Conceptual Framework | Scholar Path = Application Lifecycle Path + Academic Trajectory Path | Ch1 §1.1, Ch3 §3.3.1, Ch2 §2.8 | Done in text; lifecycle figure pending |
| REV-04 | Data Workflows | Two-stage submission (Phase 1 Pre-qualification, Phase 2 Full Verification) into the Document Vault | Ch3 §3.3.1, Ch4 §4.4 | Done |
| REV-05 | Decision Engine | Five school subcommittee rule sets (SON, SEA, SBG, SOE, SAS) | Ch3 §3.3.2, Ch4 §4.5 | Done |
| REV-06 | Exception Handling | 5-calendar-day Conditional Revert; staff-confirmed lapse | Ch3 §3.3.3, Ch4 §4.7 | Done |
| REV-07 | Terminology | SAS, SBG, SEA; "high school average of at least 85%" | All chapters, title page | Done |
| REV-08 | Interview Process | Panels assigned per application (per SOP) | Ch3 §3.3.2 | Done (configurable; OPEN-2) |
| REV-09 | Automated Decisions | Staff confirm lapses; subcommittees confirm reallocations | Ch3 §3.3.3–3.3.4, Ch4 §4.7 | Done |
| REV-10 | SOP Alignment | Add application form, homeroom recommendation, rank certificate, Office of Admission release step | Ch3 §3.3.1 | Done |

## Open Items (OPEN) — from report §10

Each unresolved rule is written as a configurable parameter in the prose and tagged `% TODO(OPEN-n)` in the `.tex` source. Nothing unconfirmed is stated as fact in the PDF. When an item is resolved, replace the configurable wording with the confirmed rule, delete the TODO comment, and mark it resolved here.

| ID | Question | Status |
|---|---|---|
| OPEN-1 | Which ISO standard is the audit against, and is the matching-engine ban an ISO requirement or an internal governance rule? | Open |
| OPEN-2 | Who conducts interviews: school-based panels (SOP step 5) or the Scholarship Director and designated interviewers? | Open |
| OPEN-3 | Does the Jubilee grant guarantee override a school's hard entrance exam cutoff? | Open |
| OPEN-4 | Which school houses Computer Science and IT, and does SAS have four departments with Assistant Deans? | Open |
| OPEN-5 | Currency and period of the 150,000 income limit; unit of the 10,000 minimum GIA grant | Open |
| OPEN-6 | Residence photos or proof of residence? Are the personal essay and ethnolinguistic endorsement still required? | Open |
| OPEN-7 | Is the top-50% interview cut a formal rule? | Open |
| OPEN-8 | Who performs SOP step 3 verification; when does the 5-day clock start; when are applicants notified after the Office of Admission release? | Open |
| OPEN-9 | Does the SOP's "academic grant" refer to the Jubilee track? | Open |
| OPEN-10 | Will the SOP be formally revised for two-stage submission and Conditional Revert, or must the system follow it as written? | Open |

Find the locations with: `grep -rn "TODO(OPEN-" chapters/`

## Local Items (L) — raised during manuscript planning, not in the report

| ID | Question | Status |
|---|---|---|
| L-1 | Is the University Scholarship Office a unit of the Office of Student Affairs (OSA), or separate? The manuscript now uses "University Scholarship Office" throughout. | Open |
| L-2 | Is Form 230-SCH the SOP "application form"? The manuscript now says "the SOP application form". | Open |
| L-3 | Has Appendix B (Pre-Study Survey) already been administered? If yes, revert Appendix B edits and keep only the §3.4.3 remapping. | Open — Appendix B was revised assuming **not yet administered** |
| L-4 | Applicants may be under 18. The §3.5 ethics text now requires parental/guardian consent for minors; confirm with the ethics adviser. | Open |
| L-5 | Final manuscript title wording to confirm with the adviser. | Open |
| L-7 | `ref51` (SOP) was entered with year 2026 and the University Scholarship Office as issuer; confirm the actual title, year and issuing office. | Open |
| L-6 | New theory sources for decision support / human oversight (Ch2 §2.3, Ch4 §4.5) must be real, team-supplied references appended as `ref53`+. | Open |

## Figures (to be drawn externally, exported as PNG to `figures/`)

| File | Action | Status |
|---|---|---|
| `figure_lifecycle.png` | New — 10-step lifecycle with 1 loop back, per report §6 diagram | Pending (placeholder box in Ch3) |
| `figure4_architecture.png` | Redraw — relabel "Student Mobile/Web App" → "Applicant/Scholar App" and "OSA & Department Admin Portal" → "Committee Portal (Scholarship Office, Panels, Subcommittees, Office of Admission)"; add an Audit Log store in the backend layer; keep no external verifier | Pending (old image still shown; TODO in source) |
| `figure1_issm.png` | Redraw — currently shows "Automated Matching", "Accurate QPI data", "Prompt OSA support", "Equitable Aid Distribution". Replace with: System Quality = "24/7 Accessibility, Audit-Logged Human Decisions, Security"; Information Quality = "Verified Applicant Data, Real-time Status Notifications"; Service Quality = "Prompt Scholarship Office Support, Clear Revert Notices"; Net Benefits = "Reduced Administrative Bottlenecks, Traceable Committee-Led Decisions" | Pending (old image still shown; TODO in source) |
| `figure3_flowchart.png` | Deleted from manuscript (REV-01) | Done — file removed from `figures/` |
