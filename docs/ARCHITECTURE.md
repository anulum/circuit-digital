<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-DIGITAL — repository foundation
-->

# Repository architecture

## Current executable tooling

**What it contains:** the repository's metadata, source-provenance, workflow, dependency-alignment, documentation, inventory and preflight controls.

**What each control does:** it inspects its fixed, declared local scope.

**What received metadata cannot do:** select another acceptance policy or grant domain authority.

Foundation qualification is in progress.

## Intended domain boundaries

| Record | Responsibility | Required evidence |
| --- | --- | --- |
| Digital operation | Pinned RTL/HLS operation request, target leaf-cell binding map, clock/reset constraints, secret-bearing register/memory annotations and formal or simulation obligations | Immutable design-view digests and explicit classification of secret-bearing storage elements |
| Digital result | Synthesis netlist, area/gate metrics, dual-simulator X-propagation verdicts, hardware security results and formal-equivalence verdicts with explicit proof mode | `equivalent` strictly for unbounded `k`-induction or property-directed reachability proofs; `equivalent up to depth k` naming `k` for bounded proofs; `not equivalent` with counterexample trace |
| Scan and JTAG DFT manifest | Scan-chain topology, built-in memory self-test (`autoMBIST`), authenticated debug lockouts and first-silicon dead-on-arrival survivability hooks (`pll_bypass_clk`, `por_override_n`, `TCK` scan dump, observation multiplexers) | Verified bypass and debug lockout isolation before physical layout or manufacturing test generation |
| Digital I/O vector trace | Cycle-accurate stimulus and reference response vectors produced by reference simulation of a pinned design view | Non-downgradeable secret-bearing tags when stimulus touches protected keys, and pre-run digest binding for prototype or tester comparison |
| Firmware and boot-ROM binding | Safe-rescue boot ROM image, post-silicon errata workarounds, register-map digests and hardware-root-of-trust signed A/B field-update bundles | Boot and power-on self-test co-simulation against RTL plus monotonic security-version signing provenance |

## Proof modes and tool-licence classes

- **Formal equivalence proof modes and mutation adequacy.** Every equivalence check states one of three verdicts verbatim: `equivalent` only after an unbounded `k`-induction or property-directed reachability proof; `equivalent up to depth k` naming the exact bound `k`; or `not equivalent` with a reproducible counterexample trace. Where a simulation or property test bundle claims mutation or fault adequacy, it reports its score with a one-sided lower confidence bound for a declared mix of mutation or fault operators, measured on a separate seeded set after the test bundle is frozen; its claim covers that declared mix only.
- **Licence isolation.** Permissive tools (`Yosys` ISC, `XLS` and `CIRCT` Apache-2.0) run under admitted profiles; copyleft tools and standalone simulators run in separate processes; proprietary vendor tools run in separate processes once admitted; tools in the unread-licence class (including `Cascade`) remain uninstalled and unexecuted until their licence is read and admitted.

## Planned record schemas

- `circuit_digital.digital_operation.v1`
- `circuit_digital.digital_result.v1`
- `circuit_digital.scan_and_jtag_dft_manifest.v1`
- `circuit_digital.io_vector_trace.v1`
- `circuit_digital.firmware_and_boot_rom_binding.v1`

These are planned identifiers. None of them is registered or qualified here.

Read [validation tooling](validation-tooling.md) for the executable repository interfaces.
