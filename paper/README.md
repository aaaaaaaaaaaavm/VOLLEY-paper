# The paper

`paper.tex` is the source. `VOLLEY_IEEE_Conference.pdf` is the last compiled build.

> This is the manuscript's home. It moved out of the VOLLEY flagship on 2026-08-13 under
> ADR-028: the flagship is an engineering record and holds no LaTeX. See [`BUILD.md`](BUILD.md)
> for the current build and evidence ownership.

## Current build, 2026-10-10

| | |
|---|---|
| `VOLLEY_IEEE_Conference.pdf` | 18 pages, US Letter. The canonical build; includes finite-force, matched-mission, installed-burden, orbit-requirement and CAD-fit findings |
| `../print/Adityavardhan_Mishra_VOLLEY_IEEE_2026_Letter.pdf` | the same file, named for handover |
| `../print/Adityavardhan_Mishra_VOLLEY_IEEE_2026_A4_Print.pdf` | 18 pages, A4. Built by `paper_a4.tex`, which passes `a4paper` to IEEEtran and then `\input`s the same `paper.tex`; PDF extraction order around equations may differ with the layout |
| Build | pdfTeX, TeX Live 2025, `latexmk` builds of Letter and A4; 18 pages each |

This build presents Gen5 as an evaluated computational configuration with a negative 3U decision; its historical speed is challenged by finite geometry. Gen6 is future research. It corrects the earlier claim that elapsed time between zero-impulse releases from an
unchanged host produces a persistent in-track phase offset. The corrected text and figure caption
require an actual relative state change for lasting separation.

The 9 October review update adds a separate Cartesian check of the immediate 28.800775 km
semi-major-axis rise and a FreeCAD reference assembly check that **fails** side-fed packaging
by 11 mm. Neither check validates atmospheric lifetime, moving release mechanics or hardware.
An additional algebraic audit passes basic mass, stroke and recovery identities and
reconciles the old 124.488 J compact-output gross remainder to assumed converter, auxiliary and integration terms. The host, material, manufacturing and TRL language
has been revised so the paper does not imply provider approval or hardware qualification.

It is an IEEE-*formatted* manuscript, using the IEEEtran class. Submission compliance for any
particular venue is not claimed, page and abstract limits are set by the conference or journal,
and none has been selected.

[Earlier build history](BUILD_HISTORY.md) is retained as a dated archive; it does not define the present claims.
