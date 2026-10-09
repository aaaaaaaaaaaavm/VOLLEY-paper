# Build and evidence ownership

`paper/paper.tex` is the editable manuscript. `paper/paper_a4.tex` uses the same source with A4 page geometry. The figures, model scripts, result JSON, validation sheets and CAD in this repository are local, inspectable snapshots; reading or rebuilding the paper does not require the flagship repository. The PDF is an IEEE-*formatted* draft. No venue has been selected, and this file does not claim submission compliance or acceptance.

## Build the manuscript

From `paper/`:

```bash
latexmk -pdf -interaction=nonstopmode -halt-on-error paper.tex
latexmk -pdf -interaction=nonstopmode -halt-on-error paper_a4.tex
```

The Letter result is `paper/VOLLEY_IEEE_Conference.pdf` (a copy of the `paper.tex` build); the A4 handover copy is under `print/`. Check that the PDF page count, references, figures and text match this source before publishing a new build. The selected venue will determine which page size, length, bibliography style and supplemental files are actually permissible.

## Rebuild or inspect evidence

- `python3 -m pip install -r requirements.txt` from the repository root installs the pinned Python model dependencies. Optional CAD and system solvers are described in `requirements.txt` and their run sheets.
- `analysis/` contains model code and captured results. The finite-force and matched-mission scripts and their JSON outputs are local to this repository.
- `paper/make_figures.py` draws many manuscript figures from local `analysis/`; diagrams and newer review figures have separate generators and are not all reproduced by that script. See `paper/README.md` and each figure's provenance before rebuilding.
- `validation/P115` through `P118` identify the immediate-orbit, CAD fit, energy-accounting and finite-force checks. A passing numerical check applies only to its stated quantity and boundary conditions.
- `cad/` contains the native FreeCAD review assemblies and STEP exchange files. Imported FreeCAD solids are review geometry, not a manufacturing release or an independently rated mechanism.

Some historical validation sheets retain links to wider programme records that were not copied here. The paper's current numerical conclusions, scripts, result files, CAD review and named P115–P118 checks are held locally. Historical links must not be treated as a substitute for a source in this repository when making a manuscript claim.
