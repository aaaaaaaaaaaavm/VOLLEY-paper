# Evaluated configuration and claim boundary

**Gen5 is the fixed computational configuration evaluated in the manuscript.** This page summarizes the numerical case and its limits; the editable [paper](paper/paper.tex), [report](reports/GEN5_COMPUTATIONAL_REVIEW.md), [CAD audit](cad/GEN5_FULL_INTERFERENCE_AUDIT_2026_10_12.md) and named validation sheets provide the evidence. There is no rated production or flight baseline.

| Quantity | Evaluated result | Status and source |
|:--|--:|:--|
| Manifest and class | Twelve nominal 3U spacecraft | Conceptual Gen5 layout; no approved payload ICD or working feed. [CAD review](cad/README.md) |
| Historical modeled exit speed | 16.029 m/s | Periodic-force shot prediction, challenged by finite geometry. [P118](validation/P118_gen5_finite_force_map.md) |
| Finite-force ideal speed | 12.448 m/s | Geometry-only screen with ideal phase; winding, switching and source are unselected. [P118](validation/P118_gen5_finite_force_map.md) · [P125](validation/P125_gen5_voltage_limited_screen.md) |
| Ideal electromagnetic work | 1.042 kJ | Separate 3-D surface-charge formulation agrees under shared assumptions; 2-D FEM gives 1.082 kJ in its plane. [P119](validation/P119_gen5_finite_force_fem2d.md) · [P121](validation/P121_gen5_finite_force_surface3d.md) |
| Modeled device dry mass | 126.562 kg | Rollup includes assumed and inherited component values; no complete installed CAD mass extraction. [P123](validation/P123_gen5_one_event_mass_screen.md) |
| Device mass per carried 3U | 10.547 kg | Fails internal 2 kg screen and roughly 6 kg canister comparator. [P123](validation/P123_gen5_one_event_mass_screen.md) |
| Side-fed enclosure deficit | 11 mm | 526 mm available versus 537 mm track plus cassettes. [P116](validation/P116_gen5_assembly_packaging.md) |
| Whole-assembly intersections | 17 pairs | Includes sled/track (82,983 mm³) and sled/stator (6,300 mm³). Widened R1 retains five pairs. [Exact-solid audit](cad/GEN5_FULL_INTERFERENCE_AUDIT_2026_10_12.md) |
| Historical-input immediate orbital rise | 28.800775 km | Independent two-body check of an **assumed** 16.029 m/s impulse, not demonstrated release. [P115](validation/P115_rated_orbit_cartesian.md) |

The one-event installed device-plus-resized-fuel proxy is 52.717 kg worse than the spring reference under the declared inputs. No sampled twelve-shot matched campaign closes. These are conditional study outcomes, not a supplier quotation or general proof that commanded delivery has no value.

A separate Gen6 research programme investigates mixed passive 1U/3U delivery from a generic maneuvering host. The [mission and article requirements](docs/GEN6_G0_MISSION_AND_ARTICLE_REQUIREMENTS.md) define its surrogate inputs. [R1](cad/gen6_integration_r1/README.md) and [R2](cad/gen6_integration_r2/README.md) are unselected one-cell CAD studies; neither changes the Gen5 result. The proposed 3–6 m/s first-article measurement band and 1 km/s long-range objective are unachieved targets.

The paper is IEEE-formatted and unsubmitted. A final academic freeze requires a selected venue or college format as applicable, a full claim-to-artifact check, a reproducible package and explicit exceptions. No hardware has been built, measured, qualified or flown.
