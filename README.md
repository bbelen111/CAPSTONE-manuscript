# ScholarPath AdDU — Capstone Manuscript

**ScholarPath AdDU: A Web-Based Scholarship Application Processing and Committee Decision-Support System for Ateneo de Davao University's Internal Scholarship Tracks**

This repository contains the LaTeX source for the capstone manuscript of **Capstone Project and Research 1** (2nd Semester, SY 2025–2026), targeting submission in **November 2026**.

| | |
|---|---|
| Authors | Raphael Miguel Operario, Brendon Justine Belen, Eriel John Espinosa |
| Adviser | Adrian Ablazo, MSc. (Supervisor on the cover) |
| Panelists | Dr. Oneil Victoriano, Ms. Novie Joy Pelobello, MS, Ms. Grace Tacadao, MS |
| Program | Bachelor of Science in Information Technology |
| Institution | Computer Studies Cluster, Information Technology Department, School of Arts and Sciences, Ateneo de Davao University (AdDU), Davao City |
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

AdDU administers three **internal scholarship tracks** (Jubilee, Grant-in-Aid, Working Scholars) — handling roughly 1,326 paper applications per cycle — through largely decentralized, paper-based processes. **ScholarPath AdDU** addresses this by providing a centralized, web-based platform unifying **two-stage digital application processing**, **first-pass eligibility screening (rule-based "Smart Eligibility Checker" with the Exclusion Flag Hierarchy conflict-resolution mechanism)**, **document management (two-stage Document Vault with Conditional Revert)**, a **Data-Feeding Committee Portal**, and **proactive, event-driven notification (Iprogsms SMS / Resend email)**.

The manuscript is organized around four research questions and is grounded in a within-subjects comparative usability evaluation against the manual baseline. See [`context/project_overview.md`](context/project_overview.md) for the full project brief.

**Manuscript status:** Chapters 1–3 (Introduction, Review of Related Literature, Methodology with §3.6 Theoretical Background) and Appendices A–E exist as a compiling draft, migrated to the **revised (Capstone 2) manuscript** (committee decision-support framing, three internal scholarship tracks, Iprogsms/Resend notification APIs). Results/Discussion (Ch. 4) and Conclusions (Ch. 5) are not yet written. See [`context/outline.md`](context/outline.md) and [`context/drafting_queue.md`](context/drafting_queue.md).

---

## Repository Structure

```text
CAPSTONE-manuscript/
├── main.tex                 # Master driver: preamble + chapter \input wiring (NO prose)
├── references.bib           # Bibliography source (plain BibTeX + acm.bst, ref1…ref51)
├── README.md                # This file
├── chapters/                # One .tex file per chapter / appendix
│   ├── 00_frontmatter.tex    # Cover (Aguirre format), Abstract, Contents, LoT, LoF
│   ├── 01_introduction.tex
│   ├── 02_related_works.tex
│   ├── 03_methodology.tex    # Chapter 3 (includes §3.6 Theoretical Background)
│   ├── 05_appendix_a.tex    # Appendix A: internal-scholarship-tracks longtable
│   ├── 06_appendix_b.tex    # Appendix B: pre-study problem validation survey
│   ├── 07_appendix_c.tex    # Appendix C: post-prototype perceived effort survey
│   ├── 08_appendix_d.tex    # Appendix D: pre-study administrative process validation survey
│   └── 09_appendix_e.tex    # Appendix E: post-prototype administrative evaluation survey
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

To compile the manuscript you need a **LaTeX distribution** that provides `pdflatex`, `latexmk`, and `bibtex`. Recommended installs:

- **TeX Live** (cross-platform; includes everything needed out of the box):
  <https://www.tug.org/texlive/>
- **MiKTeX** (Windows-friendly; auto-installs missing packages on demand):
  <https://miktex.org/>

If you use your editor's built-in LaTeX tooling, most distributions ship a Recipe for `latexmk` — ensure the default recipe is set to **pdf** with **bibtex** as the bibliography engine.

You can verify your toolchain from a terminal with:

```sh
latexmk -version
bibtex --version
```

---

## How to Run (Compile to PDF)

The master file is `main.tex`. From the repository root, run:

### One-shot PDF build (recommended)

```sh
latexmk -pdf -interaction=nonstopmode main.tex
```

`latexmk` automatically runs the correct sequence: `pdflatex` → `bibtex` → `pdflatex` (×2) to resolve cross-references and the bibliography.

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
bibtex main
pdflatex -interaction=nonstopmode main.tex
pdflatex -interaction=nonstopmode main.tex
```

> **Run from the repository root.** Figures are referenced via `\graphicspath{{figures/}}` and chapters via `\input{chapters/...}`, both of which assume the working directory is the repo root.
---

## Output

A successful build produces `main.pdf` at the repository root (ignored by `.gitignore`). The document includes:

- Cover page (Aguirre format: department/degree line, seal, authors, Supervisor, Panelists) with no page number
- Abstract with a Keywords line (roman ii), Table of contents, List of tables, List of figures
- Chapters 1–3 (Chapter 1 restarts arabic numbering at page 1; paper size is A4; Theoretical Background is §3.6 inside Chapter 3)
- References (plain BibTeX with the `acm` style: alphabetical by author, plain `[n]` in-text numbers)
- Appendices A–E

---

## Common Issues & Troubleshooting

| Symptom | Cause / Fix |
|---|---|
| `Citation 'refN' on page … undefined` | Bibliography not processed. Run `bibtex main` (or `latexmk -pdf`) so citations resolve, then re-run `pdflatex`. |
| Label references render as `??` | Cross-references unresolved. Run the full `pdflatex` → `bibtex` → `pdflatex` ×2 cycle (or `latexmk -g`). |
| `File 'chapters/….tex' not found` | You are compiling from a different directory. `cd` to the repo root first. |
| Missing package error at build | The distribution lacks a required package (e.g., `booktabs` or `enumitem`). In MiKTeX enable auto-install; in TeX Live use `tlmgr install <package>`. |
| "BibTeX not found" | `bibtex` isn't in your `PATH`. Reinstall/refresh your distribution, or add its `bin` directory. |

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
- **One chapter per file.** Each chapter file starts with `\chapter{...}` and a `\label{ch:...}` (`chapters/00_frontmatter.tex` is the front-matter exception, and Chapter 3 also contains §3.6 Theoretical Background).
- **Labels:** `ch:` for chapters, `sec:` sections, `fig:` figures, `tab:` tables, `lst:` listings. Always `\label` **after** `\caption` inside floats.
- **Tables:** use `booktabs` (`\toprule`/`\midrule`/`\bottomrule`), no vertical rules; use `longtable` for large inventories (see Appendix A). Table captions go **above** the table (Aguirre format); figure captions stay **below** the figure.
- **Appendix instruments (B–E):** components are `\section` headings (B.1, B.2, …); questions are a `series`/`resume` `enumerate` labelled `Question n:`; options are nested `itemize`; Likert sub-tasks are a nested `enumerate`.
- After any edit, recompile and confirm a clean build before committing.

---

## Bibliography & Citations

- Engine: **plain BibTeX with `\bibliographystyle{acm}`** (`\bibliography{references}`); the printed list is sorted alphabetically by author, and in-text citations are plain numbers (`[1]`, `[9, 13, 14]`).
- In-text: `\cite{refN}`; multi-cite `\cite{refA,refB}`. Never invent new keys ad hoc — append `ref51`, `ref52`, … when adding sources.
- **Heads-up:** every entry in `references.bib` carries `keywords = {needs-manual-curation}` and **51 keys (`ref1`…`ref51`) are present**. 20 journal/conference entries have already been converted from `@misc` to `@article`/`@inproceedings` with proper `journal`/`volume`/`number`/`pages`/`booktitle` fields and real URLs/DOIs; the remaining 31 `@misc` entries (web pages and reports) still need verified URLs or replacement. Tracked as item 3 in `context/drafting_queue.md`. Do not remove the curation keyword until an entry is verified.