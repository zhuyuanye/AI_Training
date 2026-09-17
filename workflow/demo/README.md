# 统一案例与静态分享资料

**案例：用户管理新增邮箱必填要求，保持前后端校验一致。**

本次采用**预制材料逐步讲解**：展示输入、对应提示词、OpenCode Plan／Build 选择、输出产物和人的检查点。现场不运行 Agent、不连接业务项目、不执行测试。

所有业务口径、代码片段、评审与结果都是合成教学内容。它们没有经过真实 OpenCode 会话生成或业务执行；运行样例明确标为模拟。

## 快速入口

| 要展示什么 | 打开哪个文件 |
|---|---|
| 每一步的具体输入和输出 | [全部 39 步示例](../examples/README.md)：36 个角色步骤＋3 个复用步骤 |
| BA／DEV／TEST 原提示词 | [原提示词索引](../README.md) |
| 90 分钟或 60 分钟讲解安排 | [静态讲师手册](presenter/01-runbook.md) |
| 每一段怎么讲 | [讲师话术](presenter/03-speaker-script.md) |
| 用哪些问题与预设回答互动 | [产品澄清卡](presenter/02-product-clarification-cards.md) |
| 课前检查材料 | [准备清单](presenter/04-rehearsal.md) |
| 超时或展示异常如何处理 | [展示兜底](presenter/05-recovery.md) |
| 各角色从哪份输入切入 | [展示顺序卡](session-cards.md) |
| 固定案例参数与版本 | [案例参数卡](environment-card.md) |
| 直接展示 HTML 原型 | [三个页面状态](../examples/prototype/index.html) |

## 原始输入按阶段展示

| 材料 | 使用时机 |
|---|---|
| [01 现状说明](inputs/01-current-system.md) | BA／TEST 独立分析时 |
| [02 主会议转写](inputs/02-teams-transcript.md) | BA 初始输入；保留时间戳 |
| [03 原始业务需求](inputs/03-raw-business-request.md) | TEST 初始输入；不预置 AC 和答案 |
| [04 工单导出转写](inputs/04-reuse-transcript.md) | 最后讲 Skill／Command 换材料复用 |

答案放在 [examples](../examples/README.md) 中，原始输入仍保持开放。讲解时先展示问题，让学员想一想，再展开后续决策与输出；无须真正启动隔离会话。

## 主线

BA 从会议中区分目标、建议和未决，产品口径形成共同 DEC；TEST 独立分析后参与同一份 AC；DEV 依据基线定位链路、拆任务、改动和自测；TEST 按 AC 检查 API、UI 与人工项目，通过模拟失败讲诊断和复测；最后从使用过程提炼 Skill 方法与 Command 入口。

代码和接口来自 [CODE-v1 虚构上下文](../examples/reference/code-context.md)。本目录是培训资料，不是业务应用；不要求讲师提供真实代码库。

## 本次怎样开始

1. 打开 [讲师手册](presenter/01-runbook.md)，选择 60 或 90 分钟。
2. 预先打开需要展示的输入、提示词和输出样例。
3. 每步讲清楚“给什么、做什么、得到什么、谁检查”。
4. 执行部分展示模拟文本，不展示伪造的真实运行画面。
5. 把原提示词作为课后实践材料；真正工作时仍须真实执行和保留证据。

流程图：[BA](../../output/role-workflow-images/ba-workflow.png)、[DEV](../../output/role-workflow-images/dev-workflow.png)、[TEST](../../output/role-workflow-images/test-workflow.png)。

[返回工作流总目录](../README.md)
