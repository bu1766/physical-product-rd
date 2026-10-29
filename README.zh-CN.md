# 实体产品研发

[English](README.md)

`physical-product-rd` 是用于协调实体产品研发的 Codex skill，覆盖需求、硬件、固件、结构设计、联调和验证。它帮助整理证据并作出有边界的验收判断。本仓库不包含真实产品设计、项目记录、客户资料或实物测试结果。

**状态：实验性流程。** 目前只对两个虚构场景做了文档推演；没有受控对比来测量缺陷、返工、耗时或 token 用量，也没有用本包验证真实设备。

## 安装与调用

将仓库内容复制到 `~/.codex/skills/physical-product-rd`，保持 `SKILL.md`、`references/` 和 `agents/` 的相对位置。如目标目录已存在，先备份并审阅差异。调用 `$physical-product-rd`，给出具体任务：

> Use $physical-product-rd to review [产品及版本] for [目标]. Controlled source files are at [路径]. Available evidence is [清单]. Do not modify the released baseline.

输入应包括产品身份、目标与排除范围、受控资料位置、相关版本、历史尝试、可用设备及获准的修改边界。预期产出包括范围与基线、风险和接口梳理、拟议工作或检查、证据等级、验收/HOLD 记录、回滚或下一步。环境允许且任务适合时可使用专业角色；单领域任务不必委派。

## 风险分级与停止条件

低风险、可逆的文档修改可做简短检查。供电、接口、保护功能、持久化参数和发布声明必须经过适用的工程及实物门禁。可复用仍然适用、可追溯的证据；需求、设计、环境或新发现影响既有结论时才重验。每项可选检查都应说明会改变什么决策；达到约定验收条件后停止扩展。对同一缺陷的两次实际修改均失败后，先进入根因调查 HOLD，再考虑继续编辑。

[虚构台灯案例](references/example-and-template.md) 展示从需求、拟议修改、测试计划到失败处理和有限验收的过程。[离线评估](references/offline-evaluation.md) 推演一个模拟故障和一个模拟新功能。两者都不能证明真实产品性能。

## 局限与责任

本 skill 不能替代原生设计工具、目标环境编译、可识别实物的台架测试、现场验证、认证或负责工程人员的批准。编译或模拟推演不等于产品放行。实物改动、烧录、量产使用和客户部署需要各自授权及适用的安全证据。产品安全和放行决定仍由使用者及负责的工程团队承担。

文件入口：[skill 主文件](SKILL.md)、[角色分工](references/agent-roles.md)、[执行门禁](references/development-execution-quality-gate.md)、[验收门禁](references/acceptance-gates.md)、[虚构案例](references/example-and-template.md)、[离线评估](references/offline-evaluation.md)，以及 `agents/openai.yaml`。

依赖齐备时可运行 skill creator 的 `quick_validate.py` 检查包结构；它不能验证工程结果。本仓库目前未授予额外开源许可证。
