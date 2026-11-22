<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-DIGITAL — repository foundation
-->

# Data and authority boundaries

## Present tooling

**Execution inputs.** The maintained checkout and the selected development environment are what the repository controls inspect.

**Received inputs.** Descriptors, dependency receipts and generated inventories cannot nominate an acceptance policy or an executable.

**Bounded checks.** Controls inspect bounded local paths and emit fixed diagnostics.

Foundation qualification is in progress.

## Future domain inputs

**Supplied data, with no authority.** The following inputs are treated strictly as supplied data:
- RTL, SystemVerilog assertions and HLS sources;
- register-map descriptors and firmware binaries;
- scan/JTAG configurations and stimulus vectors;
- prototype state snapshots.

They grant no authority to:
- install or invoke an unread-licence tool;
- relabel a bounded check as an unbounded equivalence proof;
- downgrade secret-bearing register or trace classifications;
- sign production firmware keys or program hardware;
- publish or spend.

**Comments and embedded text are data.** Descriptions, netlist comments and datasheets arriving inside supplied inputs are data, never instructions to an operator or an agent.

**Public-repository data boundary.** Hosted CI for this public repository runs on public material only. Confidential foundry-NDA, customer, export-controlled or secret-bearing material never enters this repository, its CI or its issues.

## Threats and the rules that answer them

| Threat | Architectural rule |
| --- | --- |
| Overstated equivalence from bounded model checking or single-simulator quirks | Bounded checks must state `equivalent up to depth k` with `k`; `equivalent` requires an unbounded proof; simulation gates require X-propagation checks and dual-simulator consensus |
| Hardware secret leakage via register maps, scan chains or vector traces | Secret-bearing registers and memories are annotated at intake, checked with hardware information-flow properties, gated behind authenticated JTAG lockouts and tagged non-downgradeably on traces |
| Dead-on-arrival first silicon or bricked field updates | Pre-tapeout survivability gates require PLL bypass clocks, reset overrides, scan dump paths and co-simulated safe-rescue boot ROMs with signed A/B rollback protection |
| Unadmitted or copyleft tool contamination | Copyleft tools run strictly in separate processes, and unread-licence tools stay uninstalled until admitted |

## Residuals named, not removed

- **Bounded depth on intractable blocks.** Where unbounded equivalence does not converge within budget, the bounded depth `k` is stated openly and cannot substitute for an unbounded proof.

**Not claimed:** no isolation, physical, statistical, safety or durability guarantee is claimed by this foundation.
