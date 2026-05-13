# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

An ACL (*ACL) conference paper using the official ACL LaTeX style files. The main paper source is `acl_latex.tex` with styles from `acl.sty`.

## Build Commands

```bash
# Full build (compile + bibliography + resolve references)
pdflatex acl_latex.tex && bibtex acl_latex && pdflatex acl_latex.tex && pdflatex acl_latex.tex

# Quick compile (no bibliography update)
pdflatex acl_latex.tex
```

For LuaLaTeX/XeLaTeX (needed for non-Latin scripts): use `acl_lualatex.tex` instead with `lualatex` or `xelatex`.

## Submission Modes

Controlled by the `\usepackage` option in the preamble of the .tex file:

- `\usepackage[review]{acl}` — Anonymous review version (line numbers, no author names/acknowledgments)
- `\usepackage{acl}` — Final camera-ready version (no line numbers)
- `\usepackage[preprint]{acl}` — Non-anonymous preprint with page numbers

## Key Files

- `acl_latex.tex` — Main paper source (pdfLaTeX)
- `acl_lualatex.tex` — Alternative template for LuaLaTeX/XeLaTeX
- `custom.bib` — Bibliography entries (add new references here)
- `acl.sty` — Style file (do not modify)
- `acl_natbib.bst` — Bibliography style (do not modify)
- `anthology.bib.txt` — ACL Anthology references (rename to .bib and include via `\bibliography{anthology,custom}` if needed)

## Formatting Constraints

- Long papers: 8 pages (review) / 9 pages (final) + unlimited references
- Short papers: 4 pages (review) / 5 pages (final) + unlimited references
- A4 paper format only
- Citations use natbib: `\citet{key}` for textual, `\citep{key}` for parenthetical, `\citeposs{key}` for possessive
- BibTeX entries must use LaTeX accent commands (e.g., `{\"a}`) not Unicode
- All references should include DOIs or ACL Anthology URLs when possible
