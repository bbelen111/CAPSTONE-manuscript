# Style Guide — ScholarPath AdDU Manuscript

## Voice & Tone
- Academic, precise, declarative. Prefer "The engine evaluates…" over "We think the engine might…".
- Present tense for system behavior ("the engine applies the exclusion flag"); future tense is acceptable **only** in Chapter 3 for procedures not yet executed at drafting time ("participants will be provided…").
- Use em dashes (---) for appositive elaboration, as in the source draft; do not overuse (max ~1 per paragraph).
- Spell out on first use with acronym: "Office of Student Affairs (OSA)", "Quality Point Index (QPI)", "System Usability Scale (SUS)". Thereafter use the acronym.
- Brand names verbatim: Supabase, PostgreSQL, Capacitor, Twilio, SendGrid, Vite, BIR, DOST, CHED.

## Math & Technical Notation
- Vectors/sets are not heavily used; when needed: bold lowercase for vectors (\(\mathbf{x}\)), calligraphic for sets.
- Inequalities in prose use `$\geq$` / `$\leq$` macros, not Unicode ≥ ≤.
- Membership: `$\in$`. Weights and scores: upright decimals (`0.5`), never fractions like ½.
- The fit-score formula in §3.3.1 uses equal weighting (0.5/0.5) — keep this consistent wherever restated.
- Algorithmic text lives ONLY in the `listings` environment (label `lst:matching`); never re-typeset pseudocode as prose.
- Identifiers (table/column names such as `Grant_Category`, `QPI_Requirement`) should use `\texttt{}` or `\lstinline` — underscore must be escaped in prose.

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

## Terminology Consistency (from source; keep these exact)
- "funding pipelines" (54 total), "Smart Eligibility Checker", "Exclusion Flag Hierarchy", "Document Vault", "Dynamic Faceted Search", "fit-margin relevance score", "Pre-Study Student Problem Validation Survey", "Post-Prototype Perceived Effort Survey"
- Categories: Internally Funded Endowments · Corporate & External Foundations · State-Sponsored Grants · Specialized Service Pipelines
- Numbers: "54 funding pipelines" and "over 50 programs" both appear; prefer **54** when citing the inventory count.
