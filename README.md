# Physical Product R&D — Hardware and Firmware Development Skill

[简体中文](README.zh-CN.md)

`physical-product-rd` is a Codex skill for coordinating physical product development across requirements, hardware, firmware, mechanical design, integration, and verification. It helps organize evidence and bounded acceptance decisions. It contains no real product design, project records, customer data, or device test results.

**Status: experimental workflow.** Two fictional scenarios have been walked through as documents. No controlled comparison has measured defects, rework, elapsed time, or token use. No real device has been validated by this package.

## Who this is for

For hardware and embedded-firmware developers using an AI coding assistant to structure a physical-product task: reviewing requirements, tracing hardware–firmware interfaces, planning integration tests, or recording acceptance evidence. This is a workflow package, not a circuit design, firmware library, or replacement for physical testing.

## Download and explore

- [Download the repository as a ZIP](https://github.com/bu1766/physical-product-rd/archive/refs/heads/main.zip), or select **Code → Download ZIP** on GitHub.
- Start with [SKILL.md](SKILL.md), then read the [fictional worked example](references/example-and-template.md).
- [中文说明与安装方法](README.zh-CN.md).

Downloading does not install or run anything. Review the files and the license notice below before use.

## Install and invoke

Copy the repository contents to `~/.codex/skills/physical-product-rd`, keeping `SKILL.md`, `references/`, and `agents/` together. Review and back up any existing directory before replacement. Invoke `$physical-product-rd` with a concrete task:

> Use $physical-product-rd to review [product and revision] for [goal]. Controlled source files are at [path]. Available evidence is [list]. Do not modify the released baseline.

Provide product identity, requested outcome and exclusions, controlled source location, relevant revision, prior attempts, available equipment, and authorized change boundary. The skill produces a scoped baseline, risk and interface map, proposed work or checks, evidence level, acceptance/HOLD record, and rollback or next action. It can use specialists when available and appropriate; a focused task does not require delegation.

## Risk and stopping rules

Use a short review for low-risk, reversible documentation changes. Power, interfaces, protective behavior, persistent settings, and release claims require the applicable engineering and physical gates. Reuse traceable evidence that still applies; repeat checks when a relevant requirement, design, environment, or finding changes. For every optional check, state which decision it could change and stop when agreed acceptance criteria are met. Two failed actual fixes to one defect trigger a root-cause HOLD before another edit.

The [fictional desk-lamp case](references/example-and-template.md) shows requirement, proposed change, test plan, failure route, and bounded acceptance. [Offline evaluation](references/offline-evaluation.md) walks through a simulated fault and feature. Neither is evidence of real-world performance.

## Limits and responsibility

This skill does not replace native design tools, target builds, identified-device bench tests, field validation, certification, or responsible engineering approval. A build or simulated review is not a product release. Physical changes, flashing, production use, and customer deployment require their own authorization and applicable safety evidence. The user and responsible engineering team retain product safety and release decisions.

Files: [skill entrypoint](SKILL.md), [agent roles](references/agent-roles.md), [execution gate](references/development-execution-quality-gate.md), [acceptance gates](references/acceptance-gates.md), [fictional example](references/example-and-template.md), [offline evaluation](references/offline-evaluation.md), and `agents/openai.yaml`.

The skill creator's `quick_validate.py` can check package structure when its dependencies are available; it cannot validate engineering outcomes. No additional open-source license is granted by this repository at present.
