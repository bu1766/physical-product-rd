# Product-manager acceptance gates

Read this file before final acceptance or any production-readiness conclusion. Apply only the gates relevant to the requested scope, but do not omit a gate whose failure could invalidate the result.

## Gate 0: identity and scope

- Product, SKU, relevant variants, hardware revision, interfaces, power, and optional modules are identified.
- Source inputs and excluded branches are explicit.
- Current device identity is backed by labels, file hashes, readback, or controlled records—not filenames alone.

## Gate 1: immutable evidence and rollback

- Source archives remain unchanged.
- Copied engineering inputs match source SHA-256 where identity matters; OS metadata may be excluded and documented.
- Editable work is isolated and rollback material exists.
- Unknowns are marked HOLD instead of silently inferred.

## Gate 2: native design and reproducibility

- Hardware changes: native EDA opens/compiles; ERC/DRC and manufacturing outputs are reviewed.
- Firmware changes: clean builds are reproducible; compiler, linker, configuration, map, and binary identities are recorded.
- Structure changes: native CAD/drawings or controlled measurements support the released geometry; editable models and exports are reopened and checked.

Passing static conversion, screenshot, log, or agent self-test alone does not pass this gate.

## Gate 3: interfaces and parameter safety

- Power, sensing, communication, persistent settings, controls, outputs, wiring, mechanical fit, thermal, environmental, and safety interfaces are reconciled where applicable.
- Distinct nonvolatile storage domains have separate preservation/migration/rollback rules where relevant.
- Invalid, interrupted, power-loss, and downgrade paths are tested where relevant.

## Gate 4: physical and HIL validation

- Representative hardware is identified and tested.
- Firmware is flashed/read back with preserved parameters.
- Communication uses the intended peer and captures data or waveforms under nominal and abnormal traffic where relevant.
- Sensors and outputs are tested with traceable stimuli, fault, and recovery conditions as applicable.
- Mechanical work is checked for fit, tooling, wiring, service, sealing, and assembly variation.

## Gate 5: environmental, safety, and certification

Apply relevant environmental, electrical, mechanical, electromagnetic, enclosure, and regulatory tests for the actual product and market. Review controlled drawings, critical parts, and certification scope when applicable.

Certification claims require the real certificate scope and controlled design evidence. A manual statement or logo is not enough.

## Gate 6: production release

- Controlled BOM/AVL, manufacturing files, firmware package, parameter template, drawings, inspection criteria, fixtures, SOP, traceability, and change record are complete.
- Pilot build results and failures are closed.
- Delivery procedures cannot bypass safety, identity, verification, or parameter protection.
- Product manager independently checks evidence and records an exact release status.

## Status vocabulary

- `EVIDENCE_INVENTORY_COMPLETE`: files inventoried; engineering not accepted.
- `PASS_WITH_HOLD`: bounded technical acceptance with explicit unresolved items.
- `READY_FOR_PRODUCT_MANAGER_INDEPENDENT_ACCEPTANCE`: specialist self-check complete only.
- `ACCEPTED_AS_<BOUNDED_BASELINE>_WITH_HOLDS`: usable for a stated next step, not production release.
- `PRODUCTION_RELEASED`: use only after all applicable gates are satisfied with real evidence and the scope is authorized.

## Final acceptance record

Record:

1. Exact accepted artifacts and hashes.
2. Independent checks actually performed.
3. Rejected versions and why, when relevant.
4. Active baseline and prohibited/reference branches.
5. Remaining HOLD items, owners, and closure evidence.
6. What the result may and may not be used for.
