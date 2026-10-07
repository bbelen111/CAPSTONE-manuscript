# AGENTS.md — Guidance for AI Assistants & Editors

This file instructs AI coding agents and human editors working on the **ScholarPath AdDU** capstone manuscript. Read this before making any change.

## Repository at a Glance

This is a **LaTeX academic manuscript**, not application code. There is no test suite, linter, or package manager. The only "build" is compiling the PDF, and the only hard requirement is that the document compiles cleanly after every change.

| Path | Purpose |
|---|---|
| `main.tex` | Master driver — preamble (global settings) + `\input` wiring **only**. No prose. |
| `chapters/*.tex` | One file per chapter/appendix; all body prose lives here. |
| `references.bib` | Bibliography (biblatex + biber). Keys `ref1`…`ref50`. |
| `figures/` | Raster PNGs + `addu_logo.png`; referenced via `\graphicspath{{figures/}}`. |
| `context/*.md` | Living working notes (outline, style guide, drafting queue, audit). **Read these first.** |

## Read These First

Before editing chapters, read the relevant notes in `context/`:

- `outline.md` — what exists (`[Complete]`) vs. what is missing (`[Draft/Partial]` / `[Missing]`).
- `style_guide.md` — voice, notation, citation, and LaTeX conventions (source of truth).
- `drafting_queue.md` — the **ordered** task list. Items 1–7 are foundation/cleanup that precede any new prose (items 8–11). Respect this ordering.
- `audit_report.md` — known migration artifacts and editorial verdict.

## Build Command

Always compile from the repository root:

```sh
latexmk -pdf -interaction=nonstopmode main.tex
```

`latexmk -pdf -g -interaction=nonstopmode main.tex` forces a full rebuild (use after label, citation, or bibliography changes).

**Verify a clean build after every edit** — zero LaTeX errors, zero undefined references/citations, and a regenerated `main.pdf`. If you cannot compile (no toolchain), say so explicitly and leave the change clearly scoped.

## Hard Conventions (do not violate)

- **Preamble discipline.** Never add prose, `\usepackage`, or content to `main.tex`. It is driver wiring only.
- **One chapter per file.** Each file starts with `\chapter{...}` and `\label{ch:...}`.
- **Label scheme.** `ch:`/`sec:`/`fig:`/`tab:`/`lst:` prefixes. Place `\label` **after** `\caption` inside floats.
- **Citations.** `\cite{refN}`. Keys are `refN` mirroring the legacy numbering; **never invent new keys** — append `ref51`, `ref52`, … when adding sources. Do not reorder `references.bib` (uses `sorting=none`).
- **Tables.** `booktabs` (`\toprule`/`\midrule`/`\bottomrule`), no vertical rules; `longtable` for large inventories (see Appendix A).
- **Escaping.** Escape `% & # _ $ { } ~ ^` in prose; use `\url{}` for URLs.
- **Bibliography curation gate.** Every entry in `references.bib` carries `keywords = {needs-manual-curation}`. Only remove it when you have verified and upgraded entry type, authors, venue, and DOI/URL. Otherwise leave the keyword intact.

## Drafting & Tone

- Voice: academic, precise, declarative ("The engine evaluates…", not "We think…").
- Present tense for system behavior; future tense **only** for not-yet-executed procedures in Chapter 3 ("participants will be provided…").
- Spell out + abbreviate on first use ("Office of Admission and Aid"). Brand names verbatim: Supabase, PostgreSQL, Capacitor, Iprogsms, Resend, Vite, BIR, DOST, CHED.
- Terminology must stay exact: "internal scholarship tracks" (three: Jubilee, Grant-in-Aid, Working Scholars), "Smart Eligibility Checker", "Exclusion Flag Hierarchy", "Document Vault", "Dynamic Faceted Search", "Conditional Revert", "Committee Portal", "fit-margin relevance score".
- Use em dashes sparingly (max ~1 per paragraph).

## Workflow Checklist

1. Read `context/` notes relevant to the task.
2. Make the edit in `chapters/*.tex` (or `references.bib`, or `context/*.md` as applicable).
3. Compile with `latexmk -pdf -interaction=nonstopmode main.tex`.
4. Confirm a clean build (no errors, no undefined references) before finishing.
5. Update `context/outline.md` / `context/drafting_queue.md` when you complete tracked work items.