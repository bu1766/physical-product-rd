# Handoff template and fictional example

This example is **fictional and simulated**. It demonstrates decisions and records; no device, toolchain, or field test was run.

## Compact handoff template

```text
Objective / excluded scope:
Product and revision; source identity:
Relevant prior attempts and evidence:
Risk and next decision:
Changed artifacts and rollback:
Checks actually run; reused evidence and why still valid:
Verification level and limits:
Acceptance result; HOLD item with closure evidence:
Next action and stop condition:
```

## Fictional end-to-end case: desk lamp status light

**Requirement.** Add a low-battery status light to a hypothetical rechargeable desk lamp. Brightness control and protective power cutoff must behave as before. This is not a real product or design.

**Baseline.** Assume revision H2 and firmware F4 have controlled records. A real task would record file hashes, build settings, and test history; none exist for this example. The proposed light touches an output pin, battery sensing, enclosure window, user instructions, and power budget.

**Plan and change.** Define the light's on/off conditions and current limit. Review pin assignment, power draw, and window placement. Propose a minimal firmware and drawing change in an isolated branch. Keep protective cutoff logic outside the intended change and preserve prior sources for rollback.

**Tests and stop condition.** Static review covers pin assignment, interface table, status states, and instructions. A real target build and unit tests would establish L1/L2 only if run. Identified-device checks of current draw, fit, low-battery behavior, power interruption, and protective cutoff remain necessary before physical acceptance. Stop optional investigation when these agreed criteria are met; reopen only checks affected by a changed design, environment, requirement, or new finding.

**Simulated acceptance.** The proposal is L0 and `PASS_WITH_HOLD` for design discussion only. HOLD: no target build, unit test, current measurement, fit check, or cutoff regression has occurred. It is not approved for installation or release. If two actual fixes to the same defect fail acceptance, enter `HOLD-ROOT-CAUSE`, preserve diffs and measurements, and choose a test that separates remaining causes before editing again.

This is the path from requirement through proposed change, test plan, failure route, and bounded acceptance. It makes no claim about a real product's performance.
