# The paper

`paper.tex` is the source. `VOLLEY_IEEE_Conference.pdf` is the last compiled build.

> This is the manuscript's home. It moved out of the VOLLEY flagship on 2026-08-13 under
> ADR-028: the flagship is an engineering record and holds no LaTeX. See [`BUILD.md`](BUILD.md)
> for the current build and evidence ownership.

## Current build, 2026-10-12

| | |
|---|---|
| `VOLLEY_IEEE_Conference.pdf` | 20 pages, US Letter. The canonical build; includes finite-force, matched-mission, installed-burden, orbit-requirement and expanded exact-solid CAD-interference findings |
| `../print/Adityavardhan_Mishra_VOLLEY_IEEE_2026_Letter.pdf` | the same file, named for handover |
| `../print/Adityavardhan_Mishra_VOLLEY_IEEE_2026_A4_Print.pdf` | 20 pages, A4. Built by `paper_a4.tex`, which passes `a4paper` to IEEEtran and then `\input`s the same `paper.tex`; PDF extraction order around equations may differ with the layout |
| Build | pdfTeX, TeX Live 2025, `latexmk` builds of Letter and A4; 20 Letter pages and 20 A4 pages |

The ground-air CFD section is a **pre-test screen at a historical 16.388 m/s model point**. No full-scale VOLLEY shot or measured exit velocity exists. It is not a validation of the current finite-force release result.

This build presents Gen5 as an evaluated computational configuration with a negative 3U decision; its historical speed is challenged by finite geometry. Gen6 is future research. It corrects the earlier claim that elapsed time between zero-impulse releases from an
unchanged host produces a persistent in-track phase offset. The corrected text and figure caption
require an actual relative state change for lasting separation.

The 9 October review update adds a separate Cartesian check of the immediate 28.800775 km
semi-major-axis rise and a FreeCAD reference assembly check that **fails** side-fed packaging
by 11 mm. Neither check validates atmospheric lifetime, moving release mechanics or hardware.
The 12 October all-leaf audit further finds **17 intersecting pairs** in evaluated Gen5 and
**five** in widened R1, including sled--track and sled--stator conflicts in both. The
[audited pair list](../cad/GEN5_FULL_INTERFERENCE_AUDIT_2026_10_12.md) and separate
[Gen6 integration check](../cad/GEN6_INTEGRATION_AUDIT_2026_10_12.md) are held locally.
An additional algebraic audit passes basic mass, stroke and recovery identities and
reconciles the old 124.488 J compact-output gross remainder to assumed converter, auxiliary and integration terms. The host, material, manufacturing and TRL language
has been revised so the paper does not imply provider approval or hardware qualification.

It is an IEEE-*formatted* manuscript, using the IEEEtran class. Submission compliance for any
particular venue is not claimed, page and abstract limits are set by the conference or journal,
and none has been selected.

[Earlier build history](BUILD_HISTORY.md) is retained as a dated archive; it does not define the present claims.
