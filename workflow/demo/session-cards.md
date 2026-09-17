# 展示顺序卡｜不用启动会话

每个阶段依次展示“输入→原提示词→输出样例→检查点”。模式表示实际工作时如何选择 OpenCode 主代理；本次无需切换或执行。

| 阶段 | 先展示的输入 | 再展示的输出 | 模式讲解 |
|---|---|---|---|
| BA 起步 | [现状](inputs/01-current-system.md)、[转写](inputs/02-teams-transcript.md) | [BA 01—04](../examples/BA/README.md) | Plan 分析；需要保存再 Build |
| TEST 独立分析 | [原始业务需求](inputs/03-raw-business-request.md)、现状 | [TEST 01—02](../examples/TEST/README.md) | Plan；不提前读 AC、代码与答案 |
| 产品澄清 | 已提出的问题、[产品卡](presenter/02-product-clarification-cards.md) | [共同 DEC](../examples/reference/decisions.md) | Plan 核对，Build 登记 |
| BA 需求产物 | DEC、范围 | [Story／PRD](../examples/BA/07-draft-story-prd.md)、[HTML](../examples/prototype/index.html) | Build 产物，Plan 评审 |
| 共同验收 | 独立分析、DEC、需求稿 | [AC](../examples/reference/ac.md)、[基线](../examples/BA/11-confirm-requirement-baseline.md) | Plan 讨论，Build 归档 |
| DEV 理解与实施 | 基线、[虚构代码](../examples/reference/code-context.md) | [DEV 01—12](../examples/DEV/README.md) | Plan 地图／方案／review，Build 改动和验证 |
| TEST 设计与对照 | AC，之后才给代码 | [用例](../examples/reference/test-cases.md)、分层和差异 | Plan |
| TEST 自动化与执行 | 用例、代码版本、工具设定 | [脚本](../examples/TEST/08-prepare-environment-and-automation.md)、[模拟结果](../examples/TEST/09-execute-and-capture-evidence.md) | Plan→Build；现场只是看样例 |
| TEST 诊断与结论 | 模拟记录、修复示意 | [诊断到报告](../examples/TEST/10-diagnose-failures.md) | Plan 分析，Build 修正／复测／归档 |
| 自建与复用 | 预设纠正记录、[新转写](inputs/04-reuse-transcript.md) | [COMMON 01—03](../examples/COMMON/README.md) | Plan 提炼、Build 文件与验证 |

这里不是实际 Agent 会话记录。课后实践时，才按原步骤把真实文件明确传入各会话，不假设 Agent 记得另一个窗口的内容。

[分享入口](README.md) · [讲师手册](presenter/01-runbook.md)
