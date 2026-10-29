# Development execution quality gate

Apply these checks to product development and fault finding. Scale records and reviews to risk and requested scope.

## Before a change

- Establish the active baseline from real files, records, and where available the actual device. Record product, revision, build environment, relevant configuration, and source identity.
- Review prior attempts, diffs, failures, logs, and tests. State the mechanism being tested and an observable acceptance condition.
- Keep controlled originals read-only. Work on a separate copy or branch with a rollback path.
- Prioritize safety, high-impact failure modes, and the current critical path. For each proposed check, name the decision its result would change and a stop condition. Defer low-impact possibilities that cannot change the next engineering decision.

## During development

- Make the smallest change supported by a reproducible defect, new requirement, or approved design decision. Preserve unrelated behavior.
- Record diff, configuration, target hardware, and checks. Reconcile interfaces across requirements, hardware, firmware, mechanics, and test.
- Safety-critical changes require risk analysis, independent review, relevant failure and recovery tests, and product-manager acceptance. Do not infer hardware fixes or component values from intuition alone.
- For communication changes, record frame structure, byte order, timing, electrical interface, error handling, and recovery as applicable.

## Stop repeated unsuccessful repair

After two actual changes to the same defect fail acceptance, mark `HOLD-ROOT-CAUSE` before another attempt. Preserve reproduction steps, input/output, logs or measurements, environment, versions, prior diffs, disproven hypotheses, and a discriminating next test. Resume after independent root-cause review and new evidence. Analysis alone does not count as a failed repair attempt.

## Verification levels

| Level | Evidence |
|---|---|
| L0 ANALYZED | Analysis or design only |
| L1 BUILT | Actual target toolchain build with recorded command and configuration |
| L2 TESTED | Relevant automated or integration tests with results and coverage limits |
| L3 BENCH/HIL | Identified physical unit, controlled conditions, and recorded measurements |
| L4 FIELD | Representative field or endurance evidence with conditions and duration |
| L5 RELEASE | Independent acceptance against applicable release gates and authorization |

Levels are not automatically cumulative. Describe missing evidence and scope limits. Bench results from one unit do not establish population reliability.

Reuse traceable, still-applicable evidence. Repeat a check when the relevant design, environment, or requirement changed, or new evidence calls the old result into question. Stop optional investigation once the agreed acceptance condition is met; keep real safety and physical validation gates intact.

## Handoff

Record objective; baseline; prior relevant attempts; files changed; evidence and exact checks run; verification level; failures or `HOLD`; risks and rollback; next discriminating action; and independent acceptance decision. If equipment, permissions, or tools block a check, mark it `BLOCKED` and retain the reproducible state.
