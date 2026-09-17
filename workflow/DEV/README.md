# DEV 分步提示词

静态分享请看[本角色全部输入输出样例](../examples/DEV/README.md)；本次不需要现场执行。

先理解项目与需求，再确认基线、方案和小任务，逐步修改、验证、review，最后交接 TEST。

先读[模式、参数及共同产物说明](../README.md)。每个步骤编号对应 PPT 图片里的同号节点；文件中的输入与输出路径是运行约定。

## 步骤索引

| 步骤 | 提示词 | 模式 | 输出内容 |
|---|---|---|---|
| 01 | [接收开发输入](01-receive-development-input.md) | Plan；归档用 Build | 开发输入核对表、需求理解、缺失项及开工范围。 |
| 02 | [建立项目地图](02-build-project-map.md) | Plan；归档用 Build | 技术栈、模块与目录地图、启动和测试入口、典型功能链路。 |
| 03 | [定位相关实现](03-trace-current-implementation.md) | Plan；归档用 Build | 页面到数据的实际链路、当前行为—目标行为差异表、候选修改位置。 |
| 04 | [运行修改前检查](04-run-baseline-checks.md) | Build | 实际检查命令、退出码和日志；改动前已通过、失败、阻塞及未执行项目。 |
| 05 | [分析风险与方案](05-analyze-risk-and-solution.md) | Plan；归档用 Build | 影响分析、推荐方案、文件范围、验证计划与必要的回退安排。 |
| 06 | [开发者评审](06-review-development-solution.md) | Plan；归档用 Build | 方案评审结果、已确认实施范围、需调整或业务澄清事项。 |
| 07 | [拆分小任务](07-split-small-tasks.md) | Plan；归档用 Build | TASK 编号、执行顺序、依赖、文件范围和完成条件。 |
| 08 | [实现一个小任务](08-implement-one-task.md) | Build | 一个小任务的代码与必要测试变更、实施记录、待执行验证项。 |
| 09 | [运行检查并看 diff](09-run-checks-and-diff.md) | Build | 与当前修改对应的验证证据、diff 检查结果和失败分类。 |
| 10 | [确认符合方案](10-review-scope-and-correctness.md) | Plan；归档用 Build | 按影响排序的 review 发现、范围核对和验证缺口。 |
| 11 | [完成任务与约定验证](11-complete-validation.md) | Build | 最终验证汇总、完成与剩余任务、仍未覆盖的 AC／风险。 |
| 12 | [交付 TEST](12-handoff-to-test.md) | Build | 实现说明、自测证据、运行前提、未验证项与已知风险。 |

## 使用要点

第 02 步项目地图首次建立，后续按需更新。第 08—10 步按小任务循环，第 11 步补齐约定验证。Build 模式的第 04／09 步只执行检查，不允许借机改业务代码。

图片：[DEV 流程图](../../output/role-workflow-images/dev-workflow.png)。参考材料：[原 DEV 工作流](../../workflow-template/DEV/opencode-study/AGENTS.md)。
