# Style Guide — ScholarPath AdDU Manuscript

## Voice & Tone
- Academic, precise, declarative. Prefer "The engine evaluates…" over "We think the engine might…".
- Present tense for system behavior ("the engine applies the exclusion flag"); future tense is acceptable **only** in Chapter 3 for procedures not yet executed at drafting time ("participants will be provided…").
- Use em dashes (---) for appositive elaboration, as in the source draft; do not overuse (max ~1 per paragraph).
- Spell out on first use with acronym: "School of Arts and Sciences (SAS)", "Grant-in-Aid (GIA)", "System Usability Scale (SUS)", "Standard Procedure for Scholarship Applications (SOP)". Thereafter use the acronym.
- Brand names verbatim: Supabase, PostgreSQL, Capacitor, Twilio, SendGrid, Vite, BIR, DOST, CHED.

## Math & Technical Notation
- Vectors/sets are not heavily used; when needed: bold lowercase for vectors (\(\mathbf{x}\)), calligraphic for sets.
- Inequalities in prose use `$\geq$` / `$\leq$` macros, not Unicode ≥ ≤.
- Membership: `$\in$`. Weights and scores: upright decimals (`0.5`), never fractions like ½.
- Algorithmic text lives ONLY in the `listings` environment (label `lst:lifecycle`, the application status state machine); never re-typeset pseudocode as prose.
- Identifiers (table/column names such as `School_Code`, `Verification_Status`) should use `\texttt{}` or `\lstinline` — underscore must be escaped in prose.

## Citation Rules
- Engine: **biblatex + biber**, style `numeric-comp`, `sorting=none` (citation numbers follow bibliography order ref1…ref50, mirroring the legacy draft's numbering).
- Keys are `refN` where N is the legacy reference number. Never invent new keys ad hoc; when adding sources, append `ref51`, `ref52`, …
- In-text: `\cite{refN}`; multi-cite `\cite{refA,refB}`. For "e.g." lists write `(e.g., \cite{ref21,ref44})`.
- **Every entry in `references.bib` currently carries `keywords = {needs-manual-curation}`** — verify entry type, venue, DOI/URL before removing the keyword.
- APA-ish author–date prose mentions ("Catibog \cite{ref16} identifies…") are the established pattern; keep them.

## LaTeX Rules (Preamble Discipline)
- `main.tex` contains preamble + `\input` wiring only. No prose, ever.
- One chapter per file in `chapters/`; every chapter file starts with `\chapter{...}` and a `\label{ch:...}`.
- Labels: chapters `ch:`, sections `sec:`, figures `fig:`, tables `tab:`, listings `lst:`.
- Always `\label` **after** `\caption` inside floats.
- Cross-reference with `\ref`/`\cref`-style text: hardcoded strings like "Section 3.4.3" from the legacy draft must eventually become `\ref{sec:...}`.
- Escape in prose: `% & # _ $ { } ~ ^`; use `\url{}` for URLs (xurl allows breaks anywhere — required for the Appendix A table).
- Tables: `booktabs` (`\toprule/\midrule/\bottomrule`), no vertical rules; long inventories use `longtable`.
- Figures: PNGs in `figures/`, referenced via `\graphicspath{{figures/}}`; prefer `[htbp]`; raster images extracted from the legacy PDF are placeholders — regenerate as vector/PDF when possible.

## Terminology Consistency (ISO audit revision, 2026-09-28; keep these exact)
Source of truth: `context/iso_revision_tracker.md` and the Revised ISO Audit Preparation Report.

**Use:**
- System framing: "Data-Feeding Committee Portal" — the system structures, filters and presents data; a person makes every status decision.
- "Application Lifecycle Path" and "Academic Trajectory Path" (the two meanings of "ScholarPath").
- "Phase 1 Pre-qualification" (January to April) and "Phase 2 Full Verification" (May to enrollment).
- "Conditional Revert" (5 calendar days) and the status "Lapsed" (a staff member confirms any disapproval).
- "Document Vault", "Pre-Study Student Problem Validation Survey", "Post-Prototype Perceived Effort Survey".
- Offices: "University Scholarship Office", "Office of Admission", "School Scholarship Subcommittee".
- Schools: School of Nursing (SON), School of Engineering and Architecture (SEA), School of Business and Governance (SBG), School of Education (SOE), School of Arts and Sciences (SAS).
- Tracks: Jubilee Scholarship, Grant-in-Aid (GIA), Working Scholars. External and government grants are a non-selection disbursement pathway.
- Threshold: "high school average of at least 85%". Volume: "approximately 1,326 applicants per cycle".

**Retired (do not use for the system):** "Smart Eligibility Checker", "Exclusion Flag Hierarchy", "fit-margin relevance score", "automated matching", "54 funding pipelines" as system scope (Appendix A keeps the 54-row inventory as institutional context only), "QPI" as the admission threshold, "CAS", "School of Business", "Computer Studies & Engineering", "Dynamic Faceted Search" as a core contribution (use "committee filtering").

**Unconfirmed rules:** write them as configurable parameters and tag the source with `% TODO(OPEN-n)`; never render "[To confirm]" in the PDF.
