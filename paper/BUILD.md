# Building the manuscript

**This repository is the manuscript's authoritative home** as of 2026-08-13
([ADR-028](https://github.com/aaaaaaaaaaaavm/VOLLEY/blob/main/docs/adr/028-no-latex-in-the-flagship.md)).
`paper.tex`, `IEEEtran.cls`, the compiled PDF, `archive/` and `cv/` are **authored here** and are
not generated from anywhere. The flagship holds no LaTeX at all.

Everything else in this repository — `analysis/`, `validation/`, `paper/figures/`,
`BASELINE.md`, `PROVENANCE.md` — **is generated** from the flagship by
`tools/export_companion.py` and must never be hand-edited.

```
pdflatex paper.tex     # three passes from clean, until cross-references settle
cd cv && python3 make_cv.py && pdflatex cv.tex
```

Needs `texlive-latex-base`, `texlive-latex-recommended`, `texlive-publishers`,
`texlive-fonts-recommended` and `lmodern`. The CV generator reads `../../analysis/results/*.json`,
so run the analysis first if those are stale.

## The figures are not authored here

`paper/figures/*.png` are regenerated in the flagship by `tools/make_figures.py`, which imports
`analysis/` rather than re-deriving any physics. Editing a figure here is editing a copy. Change
the analysis, regenerate there, re-export.
