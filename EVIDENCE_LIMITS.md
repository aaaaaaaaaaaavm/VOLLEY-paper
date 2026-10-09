# Gen5 decision gates and evidence limits

This file is the paper companion's local route from a headline to its counterevidence. It summarizes the fixed Gen5 manuscript and copied analysis snapshot. It does not assert that later engineering work has closed these items.

| Gate | Current result | Primary local record |
|:--|:--|:--|
| About 2 kg of deployer per 3U customer | **Fail:** 126.6/12 = 10.55 kg | [Mass rollup](analysis/results/mass_properties.json), [manuscript payload-family section](paper/paper.tex) |
| Within 15% of an approximately 6 kg/3U spring canister | **Fail:** ratio 1.758, about 76% heavier | [Payload family](analysis/results/payload_family.json), [manuscript](paper/paper.tex) |
| Current-rated lifetime invariance across activity | **Fail / not established:** historical GMAT result varied beyond the declared band; current rated lifetime has not been independently rerun | [Provenance](PROVENANCE.md), [GMAT record](validation/gmat/README.md) |
| Selected-field numerical agreement | **Partial pass:** independent methods compare named field quantities; depth-integrated thrust lacks a full independent 3-D check | [Validation register](validation/README.md), [provenance](PROVENANCE.md) |
| Payload compatibility and release mechanics | **Open:** a modeled 10.07 g does not qualify a CubeSat; retention, contact, tip-off and repeated feeder operation need specific hardware and payload evidence | [Manuscript limitations](paper/paper.tex), [validation register](validation/README.md) |
| Host and mission utility | **Open:** no named provider ICD or demonstrated complete twelve-payload mission on a specific host | [Manuscript mission assumptions](paper/paper.tex), [provenance](PROVENANCE.md) |
| Gen6 1 km/s-class goal | **Future research:** no selected architecture, qualified payload class or computed complete system | [Manuscript future work](paper/paper.tex) |

The publication claim is a **completed computational evaluation of a fixed design**, including failed criteria. It is not physical verification or an assertion that Gen5 meets every objective. Prior published hardware and product data can bound assumptions and establish prior art; they do not count as tests of this machine.

Before submission to an IEEE venue, check its current scope, length, template, abstract, ethics, data/code, author and copyright rules, and revise the manuscript accordingly. No venue is selected or submission claimed in this snapshot.
