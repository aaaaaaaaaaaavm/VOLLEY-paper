# Licensing

**Two different things live in this repository and they are not licensed identically.**

| | Licence |
|---|---|
| **The reproducibility payload** — `analysis/`, `validation/`, `paper/figures/`, `BASELINE.md`, `PROVENANCE.md`, and everything generated from the flagship | **CC BY 4.0.** Full text in [`LICENSE`](LICENSE), attribution form in [`NOTICE`](NOTICE) |
| **The manuscript** — `paper/paper.tex`, `paper/IEEEtran.cls`, the compiled PDFs, `paper/archive/`, `paper/cv/`, `handout/` and `print/` | **CC BY 4.0 today, and that position is provisional** — see below |

## Why the manuscript is held separately

**A `.tex` file is not a derived artefact.** It is written, revised, submitted, reviewed and
revised again, and it acquires a copyright status of its own. **If the manuscript is accepted for
publication, an IEEE copyright transfer would supersede this licence for the accepted version.**
This repository cannot license rights it has transferred.

That is why [ADR-028](https://github.com/aaaaaaaaaaaavm/VOLLEY/blob/main/docs/adr/028-no-latex-in-the-flagship.md)
moved the manuscript out of the flagship in the first place: *"a file the flagship cannot license
is not a file the flagship should own."* **The payload the manuscript draws on stays CC BY 4.0
regardless of what happens to the manuscript itself**, which is the part that matters for anyone
reproducing the numbers.

**Nothing has been submitted to any venue**, so nothing has been transferred.

## The MIT licence this repository used to carry

**Corrected 2026-08-22.** The root of this repository carried an **MIT** licence file while
[`paper/README.md`](paper/README.md) described the contents as CC BY 4.0 and linked a
`LICENSING.md` that did not exist. **The MIT file was a leftover**: the flagship and every other
companion moved to CC BY 4.0 and this repository's root file was not moved with them.

**The MIT text is retained at [`LICENSE-MIT-superseded`](LICENSE-MIT-superseded)** and this change
is **not retroactive** — clones, forks, archives and every commit reachable before it remain
available under the licence they carried at the time. Nothing here revokes rights already granted.

## The other repositories

| | |
|---|---|
| [VOLLEY](https://github.com/aaaaaaaaaaaavm/VOLLEY) (flagship) | CC BY 4.0 |
| [VOLLEY-thesis](https://github.com/aaaaaaaaaaaavm/VOLLEY-thesis) | CC BY 4.0, with the same manuscript hold |
| [VOLLEY-lab](https://github.com/aaaaaaaaaaaavm/VOLLEY-lab) | CC BY 4.0 |
| [orbital-deployment-trade-study](https://github.com/aaaaaaaaaaaavm/orbital-deployment-trade-study) · [pulsed-linear-motor-design-lab](https://github.com/aaaaaaaaaaaavm/pulsed-linear-motor-design-lab) | CC BY 4.0 |
| [engineering-evidence-toolkit](https://github.com/aaaaaaaaaaaavm/engineering-evidence-toolkit) | Apache 2.0 — it is a tool meant to be depended on, not a document |
