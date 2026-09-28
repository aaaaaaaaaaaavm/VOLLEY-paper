> **Programme status, 2026-09-28:** Gen6 is in development. No architecture or speed envelope is selected or validated. The independent spring-cell bank and the historical gas guide are unselected studies. This manuscript reports the older Gen5 model; it must not be read as a physical test or a current design specification.

> ## What is generated here, and what is not
>
> **Generated** from [aaaaaaaaaaaavm/VOLLEY](https://github.com/aaaaaaaaaaaavm/VOLLEY) at commit
> `06ebd07` by `tools/export_companion.py`: the analysis scripts and their results, the
> validation run sheets, the figures, and the reference records. Any edit to those is
> destroyed on the next export. **Fix them in VOLLEY and this repository picks the fix up.**
>
> **Authored here, and never overwritten:** the manuscript, its class file, the built PDF, the CV and the submission archive, all under `paper/`. VOLLEY is an engineering
> record and holds no manuscript source.
>
> Where a generated file disagrees with VOLLEY, VOLLEY is right and this copy is stale.
>
> **This repository may be improved until the work is published, and freezes at that
> moment.** What enters it has to be stable, effective and reliable against the problem
> statement -- not merely newer.

Live programme studies at this export: [sequential campaign allocation](https://github.com/aaaaaaaaaaaavm/VOLLEY/blob/06ebd07/docs/CAMPAIGN_ALLOCATION.md)
and [architecture decision gates](https://github.com/aaaaaaaaaaaavm/VOLLEY/blob/06ebd07/docs/PROGRAMME_EXECUTION.md).
[Terminal-state timing](https://github.com/aaaaaaaaaaaavm/VOLLEY/blob/06ebd07/docs/TERMINAL_TIMING.md)
extends the single-payload benchmark. These studies extend the engineering record;
the authored manuscript remains Gen5.

The latest [review and restart record](https://github.com/aaaaaaaaaaaavm/VOLLEY/blob/06ebd07/docs/REVIEW_20260916.md)
adds combined conditional release-error corners, reference-cell mechanics and the verification matrix.
These bounded calculations do not close the full campaign or select flight hardware.

<!-- PROGRAMME-HEADER-START -->
| Repository | Role | You are here |
|---|---|---|
| [VOLLEY](https://github.com/aaaaaaaaaaaavm/VOLLEY) | Main: the authoritative engineering record. Improved continuously |  |
| **[VOLLEY-paper](https://github.com/aaaaaaaaaaaavm/VOLLEY-paper)** | The concept at its most reliable, as an IEEE-formatted manuscript. **Frozen when published** | ← |
| [VOLLEY-thesis](https://github.com/aaaaaaaaaaaavm/VOLLEY-thesis) | The same concept as a full submission. **Frozen when presented** |  |
| [VOLLEY-lab](https://github.com/aaaaaaaaaaaavm/VOLLEY-lab) | The vault: ideas that never became a complete thing, and why each stopped |  |
<!-- PROGRAMME-HEADER-END -->

---

# VOLLEY: the manuscript

An IEEE-formatted technical manuscript, and everything needed to check it.

<p align="center"><img src="paper/figures/V00_system_overview.svg" alt="VOLLEY mission chain and the evidence boundary between Gen5 and historical study" width="100%"></p>

<p align="center"><sub>The manuscript reports the historical Gen5 model. Later architecture studies remain unselected and have a different evidence base.</sub></p>

<p align="center">
  <img src="paper/figures/A02_field_map.png" alt="Depth-resolved Halbach airgap field" width="32%">
  <img src="paper/figures/F01_shot.png" alt="Gen5 force, velocity and current through the modelled shot" width="32%">
  <img src="paper/figures/A35_ledger.png" alt="Requirement-attributed mass and the 64-corner mass floor" width="32%">
</p>

<p align="center"><sub>Field assumption → modelled shot → architecture verdict. The manuscript's
visual spine is generated from the same analysis files as its tables.</sub></p>

Rideshare CubeSats inherit the orbit of whoever paid for the launch. This paper models a
deployer intended to give twelve satellites individually selected release conditions without
modifying them, and reports thresholds the model fails. No mission benefit is physically verified.

## What the manuscript's machine is for

VOLLEY is a last-mile orbital delivery programme. After the primary spacecraft separates, the
launch vehicle's final stage can, where host capability and mission rules permit, continue as a
temporary controlled orbital delivery platform. The host performs the coarse orbital
repositioning; VOLLEY produces the fine, individually commanded release condition for each
secondary satellite.

The machine reported here is Gen5: the *self-contained* electromagnetic implementation of that
mission, its own track, drive, sled, energy store, brake and magazine, operating aboard the
platform. Host repositioning is treated parametrically throughout, because no launch provider
has supplied stage propulsion or control-authority data.

> The programme has since studied other mechanisms, but none is selected. The separate spring-cell
> bank and the approximately 8 m gas guide are historical comparisons. Neither inherits Gen5's
> evidence. The manuscript is retained as a dated model study.

[Read the paper](paper/VOLLEY_IEEE_Conference.pdf), 18 pages, current build.
Print-ready copies: [A4](print/Adityavardhan_Mishra_VOLLEY_IEEE_2026_A4_Print.pdf) ·
[US Letter](print/Adityavardhan_Mishra_VOLLEY_IEEE_2026_Letter.pdf). Both come from one source
and are content-identical; only the page geometry differs.

> It is IEEE-*formatted*, using the IEEEtran class. It is not claimed to be submission-compliant
> for any venue, page and abstract limits are set by the conference or journal, and no venue
> has been selected and nothing has been submitted.

Every number in it comes from a script in this repository, and every analysis behind it declared
what would count as failure before it ran. Nothing has been built, fired or measured.

## Reproduce it in one command

```bash
pip install -r requirements.txt
cd analysis && python3 verify_field.py && python3 mass_properties.py \
  && python3 motor_model.py && python3 sizing.py && python3 payload_family.py \
  && python3 astro.py && python3 comparators.py && python3 cost.py
```

Roughly two minutes, and the order matters: everything downstream reads the rated shot from
`motor_results.json` rather than restating it. Results land in `analysis/results/*.json`.

This has been checked from a clean clone rather than assumed: run that way, `motor_results.json`
returns `shot.v_exit = 16.029`, which is the figure the paper's abstract quotes.

## What reproduces, and how well

| Quantity | Value | Cross-checked against |
|---|---|---|
| Thrust constant, depth-resolved | 10.54 N per kA/m | Nothing independent. The FEM check below is of the centre-plane value it derives from |
| Thrust constant, centre-plane | 11.03 N per kA/m | A meshed 2-D magnetostatic FEM, agreeing to 0.03 % |
| Airgap field | 0.694 T midgap peak | magpylib, agreeing to three digits |
| Orbital decay | x1.60 lifetime | Cowell RK4, agreeing to 99.4 % |
| Exit velocity | 16.029 m/s at 10.07 g | Single-sourced |
| Dispersion | 0.0274 m/s, 3 sigma | Single-sourced, and resting on assumed sensor noise |

Only two rows carry an independent check. `PROVENANCE.md` says which of these carry weight.

## Figures

`python3 paper/make_figures.py` regenerates all of them. It imports the analysis rather than
reimplementing it, so a figure cannot quietly disagree with the number it plots.

## Before citing

Read [`PROVENANCE.md`](PROVENANCE.md). This is a design study at TRL 2-3. Nothing has been
built, fired or measured, and the paper says so.

[`PRIOR_ART.md`](PRIOR_ART.md) records the published work nearest to this one, including two
claims the paper had to retract after reading it. [`LITERATURE.md`](LITERATURE.md) maps the wider
field.


## The manuscript describes Gen5; the next architecture is open

This is deliberate and worth stating plainly. The authored manuscript describes Gen5, the
analysed baseline -- a frozen computational one, with no hardware behind it -- and the record of
what one self-contained deployer model costs. The long gas guide and compact independent spring
cells were later investigated and remain unselected comparators. The best sampled two-payload
campaign cannot select a product mechanism or speed ceiling; the later twelve-payload screens did
not complete a full manifest. The next design must restore the reusable shared path and loading
objective, then be compared under complete installed and mission accounting.

No performance has been physically measured, and no launch provider has supplied an accommodation.
The manuscript retains Gen5 as a historical computational case, not a current product specification.

The main repository retains these studies and their recorded failures.

## What is deliberately absent

The engineering record. Decision log, defect ledger, CAD generations, roadmap and change history
live in the flagship. This package exists so the paper can be checked, not so it can stand in for
the repository it came from.
