# TEST 分步提示词

静态分享请看[本角色全部输入输出样例](../examples/TEST/README.md)；本次不需要现场执行。

先独立理解原始业务需求，再共同确认 AC、设计测试、对照实现，最后真实执行并形成证据结论。

先读[模式、参数及共同产物说明](../README.md)。每个步骤编号对应 PPT 图片里的同号节点；文件中的输入与输出路径是运行约定。

## 步骤索引

| 步骤 | 提示词 | 模式 | 输出内容 |
|---|---|---|---|
| 01 | [接收原始需求](01-receive-original-requirement.md) | Plan；归档用 Build | 原始需求输入清单、可读取范围、材料缺口和来源说明。 |
| 02 | [分析规则与风险](02-analyze-rules-and-risks.md) | Plan；归档用 Build | 有来源的规则表、风险清单和分级澄清问题。 |
| 03 | [BA／产品现场确认](03-confirm-product-clarifications.md) | Plan；归档用 Build | 已澄清、仍未决、冲突三类结论及共同决策记录的增量内容。 |
| 04 | [生成并评审 AC](04-generate-and-review-ac.md) | Plan；归档用 Build | 候选或已确认 AC、需求—AC 对应关系和评审记录。 |
| 05 | [设计测试用例](05-design-test-cases.md) | Plan；归档用 Build | 带 TC 编号、明确预期和 AC 关联的测试用例，以及覆盖缺口。 |
| 06 | [确定测试分层](06-choose-test-layers.md) | Plan；归档用 Build | 用例分层表、API／UI／人工范围、自动化优先级和暂不覆盖项。 |
| 07 | [对照 Java／Vue 实现](07-compare-real-implementation.md) | Plan；归档用 Build | AC—实现证据—差异表、接口／页面入口及需动态验证的风险。 |
| 08 | [准备环境与自动化](08-prepare-environment-and-automation.md) | Plan → Build | 自动化计划、环境使用说明、API／UI 测试实现、人工步骤和执行说明。 |
| 09 | [真实执行并留证](09-execute-and-capture-evidence.md) | Build | 真实执行记录、日志与框架报告、可用的 UI 证据、证据清单及清理结果。 |
| 10 | [诊断异常与阻塞](10-diagnose-failures.md) | Plan；归档用 Build | 逐条异常诊断、证据与待验证假设、责任角色及处理建议。 |
| 11 | [修复后复测与回归](11-fix-retest-regression.md) | Build | 修复处理记录、独立的复测证据、相关回归结果及剩余问题。 |
| 12 | [形成测试结论](12-produce-test-conclusion.md) | Build | 测试报告、缺陷报告、需求—AC—TC—执行—缺陷追踪矩阵。 |

## 使用要点

第 01—03 步不读取预置测试答案；第 04 步起共同维护 AC。第 07 步才读取实现。第 08 步含 Plan→Build 两段提示词，第 09／11 步每次执行生成独立批次。

图片：[TEST 流程图](../../output/role-workflow-images/test-workflow.png)。参考材料：[原 TEST 提示词](../../workflow-template/TEST/share_test/prompts/01-requirement-analysis.md)。
