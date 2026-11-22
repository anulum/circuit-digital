<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-DIGITAL — repository foundation
-->

# Decision: unify deterministic RTL, formal proof modes, DFT survivability and firmware binding in Circuit Digital

## Context

First-silicon bring-up fails as often from unverified boot ROMs, missing PLL/reset bypasses or scan lockout bugs as from logic synthesis errors, while bounded formal checks are easily misread as full proofs.

## Decision

**What Circuit Digital owns:**
- digital operation;
- digital result;
- scan and jtag dft manifest;
- digital i/o vector trace;
- firmware and boot-rom binding;

**What it imports:** only Circuit Core and Circuit Technology.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| contracts, admission and approvals | Circuit Core |
| process profiles and leaf-cell maps | Circuit Technology |
| FPGA conversion, partitioning and board runs | Circuit Prototyping |
| place-and-route, static timing and DRC/LVS | Circuit Physical |
| sign-off verdicts | Circuit Acceptance |
| signed deployment packaging | Deploy Pack |

## Consequences

**What can be qualified now:** repository governance and validation tooling, before domain code exists.

**What it cannot qualify:** unimplemented schemas, solvers, hardware or sign-off verdicts.

**Architectural consequences:**
- Circuit Digital owns RTL/HLS operations, proof-mode-qualified formal results, scan/JTAG survivability manifests, reference vector traces and boot-ROM/firmware bindings together;
- every operation runs deterministically without AI on open toolchains (`Yosys`, `SymbiYosys`, `Verilator`, `XLS`, `CIRCT`);
- physical place-and-route and FPGA board conversion stay separated in Circuit Physical and Circuit Prototyping.
