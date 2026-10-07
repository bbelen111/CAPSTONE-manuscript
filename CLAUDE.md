# CLAUDE.md — Claude Code Project Rules

Project: **ScholarPath AdDU** — a LaTeX capstone manuscript, not application code. There is no test suite, linter, or package manager; the only "build" is compiling the PDF. See `README.md` and `AGENTS.md` for the full brief. These rules apply to any work in this repository.

## Repository at a Glance

| Path | Purpose |
|---|---|
| `main.tex` | Master driver — preamble (global settings) + `\input` wiring **only**. No prose. |
| `chapters/*.tex` | One file per chapter/appendix (`01_introduction.tex` … `07_appendix_c.tex`); all body prose lives here. |
| `references.bib` | Bibliography (biblatex + biber, `sorting=none`). Keys `ref1`…`ref50`. |
| `figures/` | Raster PNGs + `addu_logo.png`; referenced via `\graphicspath{{figures/}}`. |
| `context/*.md` | Living working notes. **Read these first.** |

## Context First

- Read the relevant `context/*.md` notes before touching any chapter:
  - `project_overview.md` (system summary), `outline.md` (completion tracker), `style_guide.md` (conventions source of truth), `drafting_queue.md` (ordered task list), `audit_report.md` (known migration artifacts).
- Respect the ordering in `drafting_queue.md`: foundation repairs (items 1–3) → structural cleanup (4–7) → new prose (8–11). Do not draft new prose ahead of the foundation/cleanup items unless the user explicitly asks.

## Build & Verify

- Compile from the repo root after every edit:
  `latexmk -pdf -interaction=nonstopmode main.tex`
- Force a full rebuild (after label/citation/bib changes):
  `latexmk -pdf -g -interaction=nonstopmode main.tex`
- Leave the build clean: zero LaTeX errors, zero undefined references/citations, and a regenerated `main.pdf`. Check `main.log` for `undefined` / `Error` rather than trusting the exit code alone.
- If no LaTeX toolchain is available, say so explicitly instead of assuming a successful build, and keep the change clearly scoped.
- Build artifacts (`main.aux`, `main.bbl`, `main.log`, etc.) are generated output — never edit them by hand or commit them.

## Non-Negotiable Conventions

- **Preamble discipline:** `main.tex` is driver wiring only — no prose, no `\usepackage` additions, no content.
- **One chapter per file**, each starting with `\chapter{...}` + `\label{ch:...}`.
- **Labels:** `ch:`/`sec:`/`fig:`/`tab:`/`lst:`; `\label` goes **after** `\caption` inside floats.
- **Citations:** `\cite{refN}`; keys mirror legacy numbering — never invent keys; append `ref51`, `ref52`, … when adding sources; do not reorder `references.bib`.
- **Tables:** `booktabs` (`\toprule`/`\midrule`/`\bottomrule`), no vertical rules; `longtable` for large inventories (see Appendix A).
- **Escaping:** escape `% & # _ $ { } ~ ^` in prose; use `\url{}` for URLs.
- **Bibliography curation gate:** keep `keywords = {needs-manual-curation}` on every `references.bib` entry until its entry type, authors, venue, and DOI/URL have been verified and upgraded.

## Tone & Terminology (newly drafted prose)

- Academic, precise, declarative ("The engine evaluates…", not "We think…").
- Present tense for system behavior; future tense **only** for not-yet-executed procedures in Chapter 3 ("participants will be provided…").
- Spell out + abbreviate on first use ("Office of Student Affairs (OSA)"). Brand names verbatim: Supabase, PostgreSQL, Capacitor, Twilio, SendGrid, Vite, BIR, DOST, CHED.
- Exact terminology: "funding pipelines" (prefer **54** as the count), "Smart Eligibility Checker", "Exclusion Flag Hierarchy", "Document Vault", "Dynamic Faceted Search", "fit-margin relevance score".
- Avoid em dashes; use commas, colons, or parentheses instead.

## Claude Code Notes

- Environment is Windows; prefer the dedicated Read/Edit/Grep tools for `.tex`/`.bib`/`.md` files, and run `latexmk` from the repo root.
- Make targeted edits in `chapters/*.tex` rather than rewriting whole files, so diffs stay reviewable.
- Commit only when the user asks.

## Finish

1. Confirm the build is clean (no errors, no undefined references).
2. After completing any tracked task, update `context/outline.md` and `context/drafting_queue.md` accordingly.
3. Report what changed and whether the build was verified.
