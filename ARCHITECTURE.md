<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-DIGITAL — repository foundation
-->

# Architecture

## Current executable surface

The checkout contains:
- repository validation tooling;
- dedicated tests;
- workflow definitions;
- native documentation.

No domain component of Circuit Digital is implemented yet. The metadata keeps domain capabilities, claims and qualified record formats empty.

## Intended data flow

1. **RTL, HLS and survivability elaboration** take a pinned design view, system budget and technology leaf map, enforcing bypass clocks, reset overrides, scan dump hooks and secret-register annotations.
2. **Verification and synthesis** run dual-simulator consensus (`Verilator` X-propagation plus independent event simulation), hardware information-flow and property checks (`CellIFT`, `DifuzzRTL`, `SymbiYosys`) and synthesis, recording the exact formal proof mode.
3. **Boot-ROM and firmware co-verification** bind signed boot/rescue images and errata workarounds against the exact RTL register-map digest.
4. **Snapshot replay and engineering-change fixes** replay captured prototype snapshots in RTL simulation and validate metal-fix or respin netlists from corrective-action records.

## Ownership

**This project owns** the planned Circuit Digital records and boundary rules.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| contracts, admission and approvals | Circuit Core |
| process profiles and leaf-cell maps | Circuit Technology |
| FPGA conversion, partitioning and board runs | Circuit Prototyping |
| place-and-route, static timing and DRC/LVS | Circuit Physical |
| sign-off verdicts | Circuit Acceptance |
| signed deployment packaging | Deploy Pack |

## Interpretation

- **Bounded proofs.** `equivalent up to depth k` proves nothing beyond cycle `k`.
- **Pre-layout gates.** Post-synthesis gate counts and timing estimates are not post-layout sign-off.

Read [the documentation architecture](docs/ARCHITECTURE.md) for the planned records, domain rules and schema identifiers.
