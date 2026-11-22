<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-DIGITAL — repository foundation
-->

# Roadmap

## Current foundation

**Being qualified:**
- repository identity and legal texts;
- architecture and governance;
- native documentation;
- dedicated validation tools.

**Domain capabilities and claims:** empty.

## Capability milestones

1. **The five v1 record schemas with golden fixtures** (`digital_operation`, `digital_result`, `scan_and_jtag_dft_manifest`, `io_vector_trace`, `firmware_and_boot_rom_binding`), enrolled with full quality gates.
2. **Deterministic `Yosys` / `SymbiYosys` / `Verilator` synthesis, X-propagation and proof-mode equivalence runners** on open designs.
3. **Scan/JTAG DFT, `autoMBIST` and dead-on-arrival survivability gate checks** plus boot-ROM co-simulation.
4. **Migration of generic AXI, FIFO and AER digital cores** from SC-NeuroCore under split gates.

**Enrolled with every implementation change:**
- strict native typing and linting;
- native documentation;
- meaningful statement and branch coverage;
- affected boundary tests and benchmarks.

**Requires its own evidence and explicit approval:**
- admitting any unread-licence tool;
- production firmware root-of-trust key signing;
- public activation and release.

No availability date is promised. No performance, yield or productivity gain is promised either.
