# ScholarPath AdDU — Capstone Manuscript

**ScholarPath AdDU: A Web-Based Centralized Scholarship Discovery and Application Tracking System for Ateneo de Davao University Students**

This repository contains the LaTeX source for the capstone manuscript of **Capstone Project and Research 1** (2nd Semester, SY 2025–2026), targeting submission in **April 2026**.

| | |
|---|---|
| Authors | Raphael Miguel Operario, Brendon Justine Belen, Eriel John Espinosa |
| Adviser | Adrian Ablazo, MSc. |
| Institution | Computer Studies Cluster, School of Arts and Science, Ateneo de Davao University (AdDU), Davao City |
| Requirement | Capstone Project and Research 1, 2nd Semester, SY 2025–2026 |
| Document | Compiled PDF manuscript (`main.pdf`) |

---

## Table of Contents

- [Project Overview](#project-overview)
- [Repository Structure](#repository-structure)
- [Prerequisites](#prerequisites)
- [How to Run (Compile to PDF)](#how-to-run-compile-to-pdf)
- [Output](#output)
- [Common Issues & Troubleshooting](#common-issues--troubleshooting)
- [Working Notes (context/)](#working-notes-context)
- [Editing Workflow & Conventions](#editing-workflow--conventions)
- [Bibliography & Citations](#bibliography--citations)

---

## Project Overview

AdDU manages a financial aid ecosystem of **54 funding pipelines** (internally funded endowments, corporate & external foundations, state-sponsored grants, and specialized service pipelines) through largely decentralized, paper-based processes. **ScholarPath AdDU** addresses this by providing a centralized, web-based platform unifying **discovery (faceted search)**, **eligibility automation (rule-based "Smart Eligibility Checker" with the Exclusion Flag Hierarchy conflict-resolution mechanism)**, **document management (one-time-upload Document Vault)**, and **proactive, event-driven notification (SMS/email)**.

The manuscript is organized around four research questions and is grounded in a within-subjects comparative usability evaluation against the manual baseline. See [`context/project_overview.md`](context/project_overview.md) for the full project brief.

**Manuscript status:** Chapters 1–4 (Introduction, Related Works, Methodology, Theoretical Background) and Appendices A–C exist as a compiling draft. Results/Discussion (Ch. 5) and Conclusions (Ch. 6) are not yet written. See [`context/outline.md`](context/outline.md) and [`context/drafting_queue.md`](context/drafting_queue.md).

---

## Repository Structure

```text
CAPSTONE-manuscript/
├── main.tex                 # Master driver: preamble + chapter \input wiring (NO prose)
├── references.bib           # Bibliography source (biblatex + biber, 50 entries, ref1…ref50)
├── README.md                # This file
├── chapters/                # One .tex file per chapter / appendix
│   ├── 01_introduction.tex
│   ├── 02_related_works.tex
│   ├── 03_methodology.tex
│   ├── 04_theoretical_background.tex
│   ├── 05_appendix_a.tex    # Appendix A: 54-row funding-pipelines longtable
│   ├── 06_appendix_b.tex    # Appendix B: pre-study problem validation survey
│   └── 07_appendix_c.tex    # Appendix C: post-prototype perceived effort survey
├── figures/                 # Raster figures + AdDU logo (referenced via graphicspath)
├── context/                 # Living working notes (Markdown)
│   ├── project_overview.md  # Project brief & research questions
│   ├── outline.md           # Master outline & completion tracker
│   ├── style_guide.md       # Voice, notation, citation & LaTeX rules
│   ├── drafting_queue.md    # Ordered repair/drafting task list
│   └── audit_report.md      # Migration + editorial critique
└── .gitignore               # Ignores LaTeX build artifacts and main.pdf
```

---

## Prerequisites

To compile the manuscript you need a **LaTeX distribution** that provides `pdflatex`, `latexmk`, and `biber`. Recommended installs:

- **TeX Live** (cross-platform; includes everything needed out of the box):
  <https://www.tug.org/texlive/>
- **MiKTeX** (Windows-friendly; auto-installs missing packages on demand):
  <https://miktex.org/>

If you use your editor's built-in LaTeX tooling, most distributions ship a Recipe for `latexmk` — ensure the default recipe is set to **pdf** with **biber** as the bibliography engine.

You can verify your toolchain from a terminal with:

```sh
latexmk -version
biber --version
```

---

## How to Run (Compile to PDF)

The master file is `main.tex`. From the repository root, run:

### One-shot PDF build (recommended)

```sh
latexmk -pdf -interaction=nonstopmode main.tex
```

`latexmk` automatically runs the correct sequence: `pdflatex` → `biber` → `pdflatex` (×2) to resolve cross-references and the bibliography.

### Force a full rebuild

Use the `-g` (force) flag when you change labels, citations, or the bibliography:

```sh
latexmk -pdf -g -interaction=nonstopmode main.tex
```

### Clean up build artifacts

Remove all generated auxiliary files (keeps the working tree tidy with `.gitignore`):

```sh
latexmk -c
```

### Manual build (if `latexmk` is unavailable)

Run the steps in order so that references and the bibliography resolve:

```sh
pdflatex -interaction=nonstopmode main.tex
biber main
pdflatex -interaction=nonstopmode main.tex
pdflatex -interaction=nonstopmode main.tex
```

> **Run from the repository root.** Figures are referenced via `\graphicspath{{figures/}}` and chapters via `\input{chapters/...}`, both of which assume the working directory is the repo root.
---

## Output

A successful build produces `main.pdf` at the repository root (ignored by `.gitignore`). The document includes:

- Title page (AdDU logo + author/venue metadata)
- Table of contents
- Chapters 1–4
- Bibliography (printed via biblatex/biber, `numeric-comp` style)
- Appendices A–C

---

## Common Issues & Troubleshooting

| Symptom | Cause / Fix |
|---|---|
| `Citation 'refN' on page … undefined` | Bibliography not processed. Run `biber main` (or `latexmk -pdf`) so citations resolve, then re-run `pdflatex`. |
| Label references render as `??` | Cross-references unresolved. Run the full `pdflatex` → `biber` → `pdflatex` ×2 cycle (or `latexmk -g`). |
| `File 'chapters/….tex' not found` | You are compiling from a different directory. `cd` to the repo root first. |
| Missing package error at build | The distribution lacks a required package (e.g., `biblatex`). In MiKTeX enable auto-install; in TeX Live use `tlmgr install <package>`. |
| "Biber not found" | `biber` isn't in your `PATH`. Reinstall/refresh your distribution, or add its `bin` directory. |

---

## Working Notes (context/)

The `context/` folder holds the living notes that drive the project. Start here before editing:

- **`outline.md`** — master outline and completion tracker (`[Complete]` / `[Draft/Partial]` / `[Missing]`).
- **`style_guide.md`** — voice, math/notation, citation, and LaTeX conventions.
- **`drafting_queue.md`** — ordered list of remaining work (foundation repairs → structural cleanup → new prose). Compile after every item.
- **`audit_report.md`** — findings from the legacy-PDF migration and an editorial critique.
- **`project_overview.md`** — the project brief, research questions, and methodology summary.

---

## Editing Workflow & Conventions

- **Preamble discipline:** `main.tex` contains global settings and `\input` wiring **only** — never add prose there. All body content lives in `chapters/*.tex`.
- **One chapter per file.** Each chapter file starts with `\chapter{...}` and a `\label{ch:...}`.
- **Labels:** `ch:` for chapters, `sec:` sections, `fig:` figures, `tab:` tables, `lst:` listings. Always `\label` **after** `\caption` inside floats.
- **Tables:** use `booktabs` (`\toprule`/`\midrule`/`\bottomrule`), no vertical rules; use `longtable` for large inventories (see Appendix A).
- After any edit, recompile and confirm a clean build before committing.

---

## Bibliography & Citations

- Engine: **biblatex + biber**, style `numeric-comp`, `sorting=none` (citation numbers follow bibliography order, `ref1`…`ref50`).
- In-text: `\cite{refN}`; multi-cite `\cite{refA,refB}`. Never invent new keys ad hoc — append `ref51`, `ref52`, … when adding sources.
- **Heads-up:** every entry in `references.bib` currently carries `keywords = {needs-manual-curation}` and is `@misc`. These must be upgraded to proper entry types/venues/DOIs/URLs before submission — tracked as item 3 in `context/drafting_queue.md`. Do not remove the curation keyword until an entry is verified.