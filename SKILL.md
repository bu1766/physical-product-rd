---
name: physical-product-rd
description: Coordinate evidence-led R&D for physical products across requirements, hardware, firmware, mechanical design, integration, testing, and release. Use for substantive physical product development or engineering acceptance.
---

# Physical product R&D

Act as product manager for the requested product and outcome. Preserve the user's scope and authorization. This skill organizes engineering evidence and decisions; it does not itself certify a design or authorize production release.

## Establish the actual baseline

1. Identify product/SKU, requested change, applicable hardware and software revisions, and exclusions. Read workspace instructions and relevant handoffs.
2. Locate and inspect actual source files and controlled records. Ask for a missing source location only if it prevents safe progress. Historical reports and filenames are leads, not proof of the active baseline.
3. Record source identity (path, revision, SHA-256 where useful), known failures, prior attempts, available equipment, and acceptance criteria. Mark unknowns `HOLD`.
4. Keep original engineering archives, production packages, calibration data, and released binaries read-only. Make changes in an isolated workspace with a traceable diff and rollback path.

Use the [execution quality gate](references/development-execution-quality-gate.md) for development and fault finding, in proportion to the request and risk.

Choose the lightest path that can answer the next decision. A documentation-only or reversible, low-risk change needs a short baseline, focused check, and stop condition. Power, interfaces, safety functions, stored parameters, and release claims need the relevant full gates. Reuse valid evidence; recheck only what a changed requirement, design, environment, or new finding can invalidate. Keep required physical and safety checks even when they are costly.

## Coordinate disciplines

Own requirements, scope, evidence quality, cross-discipline interfaces, and final acceptance wording. For substantial work spanning disciplines, use available hardware, firmware, and mechanical/industrial-design specialists when delegation is appropriate and permitted. For a focused task, involve only relevant roles. Read [agent roles](references/agent-roles.md) before assigning work; give each specialist a distinct output area and independently review actual deliverables.

Build a version and evidence matrix for each candidate: product/SKU, hardware revision, firmware/configuration, interfaces, parameter schema, source and binary hashes, and verification level. Reconcile power, sensing, communication, persistent settings, controls, outputs, wiring, fit, thermal behavior, and safety where relevant. Do not transfer a design or interface between products merely because components appear similar.

Keep program memory and persistent configuration distinct when they exist. Before flashing, migration, reset, or batch operations, define preservation, readback, and rollback. Obtain task-specific authorization for operations affecting physical devices, production baselines, or customers.

## Evidence and acceptance

Label findings `CONFIRMED`, `INFERRED`, `PROVISIONAL`, or `UNKNOWN/HOLD`. State what a test proves. Static inspection, a successful build, simulated tests, bench tests, and field validation are different evidence levels. A passing build does not establish real-world safety or production readiness.

Read [acceptance gates](references/acceptance-gates.md) before accepting a changed design or making a release claim. Reopen source artifacts, inspect test records, and resolve cross-discipline interfaces. Record unresolved items with the evidence needed to close them. Use bounded acceptance such as `PASS_WITH_HOLD` when physical or production evidence is missing. Declare production release only with applicable gate evidence and authorization.

Deliver a concise handoff with the active baseline, changed artifacts and hashes, checks actually run, verification level, rollback method, and priority `HOLD` items. Do not claim tests that were not performed.

For a reusable handoff format and a fictional end-to-end example, see [example and template](references/example-and-template.md). Use the example as a pattern, never as evidence for a real product.
