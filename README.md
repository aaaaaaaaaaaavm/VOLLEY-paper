> ## Generated repository — do not edit here
>
> Every file in this repository is generated from the **EMOCD flagship** by
> `tools/export_companion.py`. Nothing here is authored, and any edit made here will be
> destroyed the next time it is regenerated.
>
> **Source:** [aaaaaaaaaaaavm/EMOCD](https://github.com/aaaaaaaaaaaavm/EMOCD) at commit `c927df9`
> **Found a mistake?** Fix it in the flagship. This repository will pick it up.
>
> The flagship is the authoritative engineering record. Where this repository and the
> flagship disagree, the flagship is right and this copy is stale.

<!-- PROGRAMME-HEADER-START -->
| Repository | Role | You are here |
|---|---|---|
| [EMOCD](https://github.com/aaaaaaaaaaaavm/EMOCD) | Flagship — authoritative engineering record, portfolio |  |
| **[EMOCD-paper](https://github.com/aaaaaaaaaaaavm/EMOCD-paper)** | IEEE companion — manuscript and reproducibility package *(generated)* | ← |
| [EMOCD-thesis](https://github.com/aaaaaaaaaaaavm/EMOCD-thesis) | Thesis companion — university submission *(generated)* |  |
| [EMOCD-lab](https://github.com/aaaaaaaaaaaavm/EMOCD-lab) | Phase II — research, redesign, deliberately unstable |  |
<!-- PROGRAMME-HEADER-END -->

---

# EMOCD — IEEE companion

Reproducibility package for the EMOCD conference paper: manuscript source, figures, the
analysis scripts that produce every number in it, and the validation run sheets.

## Reproducing the paper's numbers

```bash
pip install -r requirements.txt
cd analysis
python3 verify_field.py && python3 mass_properties.py && python3 motor_model.py \
  && python3 sizing.py && python3 astro.py && python3 cost.py
```

Results land in `analysis/results/*.json`. Every figure regenerates with
`python3 paper/make_figures.py`, which imports the analysis rather than reimplementing it.

## What is not here

The engineering record — decision log, defect ledger, CAD generations, roadmap — lives in the
flagship. This package exists so a reader can reproduce the paper, not so it can replace the
repository the paper came from.

**Read [`PROVENANCE.md`](PROVENANCE.md) before citing anything.** This is a design study at
TRL 2–3 with no hardware, no measurement and no third-party review.
