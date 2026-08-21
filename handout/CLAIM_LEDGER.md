# Claim ledger for the printed pack

**Not printed.** This file is the audit trail for the three documents carried to Delhi, Noida and
Bangalore, prepared 2026-08-21. Every headline figure that appears in any of them is listed with
where it comes from and what class of evidence it is.

**Evidence classes**, from `VOLLEY/docs/FIGURE_INDEX.md`:

| | |
|---|---|
| **M** | model output — a script produced it |
| **X** | cross-checked — an independently implemented method reproduces it |
| **S** | schematic — a drawing, not a result |
| **A** | declared assumption — chosen, not derived, and labelled as chosen |
| **R** | **internal design requirement — a number this project set on itself.** Never an externally established capability, and never evidence that anything outside this project can meet it |
| **measured** | **zero members. Nothing in this project has been measured** |

**The pack:**

| File | What | Pages |
|---|---|---|
| `print/Adityavardhan_Mishra_VOLLEY_IEEE_2026_A4_Print.pdf` | **IEEEtran-formatted technical manuscript**, A4, the physical handover version | 18 |
| `print/Adityavardhan_Mishra_VOLLEY_IEEE_2026_Letter.pdf` | the same manuscript, US Letter, the canonical format | 18 |

**Both are IEEE-*formatted*, using the IEEEtran class. Neither is claimed to be submission-compliant for any particular venue** — page limits, abstract limits and formatting requirements are set by the conference or journal, and no venue has been selected.
| `handout/volley_brief.pdf` | one A4 sheet, printed double-sided | 2 |
| `handout/selected_work.pdf` | one A4 side | 1 |

The two manuscript builds are produced from one source: `paper_a4.tex` passes `a4paper` to
IEEEtran and then `\input`s `paper.tex` verbatim. **They cannot diverge in content.** Verified by
extracting both texts and comparing word streams: 13 657 tokens each, identical.

---

## Gen5 performance — the front of the brochure and the body of the paper

| Claim | Value | Gen | Class | Source | Status |
|---|---|:-:|:-:|---|---|
| Thrust constant | 10.54 N per kA/m | 5 | **X** | `motor_results.Kt_N_per_kA` | live |
| Force ripple | ±1.01 % | 5 | M | `motor_results.ripple_pct` | live |
| 2-D FEM agreement | 0.03 % | 5 | **X** | `validation/results/A1_femm.json`, `Kt_N_per_kA` 11.026 vs `Kt_reference` 11.03 | **corrected today** from 0.07 %, which predated the 2026-08-03 quadrature fix |
| 3-D FEM agreement | 0.059 % | 5 | **X** | `validation/fem3d/band4_result.json`, A2 band 4 | live. Tests the **field**, not the depth average |
| Exit velocity, 3U | 16.029 m/s | 5 | M | `motor_results.shot.v_exit` | live |
| Acceleration | **10.07 g for 162 ms** | 5 | M | `motor_results.shot.a_g` | live. **The model result. Unchanged by anything below** |
| Acceleration ceiling | **25 g** | 5 | **R** | `docs/VELOCITY_CEILING.md`, `cad/parameters.json` | **INTERNAL DESIGN REQUIREMENT.** Chosen by this project. Everything downstream — retention chain, cradle preload, abort logic, payload-family table, A27, A38, A63, A65 — is sized against it consistently. **It is not a CubeSat qualification limit and must never be quoted as one — P98** |
| CubeSat quasi-static qualification level | **none exists in this repository** | — | — | — | **The CubeSat Design Specification Rev. 14 publishes a mechanical interface and defers test levels to the launch provider; GEVS publishes a random-vibration spectrum. Neither gives a universal quasi-static level. The \"14 g quasi-static\" figure once cited here was 14.1 g rms with its units changed — P98, withdrawn** |
| Payload structural compatibility with a 10.07 g event | **not established** | 5 | — | — | **OPEN.** Depends on the spacecraft's own qualified load environment and on an integration review that has not been performed. **No payload has been mechanically qualified against this machine** |
| Velocity at the 25 g ceiling over the 1.30 m zone | 25.3 m/s | 5 | M | `docs/VELOCITY_CEILING.md` | live, **against the internal ceiling only** |
| Pulse duration | 162.3 ms | 5 | **X** | `motor_results.shot.t_ms`, ngspice agrees to 0.03 % | live |
| Peak current | 320 A | 5 | **X** | `motor_results.shot.I_peak` = 319.539 | live |
| Energy drawn, gross | 2782 J | 5 | M | `motor_results.shot.E_drawn` | live |
| Energy drawn, net | 2735 J | 5 | M | `motor_results.E_drawn_net_J` | live |
| Energy recovered | 47 J | 5 | M | `motor_results.regen.E_recovered` | **corrected today** from 291 J — **P97** |
| Electrical to payload | 18.8 % | 5 | M | `motor_results.eff_net_pct` = 18.79 | **corrected today** on three front-door pages that published 18.5 %, the gross figure |
| Dispersion, closed loop | 0.0274 m/s (3σ) | 5 | M | `motor_results.closed_loop_3sigma`, 800 runs | live |
| Apogee placement | ±0.10 km | 5 | M | `astro_results.apogee_placement_km` | live |
| Semi-major axis change | +28.8 km | 5 | **X** | `A21R`, GMAT-checked in A15 | live |
| Lifetime multiplier | ×1.60 at mean activity | 5 | **X** | `astro_results.lifetime.mean.multiplier` | live. **Not invariant — P16** |
| Lifetime extension vs a spring | +60.2 % vs +8.2 % | 5 | M | `comparators.lifetime_extensions` | live |
| Dry / loaded mass | 126.6 / 174.6 kg | 5 | M | `mass_properties.dry_kg`, `loaded_kg` | live since A46 |
| Deployer mass per 3U satellite | 10.55 kg | 5 | M | `payload_family` 3U `kg_per_satellite` | live |
| Track first mode | 109.0 Hz | 5 | M | `sizing.track_mode.fixed_fixed_Hz` | live |
| Recoil per shot | 64.1 N·s | 5 | M | `astro_results.recoil_Ns_per_shot` | live |
| Recurring hardware cost | ₹1,345,055 | 5 | **A** | `cost.total_INR` | **every price assumed. No vendor quotation exists for any line item (E16)** |

## Comparative claims — the back of the brochure

| Claim | Value | Class | Source | Status |
|---|---|:-:|---|---|
| Canisterised dispenser, per 3U slot | ~6.0 kg | **A** | published class figure, `comparators.kg_per_3U_dispenser` | no manufacturer named |
| **Mass ratio against it** | **1.758** | M | `comparators`, 10.55 / 6.0 | **A21 band 4 FAILS. Parity is withdrawn — P69** |
| Kill criterion 1 crossing | 5.3× on dry mass | M | `docs/KILL_CRITERIA.md` threat 1, against a **2 kg estimate** | crossed |
| Cold-gas module, on the satellite | 0.5–1.2 kg | **A** | published class range | no manufacturer named |
| **Loss to it at 3U** | **12.4×** | M | `comparators.coldgas_loss_ratio` at the 0.85 kg mid-class figure | **declared as a loss before the run** |
| Spring Δv | 1–2.5 m/s | **A** | published deployer interface documents | class figure |
| **Orbital effect of a spring impulse** | **real, and small: +8.2 % lifetime at 2.5 m/s** | M | `comparators.lifetime_extensions` | live. **A spring changes orbital energy. The defensible distinction is scale and commandability, not presence or absence — every document in the pack now says so** |
| Spring designed differential | exactly 0 | M | `comparators`, A21 band 3 | live, and categorical |
| Spring maturity | TRL 9, thousands deployed | **A** | published | live |
| VOLLEY maturity | TRL 2–3, nothing measured | — | `docs/BUILD_READINESS.md`, E4 | live |
| 30° of phase by release timing | 468 s at zero Δv | M | `comparators.release_timing.seconds_to_30deg_by_timing` = 467.93 | **A21-R. The phase claim is withdrawn — P56** |
| **What release timing changes** | **phase, and nothing else** | M | A21-R bands R5, R6 | live. Semi-major axis 0 m, lifetime ×1.0000 |
| **What a commanded impulse changes** | **orbital energy: +28.8 km of semi-major axis, ×1.60 lifetime** | **X** | A21-R, GMAT-checked in A15 | live. **This is a statement about what the deployment interface can command, not a claim that only Δv perturbs an orbit — drag, J₂ and SRP all do, and this work prices two of them.** The brochure's earlier *"only Δv changes an orbit"* is withdrawn as overbroad |
| Phase drift under a commanded split | 21.75 °/day, never stops | M | `comparators.release_timing.drift_deg_per_day_at_10_m_s` | live |
| Semi-major axis by timing | 0 m at any cadence | M | `comparators.release_timing.da_timed_m` | live |
| Host cost per 50 km shell | 27.8 m/s | M | A20 reachable envelope | live |
| Fleet altitude span at 100 m/s | 269 km | M | A20 | live |
| Plane change | 133 m/s per degree, excluded | M | `A15_caseB_plane_change.dv_per_degree_m_s` = 133.35 | live |

## Method-chain claims — the back of the brochure and the work sheet

| Claim | Value | Class | Source |
|---|---|:-:|---|
| Run sheets | 65, A1–A65 | — | `validation/`, one file each |
| Bands declared before the script | every one | — | provable per sheet: `git show --stat <band commit> -- <script>` returns nothing |
| Defect register | 133 entries, 53 live | — | `tools/register_status.py`, gate-checked |
| 2-D FEM mesh | 141 k elements | M | `A1_femm.mesh_elements` = 140 750 |
| 3-D FEM | 274 105 DoF, 315 370-node mesh | M | `validation/fem3d/` |
| CFD cell count | 581 779 | M | `validation/cfd/free_fine/constant/polyMesh` |
| Monte Carlo runs | 800 | M | `motor_model.closed_loop_mc()` |
| **Exit velocity history** | 20.37 → 16.388 → 16.029 m/s | M | P15 (CAD sled mass), then ADR-030 (depth-resolved K_t) |
| Parametric vs CAD sled | 4.86 → 9.445 kg | M | `mass_properties.sled_parametric_kg`, `sled_kg` |
| Depth-resolution cost | 4.42 % | **X** | A2 band 2 ratio 0.9558 |
| GMAT disagreement at low activity | 18 % against a 5 % band | **X** | A15, P16 |
| ngspice energy-closure gap | 86.6 J a shot | **X** | A8-R, P24. ESR loss computed at 85.5 J, agreeing to 98.7 % |
| Constraint-ledger corners | 64 | M | `constraint_ledger.corners`, 2⁶ |
| **Survives every deletion** | **88.67 kg — 70.06 % — 7.39 kg per satellite** | M | `constraint_ledger`, dry 126.56, best corner removes 37.89 kg | 
| Criterion it is measured against | 2 kg per satellite | **A** | `docs/KILL_CRITERIA.md`, **an estimate, and the file says so** |

## Context figures

| Claim | Value | Class | Source |
|---|---|:-:|---|
| Catalogued nanosatellites and CubeSats | more than 4 800, Jan 2026 | external | `\cite{nanosats}` in the manuscript |
| Of those, carrying propulsion | on the order of 222 | external | same |
| Prior electromagnetic CubeSat launch | ~20× the velocity, ~10³ g, armature on the payload | external | `\cite{feng2025}` |

**The brochure states the propulsion figure as the count, not as a percentage.** An earlier draft
said "roughly 94 %"; that number is not in any repository file and was removed rather than
sourced.

## Work-sheet claims

| Claim | Value | Source |
|---|---|---|
| BOLLEY candidate space | 2 856 declared, 77 clear every hard band | `bolley/README.md`, A8b |
| BOLLEY Gen1 failure | 66.7:1 copper-window deficit | `bolley/README.md` |
| Trade study, phase boundary | 468 s vs 1.38 days | `orbital-deployment-trade-study/README.md`, from VOLLEY P56 |
| Motor lab agreement | 16.024 vs 16.029 m/s, 0.005 inside a 0.01 band | `pulsed-linear-motor-design-lab/README.md` |
| Motor lab source check | closes at 12 mΩ, **fails at 116 mΩ** | same |
| Toolkit scope | consistency, not physics validation | `engineering-evidence-toolkit/README.md` |

---

## What the pack deliberately does not claim

1. **No measurement of anything.** The `measured` evidence class has zero members and every
   document says so on its own face.
2. **No cost superiority in either direction.** A21 band 7 required the comparison script to emit
   `NOT COMPUTED`, and it does.
3. **No mass parity.** Withdrawn — P69, and printed as a loss.
4. **No constellation-phasing advantage.** Withdrawn — P56, and printed as a loss.
5. **No lifetime-ratio invariance.** Withdrawn — P16.
6. **No inheritance.** Gen5 is the evidence; the current stage-integrated direction is marked on
   both the brochure and in the manuscript as carrying none of it.
7. **No affiliation.** No institution, agency, company or individual other than the author and his
   university appears anywhere in the pack, and the brochure says so in its status line.
8. **No payload qualification.** The pack no longer says "within standard qualification loads" or
   "inside its existing qualification envelope" anywhere. 25 g is labelled an internal design
   requirement; 10.07 g is labelled a design acceleration; compatibility is labelled open. **P98.**
9. **No claim that a spring does not change an orbit.** It does. The claim is about scale and
   commandability.
10. **No claim that only Δv changes an orbit.** Drag, J₂ and solar radiation pressure change orbital
    elements. The claim is that a clock changes phase and a commanded impulse changes orbital energy.
11. **No claim of conference compliance.** The manuscript is IEEE-formatted, not venue-verified.

## Verification performed 2026-08-21

| | |
|---|---|
| Page geometry | brochure 2 pages A4, work sheet 1 page A4, carry paper 17 pages A4, submission paper 17 pages Letter — `pdfinfo` |
| Fonts | all four PDFs: every font embedded, **zero Type 3 bitmap fonts** — `pdffonts`. The handout sources carry `beramono` for a Type 1 typewriter (the default `tt` embedded as a 600 dpi bitmap) and declare the `cmr` condensed shape before `roboto` loads, so the builds log **zero warnings of any kind** |
| Overfull lines | zero in all four documents |
| Withdrawn wording | *qualification envelope*, *standard qualification loads*, *CDS cap*, *not enough to change an orbit*, *too little to alter that orbit*, *only Δv changes an orbit* — **zero occurrences across all four rendered PDFs**. `42 g` survives twice, both inside the sentence that names the withdrawn derivation and immediately withdraws it |
| Undefined references | zero in both manuscript builds |
| Unreferenced figures | zero. `A02_field_map.png` and `A35_ledger.png` were orphans in `figures/` and are now placed with the text they support |
| QR codes | **decoded from the rendered PDF at 300 dpi with OpenCV `QRCodeDetector`**, not merely regenerated. Brochure page 2 → `https://github.com/aaaaaaaaaaaavm/VOLLEY`; work sheet → `https://github.com/aaaaaaaaaaaavm` |
| Every page | rendered to PNG and inspected |
| Qualification wording | swept for *qualification envelope*, *standard qualification loads*, *25 g cap*, *25--30 g*, *3σ*, *14.1 grms* across all four rendered PDFs; every survivor inspected in context |
| Grayscale | brochure rendered `-gray` and checked; the single accent survives as a distinguishable mid-grey |
