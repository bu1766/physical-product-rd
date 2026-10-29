# Offline evaluation record

These are **fictional, simulated document walkthroughs**, performed without a real project, device, toolchain, live model run, or token meter. They check whether the written workflow gives a bounded next decision, keeps relevant safety gates, and has a stop condition. They do not demonstrate measured time, token, defect, or rework improvement.

## Scenario A: intermittent power reset

**Input:** A hypothetical rechargeable desk lamp sometimes resets when its charging cable moves. A short event log exists, but no voltage capture. One earlier configuration change failed. The user asks for diagnosis without permission to modify a device.

**Walkthrough result:** Identify the product revision, power interface, log identity, and previous change. The next discriminating check is a controlled voltage/current capture during cable movement, after a safe test setup is approved. No firmware rewrite or battery replacement is justified yet. A second failed actual repair would trigger `HOLD-ROOT-CAUSE`. Current result: L0, `HOLD` for missing electrical evidence. Stop speculative checks that cannot separate connector, supply, and firmware-reset causes.

**Gate check:** Baseline, prior failure, next decision, physical evidence gap, and no-modification boundary are explicit. Root cause and real safety behavior remain unverified.

## Scenario B: low-battery status light

**Input:** The fictional lamp needs a low-battery indicator using a spare output and enclosure window. Protective power cutoff must remain intact. No design files or device are supplied.

**Walkthrough result:** Scope firmware status logic, pin drive, power budget, enclosure fit, and instructions. Propose a minimal isolated change and list target build, state tests, current/fit checks, power interruption, and cutoff regression as acceptance evidence. Reuse prior evidence only when the affected design and environment are unchanged. Without actual artifacts, result: L0 and `PASS_WITH_HOLD` for a proposal only. Stop optional analysis once the relevant criteria are agreed; keep the physical safety check.

**Gate check:** Requirement to acceptance, cross-discipline interface, rollback, and safety path are covered. Build, bench behavior, and release readiness remain unverified.

## Repeatable comparison on a real project

For a future authorized trial, give the same controlled task packet to a baseline workflow and this skill in separate isolated workspaces. Predefine the correct baseline, critical missed items, acceptance criteria, stop condition, and time budget. Record actual defects found, meaningful acceptance items passed, rework cycles, elapsed time, and measured token use if available. Review artifacts blind to workflow when practical. Count only relevant checks and retain applicable hardware and safety gates. No baseline run or measurements were available for this repository preparation, so no comparative claim is made.
