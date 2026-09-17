# BA 分步提示词

静态分享请看[本角色全部输入输出样例](../examples/BA/README.md)；本次不需要现场执行。

从 Teams 转写与现有系统材料出发，经过澄清、需求草稿和原型评审，形成可交接的需求基线。

先读[模式、参数及共同产物说明](../README.md)。每个步骤编号对应 PPT 图片里的同号节点；文件中的输入与输出路径是运行约定。

## 步骤索引

| 步骤 | 提示词 | 模式 | 输出内容 |
|---|---|---|---|
| 01 | [准备输入](01-prepare-inputs.md) | Plan；归档用 Build | 材料清单、可读取情况、现状材料缺口和本轮分析范围。 |
| 02 | [提取需求与依据](02-extract-requirements.md) | Plan；归档用 Build | 带来源的需求线索表，以及冲突、疑似转写错误和未知清单。 |
| 03 | [明确本次变化](03-define-change-scope.md) | Plan；归档用 Build | 现状—目标变化表、范围清单、相关角色与受影响流程。 |
| 04 | [生成澄清问题](04-prepare-clarification.md) | Plan；归档用 Build | Q 编号的问题清单、本轮优先询问的最多三个问题。 |
| 05 | [BA／产品确认](05-confirm-business-rules.md) | Plan；归档用 Build | 已明确确认、部分回答、仍未决、与旧结论冲突四类结果。 |
| 06 | [记录确认结果](06-record-decisions.md) | Build | 更新后的业务决策、问题状态和下游影响清单。 |
| 07 | [形成需求草稿](07-draft-story-prd.md) | Build | 按用户价值拆分的 User Story，以及聚焦本次变化的 PRD 草稿。 |
| 08 | [生成 HTML 原型](08-generate-html-prototype.md) | Build | 本地可打开的交互原型、页面与 Story 映射、实际检查记录。 |
| 09 | [业务／产品评审](09-review-requirement-prototype.md) | Plan；归档用 Build | 反馈分类、PRD—Story—原型一致性检查、需修订项与评审状态。 |
| 10 | [三方联合评审 AC](10-review-shared-ac.md) | Plan；归档用 Build | 同一份 AC 的候选修订、逐条评审记录及正式确认范围。 |
| 11 | [确认需求基线](11-confirm-requirement-baseline.md) | Build | 需求基线索引、REQ—US—AC—PAGE 映射，以及未确认范围。 |
| 12 | [交接 DEV 与 TEST](12-handoff-dev-test.md) | Build | 需求交接说明、阅读顺序、待办与变更同步机制。 |

## 使用要点

第 05／09／10 步包含人工确认或评审；只有受影响的规则和范围需要回退。第 07 步是草稿，第 11 步才索引已确认范围。

图片：[BA 流程图](../../output/role-workflow-images/ba-workflow.png)。参考材料：[原 BA Commands](../../workflow-template/BA/workflow-template/.opencode/commands/discover.md)。
