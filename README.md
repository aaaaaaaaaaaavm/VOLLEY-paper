> ## Generated repository, do not edit here
>
> Every file in this repository is generated from the **VOLLEY flagship** by
> `tools/export_companion.py`. Nothing here is authored, and any edit made here will be
> destroyed the next time it is regenerated.
>
> **Source:** [aaaaaaaaaaaavm/EMOCD](https://github.com/aaaaaaaaaaaavm/EMOCD) at commit `7648506`
> **Found a mistake?** Fix it in the flagship. This repository will pick it up.
>
> The flagship is the authoritative engineering record. Where this repository and the
> flagship disagree, the flagship is right and this copy is stale.

<!-- PROGRAMME-HEADER-START -->
| Repository | Role | You are here |
|---|---|---|
| [VOLLEY](https://github.com/aaaaaaaaaaaavm/VOLLEY) | Flagship: the authoritative engineering record, and the portfolio |  |
| **[EMOCD-paper](https://github.com/aaaaaaaaaaaavm/EMOCD-paper)** | IEEE companion: manuscript and reproducibility package *(generated)* | ← |
| [EMOCD-thesis](https://github.com/aaaaaaaaaaaavm/EMOCD-thesis) | Thesis companion: university submission *(generated)* |  |
| [EMOCD-lab](https://github.com/aaaaaaaaaaaavm/EMOCD-lab) | Phase II: research, redesign, deliberately unstable |  |
<!-- PROGRAMME-HEADER-END -->

---

# VOLLEY: IEEE companion

Everything needed to reproduce the conference paper. Manuscript source, figures, the analysis
scripts behind every number in it, the validation run sheets, and the literature record.

**[Read the paper](paper/VOLLEY_IEEE_Conference.pdf)** (11 pages)

## Reproduce it in one command

```bash
pip install -r requirements.txt
cd analysis && python3 verify_field.py && python3 mass_properties.py \
  && python3 motor_model.py && python3 sizing.py && python3 astro.py && python3 cost.py
```

Roughly two minutes. Results land in `analysis/results/*.json`.

This has been checked from a clean clone rather than assumed: run that way, `motor_results.json`
returns `shot.v_exit = 16.537`, which is the figure the paper's abstract quotes.

## What reproduces, and how well

| Quantity | Value | Cross-checked against |
|---|---|---|
| Thrust constant | 11.22 N per kA/m | A meshed magnetostatic FEM, agreeing to 0.07 % |
| Airgap field | 0.694 T midgap peak | magpylib, agreeing to three digits |
| Orbital decay | x1.62 lifetime | Cowell RK4, agreeing to 99.4 % |
| Exit velocity | 16.537 m/s at 10.7 g | Single-sourced |
| Dispersion | 0.027 m/s, 3 sigma | Single-sourced, and resting on assumed sensor noise |

The last two have no independent check. `PROVENANCE.md` says which of these carry weight.

## Figures

`python3 paper/make_figures.py` regenerates all of them. It imports the analysis rather than
reimplementing it, so a figure cannot quietly disagree with the number it plots.

## Before citing

**Read [`PROVENANCE.md`](PROVENANCE.md).** This is a design study at TRL 2-3. Nothing has been
built, fired or measured, and the paper says so.

[`PRIOR_ART.md`](PRIOR_ART.md) records the published work nearest to this one, including two
claims the paper had to retract after reading it. [`LITERATURE.md`](LITERATURE.md) maps the wider
field.

## What is deliberately absent

The engineering record. Decision log, defect ledger, CAD generations, roadmap and change history
live in the flagship. This package exists so the paper can be checked, not so it can stand in for
the repository it came from.
