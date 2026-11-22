<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-DIGITAL — repository foundation
-->

# Circuit Digital

Circuit Digital is being built to execute register-transfer-level elaboration, dual-simulator verification, unbounded and bounded formal checks, hardware security verification, logic synthesis, scan and JTAG design-for-test insertion, first-silicon survivability checks and signed boot-ROM or firmware bindings — completely deterministically without requiring AI. This checkout contains repository validation tooling and documentation only. Full foundation qualification is in progress. There is no installed RTL synthesis runner, formal verification harness, DFT generator, firmware binder or qualified record schema.

Circuit Digital is part of the **SC Neuromorphic Computing Systems** group (SC-NEUROMORPHIC-COMPUTING-SYSTEMS). The [group and project map](https://github.com/anulum/sc-neurocore/blob/main/docs/ecosystem.md) shows the whole programme and where this repository sits in it.

**What does not exist yet:**
- an RTL synthesis, formal-equivalence, DFT or firmware-binding runner;
- a registered runtime record schema;
- any migrated AXI, FIFO or address-event-representation HDL core in this checkout.

## Boundary

**What this project owns:**

| Record | Scope |
|---|---|
| Digital operation | Pinned RTL/HLS operation request, target leaf-cell binding map, clock/reset constraints, secret-bearing register/memory annotations and formal or simulation obligations |
| Digital result | Synthesis netlist, area/gate metrics, dual-simulator X-propagation verdicts, hardware security results and formal-equivalence verdicts with explicit proof mode |
| Scan and JTAG DFT manifest | Scan-chain topology, built-in memory self-test (`autoMBIST`), authenticated debug lockouts and first-silicon dead-on-arrival survivability hooks (`pll_bypass_clk`, `por_override_n`, `TCK` scan dump, observation multiplexers) |
| Digital I/O vector trace | Cycle-accurate stimulus and reference response vectors produced by reference simulation of a pinned design view |
| Firmware and boot-ROM binding | Safe-rescue boot ROM image, post-silicon errata workarounds, register-map digests and hardware-root-of-trust signed A/B field-update bundles |

**Static imports:** only Circuit Core and Circuit Technology.

**Records read without importing domain code:**

| Source | Records consumed |
|---|---|
| Circuit Core | entity references, data-handling profiles, design views, operation profiles, approvals and system budgets |
| Circuit Technology | technology profiles and leaf-cell binding maps |
| Circuit Assembly | chiplet and 3D stack interface specifications |
| Circuit Prototyping | conversion manifests and host co-emulation bindings |
| Circuit Acceptance | acceptance reports |
| Circuit Flow | design-step learning records |
| Circuit Learning | circuit graph contracts and grader bundle specifications |
| Circuit Manufacturing | corrective-action silicon errata records |
| Spike Log | reference event-trace formats |

**Capability registration and handoffs:** Registers the digital tool profile manifest with Circuit Core, feeds formal/synthesis netlists and firmware bindings to Circuit Physical, Circuit Prototyping, Circuit Lab, Circuit Manufacturing, Circuit Acceptance, SNN Divergence Harness and Deploy Pack, and receives generic AXI, FIFO and AER HDL cores split from SC-NeuroCore.

**Explicit non-claims and operating boundaries:**
- Every digital design and verification step completes without machine learning via deterministic tools (`Yosys`, `SymbiYosys`, `Verilator`, `Icarus Verilog`) or deterministic generators and high-level synthesis (`XLS`, `CIRCT`).
- Bounded model checking is never reported as full equivalence: `equivalent` requires an unbounded proof.
- Tools whose licences have not yet been read and admitted (such as `Cascade` or unreviewed commercial EDA suites) are neither installed nor executed.

## Current tooling

Repository controls inspect:
- metadata and source attribution;
- workflows and dependency alignment;
- native documentation and repository inventory;
- preflight orchestration.

Metadata declares architecture-only maturity with empty implemented domain capability and claim inventories.

- Use the exact environment in [Contributing](CONTRIBUTING.md).
- Full CI and preflight belong in CI or in an explicitly admitted pre-push environment.
- See [Validation](VALIDATION.md) for the maintained validation scope.

## Intended evidence

Every future domain artefact will carry the platform's common provenance envelope, its source and environment digests, its confidentiality compartment and its explicit verification boundary. None of the planned record schemas is registered or qualified by this foundation.

## Documentation and support

Read [Architecture](ARCHITECTURE.md), [support](SUPPORT.md), [security reporting](SECURITY.md) and [citation metadata](CITATION.cff).

**Not claimed:**
- a hosted service, released package or DOI;
- a public CI status;
- a performed simulation, hardware measurement or sign-off verdict.

## Licence

Source is licensed under [AGPL-3.0-or-later](LICENSE). A commercial licence is available through the contact in [NOTICE](NOTICE.md).

![ANULUM](docs/assets/anulum_logo_company.jpg)

![Fortis Studio](docs/assets/fortis_studio_logo.jpg)

## Text and data mining reservation
The rightsholder, Miroslav Šotek (ANULUM), expressly reserves the use of the
works in this repository for text and data mining, including the collection of
this content for, and its use in, training, fine-tuning or evaluating machine
learning and artificial intelligence models, in accordance with Article 4(3) of
Directive (EU) 2019/790 and the national provisions transposing it.

No permission for such use has been granted beyond what the licence in
`LICENSE` grants. This reservation does not change that licence: uses the
licence permits remain permitted on its terms, including its attribution and
share-alike conditions.

Reservation made on 2026-11-22. Requests for permission: contact the
rightsholder through the contact listed in this repository.
