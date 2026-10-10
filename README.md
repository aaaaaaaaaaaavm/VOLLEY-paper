# VOLLEY Gen5 — paper and reproducibility package

### A system-level computational design study of a programmable electromagnetic CubeSat deployer

This repository is the **standalone companion** to an [IEEE-formatted manuscript](paper/VOLLEY_IEEE_Conference.pdf). It includes the manuscript source, cited local figures, CAD, analysis code and outputs, validation records, assumptions and known defects. A reader can evaluate the paper from this repository alone.

> **Publication state, October 2026:** The paper is **not submitted or peer reviewed**. No IEEE venue has been selected, so venue-specific page, abstract, reference and copyright requirements have not been checked. Gen5 is a controlled computational evaluation snapshot; Gen6 is future scaling research toward a 1 km/s-class objective. No VOLLEY hardware has been built, fired, measured, qualified or flown.

![Four-stage STEP-derived Blender storyboard of intended Gen5 storage, handoff, acceleration and departure](cad/renders/sequence/gen5_operations_hero.png)

*Conceptual motion from the local [FreeCAD-linked STEP review solids](cad/renders/sequence/README.md). The enclosure and near cassette shell are hidden. The evaluated reference placement has a known side-fed track/cassette clash; moving clearances, contact and brake behavior are unverified. [Watch the eight-second sequence](cad/renders/sequence/gen5_intended_sequence.mp4) · [view the static STEP audit](cad/renders/step_review/README.md). This is graphical orientation for the paper, not added performance evidence.*

<p align="center"><img src="cad/renders/sequence/gen5_intended_sequence.gif" alt="STEP-derived Gen5 intended-operations animation; not a mechanism validation" width="70%"></p>

> **Performance correction under review:** a finite-geometry analytic 3-D force integral finds **12.448 m/s only under ideal phase with circuit losses omitted**. This challenges the historical periodic-force shot result of **16.029 m/s**. The latter remains in the paper as a traceable model output, not an established machine capability. [Numerical run sheet](validation/P118_gen5_finite_force_map.md) · [affected-claim disposition](docs/GEN5_2026_10_09_FINDING_DISPOSITION.md).

An independent [2-D finite-element screen](validation/P119_gen5_finite_force_fem2d.md) reproduces the finite-array force decline with **1,081.6 J ideal in-plane work** on a 1 mm mesh; the analytic 3-D model gives 1,041.7 J. A [finite-force shot rerun](validation/P120_gen5_finite_coupled_shot.md) gives 12.448 m/s and 2.099 kJ gross draw under the historical bank and full-winding assumptions. A second [depth-resolved 3-D surface-charge implementation](validation/P121_gen5_finite_force_surface3d.md) independently recovers **1,041.7 J** under shared ideal assumptions. An [illustrative gap sweep](validation/P122_gen5_finite_force_sensitivity.md) gives **906.7 J at 14 mm**, 13.0% below the 12 mm case. Selected power hardware, contact and physical validation remain open.

> **Updated manuscript result, 10 October 2026:** [P123](validation/P123_gen5_one_event_mass_screen.md) re-solves the matched one-release reference with fuel sized for that event. Gen5 saves 1.866 kg of fuel when both options start with 10 kg, yet its modeled dry device is 54.562 kg heavier. The self-consistent one-event device-plus-fuel proxy is **52.717 kg worse** than the spring class. Parity at the *ideal* P118 speed would require about **52.630 kg less Gen5 device dry mass**. [Source](analysis/gen5_one_event_mass_screen.py) · [result JSON](analysis/results/gen5_one_event_mass_screen.json). This is an algebraic screen, not a twelve-shot, motor-rated or provider mission conclusion. The manuscript PDF now includes this limited result.

> **Architecture bound:** even a zero-burn release cannot lower Gen5 loaded fuel below the common 2 kg reserve. A Gen5 successor would need a device at or below **74.659 kg** to tie this one-event spring reference; the current model is 126.562 kg. [Recomputed bound](analysis/results/gen5_architecture_bounds.json) · [unselected H1 architecture hypothesis](docs/GEN5_H1_INTEGRATED_DEPLOYER_HYPOTHESIS.md). This is a necessary condition, not an achievable design.

> **New requirements screen, P124:** [reproducible orbit and stroke analysis](validation/P124_precision_delivery_design_space.md) translates explicit 450 km orbital-state tolerances to ideal tangential velocity margins and tests payload load against release speed. At 1.3 m usable stroke, 1 km/s implies about **39,220 g** for a 4 kg payload; it is not a credible first Gen6 3U prototype specification. The analysis does not demonstrate a VOLLEY command range or accuracy. [Code](analysis/precision_delivery_design_space.py) · [result](analysis/results/precision_delivery_design_space.json).

The [prototype-to-flight decision gates](docs/GEN6_PROTOTYPE_TO_FLIGHT_ROADMAP.md) show what evidence a real Gen6 instrumented article, engineering model, qualification candidate and eventual flight demonstration would each need. Those stages are proposed, not achieved.

![Ideal speed, stroke and payload-load screen](figures/precision_delivery_design_space.svg)

![P123 one-event installed device and fuel comparison](figures/gen5_one_event_installed_burden.svg)

<p align="center"><img src="figures/gen5_finite_force_surface3d.png" alt="Depth-resolved 3-D numerical force overlay" width="48%"> <img src="figures/gen5_finite_force_sensitivity.png" alt="Illustrative ideal-force geometry sensitivity" width="48%"></p>

*The 3-D formulations share geometry, remanence and ideal phase. The sensitivity cases are deterministic scenarios, not measured tolerances or statistical uncertainty.*

<p align="center"><img src="figures/gen5_finite_force_map.png" alt="Finite geometry force map" width="48%"> <img src="figures/matched_mission_reference.png" alt="Matched reference mission comparison" width="48%"></p>

*The mission comparison uses the same modeled host, payloads and delivery target for a spring class and two Gen5 model speeds. No sampled twelve-shot case closes. [Exact reference inputs](docs/MATCHED_MISSION_REFERENCE.md).*

<p align="center"><img src="figures/gen5_finite_force_fem2d.png" alt="Independent two-dimensional finite-element and analytic force comparison" width="48%"> <img src="figures/gen5_finite_coupled_shot.png" alt="Finite-force shot with assumed bank and inverter efficiency" width="48%"></p>

*Open-source solver and model outputs, not physical measurements. [P119](validation/P119_gen5_finite_force_fem2d.md) gives mesh and boundary checks; [P120](validation/P120_gen5_finite_coupled_shot.md) states the two copper-energization branches.*

<p align="center"><img src="paper/figures/V00_system_overview.svg" alt="Gen5 system architecture and mission concept" width="100%"></p>

*Architecture figure from this repository. Host operations and payload interface are conceptual and provider dependent.*

**Start here:** [Paper PDF](paper/VOLLEY_IEEE_Conference.pdf) · [LaTeX source](paper/paper.tex) · [Remaining CAD and IEEE work](IEEE_AND_CAD_REMAINING_WORK.md) · [IEEE prior-art update](IEEE_PRIOR_ART_UPDATE_2026-10-09.md) · [Claim audit](CLAIM_CORRECTIONS_2026-10-09.md) · [Computational review PDF](reports/GEN5_COMPUTATIONAL_REVIEW.pdf) · [FreeCAD/CAD review PDF](cad/GEN5_CAD_REVIEW.pdf) · [Artifact checksums](ARTIFACT_MANIFEST.sha256) · [Build notes](paper/README.md) · [Market and spacecraft fit](MARKET_AND_CUSTOMER_FIT.md) · [Claim provenance](PROVENANCE.md) · [Baseline](BASELINE.md) · [Validation register](validation/README.md)

## What the paper actually establishes

Gen5 models a magazine-fed, reusable-sled electromagnetic deployer for twelve unmodified 3U CubeSats on a host platform. The release station is 1.5 m from the breech on 1.8 m structural longerons; the powered stroke is 1.3 m. The design includes a double-sided Halbach linear motor, pulse-energy store and eddy-current sled arrest. A qualified host, complete release mechanism and flight interface have not been selected.

| Reported quantity | Gen5 result | How to read it |
|:--|--:|:--|
| Historical modeled 3U exit speed | **16.029 m/s** | Periodic model output contradicted by finite geometry; not a proven command envelope |
| Finite-force model screen | **12.448 m/s; 2.099 kJ gross** | Ideal phase and historical full-winding bank assumptions; not a rating |
| Modeled acceleration | **10.07 g** | Payload-specific structural compatibility unproven |
| Gross shot energy | **2.78 kJ** | Circuit and dynamics model of the historical shot |
| Dry / loaded mass | **126.6 / 174.6 kg** | Modeled rollup with a historical Gen3 sled solid-volume input and assumed components; installed host system not closed |
| Exit-speed dispersion | **0.0274 m/s (3σ)** | Closed-loop simulation with assumed sensor and uncertainty terms |
| 3U deployer mass per satellite | **10.547 kg** | Fails the stated roughly 2 kg/satellite economic criterion |
| Single-shot orbit case | **28.8 km** semi-major-axis rise; **1.60×** modeled lifetime | Stated 450 km, mean-activity case; lifetime result has not been independently rerun for that assumed historical input |
| Side-fed CAD reference fit | **11 mm width shortfall** | FreeCAD and CadQuery STEP intersection also finds 32,915 mm³ clash per cassette; feeder redesign needed |

See [baseline field names](BASELINE.md), [method limits](PROVENANCE.md), [decision gates and open problems](EVIDENCE_LIMITS.md). The approximately 6 kg/3U canister comparison is a separate incumbent-hardware parity test; it also fails (10.547/6 ≈ 1.76). These are two different decision boundaries.

<p align="center"><img src="figures/gen5_mass_decision.svg" alt="Gen5 mass per 3U compared with two distinct screens" width="49%"> <img src="figures/gen5_energy_accounting.svg" alt="Historical periodic-model shot energy accounting" width="49%"></p>

*Generated from this repository's [mass](analysis/results/mass_properties.json), [historical shot](analysis/results/motor_results.json) and [energy audit](analysis/results/rated_energy_mass_audit.json) outputs by the local [plot script](tools/plot_gen5_decision.py). Neither is a measurement. [P117](validation/P117_rated_energy_mass_audit.md) reconciles the old 124.488 J compact-output remainder to assumed converter loss, auxiliaries and a numerical step; actual power hardware remains unverified.*

<p align="center"><img src="figures/rated_orbit_crosscheck.svg" alt="Historical-input two-body orbit cross-check" width="49%"> <img src="figures/gen5_packaging_section.svg" alt="FreeCAD reference assembly packaging failure" width="34%"></p>

*The separate Cartesian calculation recovers **28.800775 km** of immediate axis rise; it does not verify lifetime. The side-fed [native FreeCAD project](cad/native/Gen5_Review.FCStd) and [assembly STEP](cad/step/gen5/VOLLEY_Review_Assembly_FreeCAD_Gen5.step) retain a measured track/cassette clash. [Orbit method](validation/P115_rated_orbit_cartesian.md) · [CAD report](cad/GEN5_CAD_REVIEW.pdf).*

![Unselected R1 feeder geometry](figures/gen5_feeder_candidate_r1.png)

<p align="center"><img src="cad/renders/step_review/gen5_fit_plan.jpg" alt="STEP-derived top view of Gen5 reference track and cassettes, enclosure and payloads hidden" width="49%"> <img src="cad/renders/step_review/r1_candidate_plan.jpg" alt="STEP-derived top view of the separate unselected R1 feeder candidate" width="49%"></p>

*Left: failed Gen5 reference placement. Right: separate R1 widened geometry candidate; its actuation and installed system remain open. [Exact-solid audit and render provenance](cad/renders/step_review/README.md).*

*The [R1 FreeCAD/STEP candidate](cad/FEEDER_CANDIDATE_R1.md) clears a scripted 3U envelope path in a widened enclosure. It has no lift actuator, launch retention, tolerance closure or revised installed budget, and is not the evaluated Gen5 baseline.*

<p align="center"><img src="paper/figures/A02_field_map.png" alt="Calculated Halbach field" width="32%"> <img src="paper/figures/F01_shot.png" alt="Modeled Gen5 shot" width="32%"> <img src="paper/figures/A35_ledger.png" alt="Requirement-attributed mass floor" width="32%"></p>

*Field → shot → mass floor. The numerical field cross-check applies to selected quantities, not to the entire machine. The mass-ledger result is a negative finding, not a design endorsement.*

## Evidence levels

| Level | Present evidence | Limit |
|:--|:--|:--|
| Model calculation | Shot, orbit, control, thermal, mass and CAD outputs in [analysis](analysis/) and [cad](cad/) | Depends on assumed inputs and geometry |
| Independent numerical cross-check | Selected field, circuit and orbital calculations in [validation](validation/) | Checks defined model aspects and cases only |
| External literature or products | [Prior art](PRIOR_ART.md), [literature](LITERATURE.md), bibliography in the manuscript | Supports comparison and assumptions; does not validate Gen5 hardware |
| Physical qualification | **None** | Release repeatability, loads, feeder, recoil, environmental and host acceptance remain open |

![Bounded two-payload timing screen](figures/manifest_timing.svg)

*The timing figure is a sampled mission study. Its 4.57 m/s best point is not an achieved launcher setting, a maximum speed or a full twelve-payload mission result.*

## Reproduce the published model point

```bash
python3 -m pip install -r requirements.txt
cd analysis
python3 verify_field.py
python3 mass_properties.py
python3 motor_model.py
python3 sizing.py
python3 payload_family.py
python3 astro.py
python3 comparators.py
python3 cost.py
```

Outputs are written under [analysis/results](analysis/results/). Run in the listed order because downstream analyses read the rated shot from `motor_results.json`. The cited artifact is the checked-in result set; dependency and solver availability may affect a new run. [Build both paper page sizes](paper/README.md) and [regenerate figures](paper/make_figures.py) from local sources.

Run `python3 tools/check_review_surface.py` for the repository's fast integrity gate: current local links, manuscript figures, key captured-result identities, artifact hashes and the compiled PDF. It does not independently validate electromagnetic thrust or certify a host interface. Some older, copied validation sheets contain programme-history links outside this companion; current manuscript claims must trace to local sources named above.

## Package map

| Path | Purpose |
|:--|:--|
| [paper/](paper/) | Authored LaTeX, figures and current Letter PDF |
| [print/](print/) | Current A4 and Letter handover PDFs |
| [analysis/](analysis/) | Executable models and captured JSON results |
| [validation/](validation/) | Predeclared run sheets, cross-checks and failures |
| [cad/](cad/) | Gen5 source parts, eight FreeCAD-exported STEP parts, native FCStd assembly, failure report and rendered views |
| [reports/](reports/) | Local seven-page computational evidence review and its source |
| [BASELINE.md](BASELINE.md), [PROVENANCE.md](PROVENANCE.md), [EVIDENCE_LIMITS.md](EVIDENCE_LIMITS.md) | Claim values, evidence classes and unresolved decisions |

The analysis and reference records began as a dated engineering snapshot and now include local P115/P116 checks and FreeCAD exports. This copy is the evidence package for the manuscript; later changes elsewhere do not silently change its claims. The manuscript and PDFs are authored here. Any future update requires rerunning the local checks and recording the changed sources. [VOLLEY engineering](https://github.com/aaaaaaaaaaaavm/VOLLEY), [college thesis](https://github.com/aaaaaaaaaaaavm/VOLLEY-thesis) and [research vault](https://github.com/aaaaaaaaaaaavm/VOLLEY-lab) provide optional programme context.
