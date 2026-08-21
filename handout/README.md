# The printed pack

Three documents, prepared 2026-08-21, built from this repository and from the engineering record.

| | |
|---|---|
| `volley_brief.tex` → `volley_brief.pdf` | **one A4 sheet, printed double-sided.** What the project is, what Gen5 measures against, what the analysis changed, and the two comparisons it loses |
| `selected_work.tex` → `selected_work.pdf` | **one A4 side.** Five projects, one method |
| `../print/Adityavardhan_Mishra_VOLLEY_IEEE_2026_A4_Print.pdf` | the manuscript, A4, to carry |
| `../print/Adityavardhan_Mishra_VOLLEY_IEEE_2026_Letter.pdf` | the same manuscript, US Letter, the submission format |

**[`CLAIM_LEDGER.md`](CLAIM_LEDGER.md) is not printed.** It lists every headline figure in all
three documents with its source file, its evidence class and its register status. Read it before
changing a number on either sheet.

## Building

```
pdflatex volley_brief.tex        # 1 pass; no references to settle
pdflatex selected_work.tex
```

Needs `roboto`, `lmodern`, `tcolorbox`, `tikz`, `qrcode`, `tfrupee`, `microtype`.
**`lmodern` is not decoration** — without it `\texttt` falls back to a 600 dpi bitmap PK font and
the PDF carries Type 3 text.

The QR codes are vector, drawn by `qrcode.sty`. There is no image dependency and no external
service. **Verify them by decoding the rendered PDF, not by trusting the source string**:

```
pdftoppm -png -r 300 volley_brief.pdf /tmp/q
python3 -c "import cv2;print(cv2.QRCodeDetector().detectAndDecodeMulti(cv2.imread('/tmp/q-2.png'))[1])"
```

## The images

`img/` holds copies. `hero.png` is `VOLLEY/cad/renders/gen5/three_quarter.png`; `ledger.png` and
`field.png` are `VOLLEY/figures/A35_ledger.png` and `A02_field_map.png`. They are copies rather
than links because this repository is the manuscript's home and the flagship is the record's; if a
figure is regenerated there, copy it here again.

## The rules these sheets are held to

1. **No number that is not already in a repository file.** Where the brochure needed one that was
   not — a percentage of catalogued CubeSats carrying propulsion — it was removed rather than
   estimated, and the underlying count is printed instead.
2. **Simulation is never described as a test.** Model-to-model agreement between two solvers is
   named as a consistency check on both sheets.
3. **Losses are printed at the same size as wins.** Two of the three commercially decisive rows in
   the comparison table are losses.
4. **Gen5 does not lend its evidence forward.** The current stage-integrated direction is marked
   on the brochure as carrying none of it.
5. **No affiliation is claimed.** No institution, agency, company or person other than the author
   and his university appears in either sheet.
