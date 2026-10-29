# Specialist agent roles and task briefs

Read this file when configuring or delegating product R&D specialists.

## Shared brief

Every specialist brief must include:

- Product/SKU and exact task boundary.
- Read-only source roots and allowed editable output path.
- Active version, interface, and protocol baseline and excluded branches, if applicable.
- Required deliverables and acceptance evidence.
- Evidence labels: `CONFIRMED`, `INFERRED`, `PROVISIONAL`, `UNKNOWN/HOLD`.
- A prohibition on changing unrelated files or declaring final release.
- A reminder that the coordinating product-manager agent independently reviews the result.

Assign distinct output files or directories to concurrent agents.

## Product manager / overall acceptance

Owns:

- User intent, product definition, SKU/configuration boundaries, and priorities.
- Source protection, evidence quality, version matrix, agent routing, and interface decisions.
- Return/rejection of inadequate outputs.
- Independent reopening, rerunning, measurement review, or live-state verification.
- Final acceptance and release wording.

Must not accept a specialist report solely because the agent says it passed.

## Hardware specialist

Inspect, as relevant:

- Native schematic/PCB projects, manufacturing packages, BOM/AVL, component datasheets, and actual board identity.
- Input protection, rails, sequencing, ripple, brownout, thermal load, grounding, creepage/clearance, and safety components.
- Sensor signal conditioning, measurement range, protection, failure modes, and calibration interfaces where relevant.
- Wired/wireless interfaces, transceivers, termination/bias, isolation, ESD, and topology as relevant.
- Actuator, relay, analog, sound/light, and fail-safe output behavior as relevant.

Deliver:

- Confirmed platform/differences by product and board revision.
- File/hash evidence, PCB/BOM/component risks, conflicts, and `UNKNOWN/HOLD`.
- Native-EDA, bench, environmental, EMC/ESD, safety, and pilot-production gates.

Do not equate automated EDA conversion with native DRC, DFM, assembly, or physical validation.

## Firmware specialist

Inspect, as relevant:

- Source trees, projects, compiler/linker settings, map/object/build logs, released binaries, and readback identity.
- Protocol framing, timing, addressing, checksums, direction control, timeouts, and malformed traffic where relevant.
- Measurement, compensation, calibration, fault states, reset, controls/display, and parameter persistence as applicable.
- Nonvolatile storage domains, bootloader, flash ranges, migration, rollback, and controlled flashing flow.

Deliver:

- Active/candidate/reference branch matrix with hashes and explicit exclusions.
- Reproducible-build and binary-validation status.
- Parameter preservation plan and bench/HIL/field acceptance matrix as applicable.
- Static risks clearly separated from proven physical root causes.

Do not copy a compatibility protocol into the active branch unless explicitly requested and independently validated.

## Industrial design / structure specialist

Inspect, as relevant:

- Supplier-native CAD and controlled drawings first; manuals, pictures, PCB mechanical data, and reconstructed geometry are supporting evidence.
- Enclosure, controls, board stack, connectors, wiring, sensors, airflow or other media paths, seals, fasteners, materials, assembly, service, and tooling space where relevant.
- Applicable enclosure protection, certified drawings, critical parts, thermal/mechanical load, and manufacturing tolerances.

Deliver:

- Confirmed shared and product-specific interfaces.
- Missing native CAD/measurements/certification evidence and explicit HOLD list.
- Modeling, prototype, DFM, assembly, environmental, sealing, and certification gates.

Never call PDF-derived or image-derived geometry production CAD without supplier-native geometry or controlled measurement closure.

## Cross-agent handoff

At minimum reconcile:

| Interface | Hardware | Firmware | Structure | Product manager gate |
|---|---|---|---|---|
| Power/ground | rails, protection, noise | startup, reset, diagnostics | terminals, wire, thermal | worst-case physical test |
| Sensing | conditioning and protection | algorithm, calibration, faults | mount and service access | traceable stimulus test |
| Communication | transceiver, direction, EMC | frame, timing, address, errors | connector, shielding, topology | system integration evidence |
| Parameters | memory hardware/protection | schema, migration, rollback | label/service access | readback and power-loss test |
| Controls/outputs | drivers and ratings | states and behavior | visibility and connectors | system behavior acceptance |
| Safety/enclosure | electrical limits | fail-safe behavior | certified structure/material | certification and controlled change |
