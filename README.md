# VOLLEY research manuscript

**VOLLEY: Design and Computational Evaluation of a Commanded Electromagnetic CubeSat Deployment Mechanism**

Adityavardhan Mishra and Pratham Chawla · Mechanical Engineering, Symbiosis Institute of Technology, Pune · Gen5 ACR1

VOLLEY evaluates commanded CubeSat release as an additional control variable for a manoeuvring host. The completed computational study integrates twelve-payload storage, a positive pallet handoff, finite electromagnetic force, source-limited acceleration, release and active carrier recovery in one controlled configuration.

Current academic files are the [ED1 citation-corrected editorial revision](current/academic/EDITORIAL_REVISION.json), dated 25 October 2026. The engineering argument and results are unchanged; the [original dated issue](archive/2026-10-24-acr1-original/README.md) preserves the original bytes.

**Read the nine-page IEEE-formatted manuscript:** [PDF](current/academic/paper/paper.pdf) · [LaTeX source](current/academic/paper/paper.tex) · [build instructions](current/REPRODUCE.md). The manuscript is unsubmitted and a venue has not been selected.

<p><a href="current/academic/assets/01_assembly_isometric.png"><img src="current/academic/assets/01_assembly_isometric.png" alt="ACR1 native-CAD-derived integrated assembly with two storage banks and a central reusable carrier" width="420"></a></p>

*Orienting CAD-derived Blender view · ACR1 home state. [Native/STEP source](current/cad/release/) · [visual source identities](docs/ACR1_VISUALS.json).*

| Research result | Source and data |
|---|---|
| Twelve 4 kg 3U surrogates; studied commanded release 1–3 m/s | [Controlled parameters](current/cad/PARAMETERS.json), [coupled source/shot model](current/analysis/coupled_shot.py), [sampled results](current/analysis/COUPLED_SHOT.json) |
| Eight native/STEP states and 154 accepted motion/refinement checks | [CAD inventory](current/cad/release/FINAL_CAD_MANIFEST.json), [motion evidence](current/cad/release/MOTION_VERIFICATION.json), [all eight local native/STEP states](current/cad/release/) |
| 149.557 kg represented dry CAD plus 7 kg electrical/control allowance | [Resource ledger](current/analysis/RESOURCE_LEDGER.json), [mass/CG/inertia](current/verification/MASS_CG_INERTIA_SUMMARY.json) |
| Approximately 1.328 N/A active force and 1.399 N/A including represented returns | [Finite motor](current/analysis/FINITE_MOTOR.json), [independent source-face calculation](current/analysis/SURFACE_CHARGE_CHECK.json), [actual-conductor-current comparison](current/analysis/CURRENT_FIELD_FORCE.json) |
| 24 nominal custody commands and 166 declared logic tests | [Executable interlocks](current/analysis/transfer_interlocks.py), [captured checks](current/analysis/TRANSFER_INTERLOCKS.json) |
| Matched twelve-release host-assisted campaigns | [Inputs/targets](current/mission/MISSION_INPUTS.json), [raw command histories](current/mission/release/), [results](current/mission/MISSION_RESULTS.csv), [native replay](current/mission/NATIVE_REPLAY_CHECKS.json) |

The numerical contribution is the integrated design reference and its source-linked evaluation. Source-face, actual-current, timestep and native orbital comparisons test different numerical approximations while retaining their stated shared assumptions. The mission comparison finds target-dependent outcomes: commanded deployment does not provide a universal propellant advantage. [Methods, quantitative results and boundaries](current/RESULTS.md) explain the supported conclusions.

<p><a href="current/academic/assets/MISSION_RESOURCES.png"><img src="current/academic/assets/MISSION_RESOURCES.png" alt="Same-input G5-MISSION-01 comparison: host fuel by tested target family and initial wet-mass allocation for Gen5 and spring deployment" width="760"></a></p>

*Computed result · G5-MISSION-01 · twelve 4 kg 3U payloads and common full-state targets. The ideal ground-pretrimmed spring comparator closes both synthetic families at the declared 1 N and 5 N host-authority gates; these preplanned cases establish no Gen5 propellant or initial wet-mass advantage. [Source table](current/mission/MISSION_RESULTS.csv) · [model boundary](current/academic/evidence/mission/MISSION_REPORT.md).*

The [supplementary chapter and figure map](current/ACADEMIC_MAP.md) connects each argument to local methods, data and figures. The closest [full-text prior-art comparison](current/academic/evidence/literature/FEEDER_FULL_TEXT_REVIEW_2026_10_19.md) distinguishes published laboratory observations from simulations. [Reproduce the local example](current/REPRODUCE.md) to run the actual logic, feeder-sizing and nominal 3 m/s shot source without another checkout.

The academic record also includes the [55-page report PDF](current/academic/GEN5_FINAL_YEAR_REPORT.pdf), [editable DOCX](current/academic/GEN5_FINAL_YEAR_REPORT.docx), [report source](current/academic/GEN5_FINAL_YEAR_REPORT.md), and [17-slide presentation PDF](current/presentation/VOLLEY_BTech_Presentation.pdf)/[PPTX](current/presentation/VOLLEY_BTech_Presentation.pptx), with [900-second speaker notes](current/presentation/SPEAKER_NOTES.md).

The geometry, source, structural and logic results establish the declared computational criteria. Physical hardware, payload-interface acceptance, environmental and flight qualification remain subsequent development. The [editorial checklist](current/SUBMISSION_CHECKLIST.md) records the external human-read, venue and academic-administration conditions. No individual research-contribution allocation is asserted.

All eight native/STEP/BOM states and the 60-member raw solver supplement are included in this checkout. [Local data and restoration](current/README.md) provide source identities and scratch extraction; the captured conductor solution arrays are also bundled.

[Reproduction and build](current/REPRODUCE.md) · [Scientific figure conventions](docs/FIGURE_STANDARD.md) · [Current verification](VALIDATION_CURRENT.json) · [Citation](CITATION.cff) · [Licensing](LICENSING.md) · [Dated development archive](archive/README.md) · [Release and errata policy](RELEASE_POLICY.md) · [Publication policy](PUBLICATION_POLICY.md)
