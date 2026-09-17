# BA 11｜登记需求基线：输入输出示例

[对应提示词](../../BA/11-confirm-requirement-baseline.md) · 实际工作模式：**Build**

> 合成教学样例，用于静态讲解；不是已执行记录或真实产品确认。

## 输入示例

输入 BA 09 原型评审、BA 10／TEST 04 的共同 AC 评审。
教学设定：产品同意 AC-01—08 对应的有限范围继续分析；BLOCK-01 未关闭。

## 输出产物示例

### shared/baseline.md

基线 BASELINE-v1，需求 REQ-DEMO-EMAIL-001，性质：教学场景。
| 产物 | 版本 | 状态 |
|---|---|---|
| shared/decisions.md | DEC-v1 | 教学采用 |
| ba/user-stories.md | US-v1 | US-01/02 教学采用 |
| ba/prd.md | PRD-v1 | 当前范围已核对 |
| ba/prototype/index.html | PROTO-v1 | 展示布局，非真实系统 |
| shared/ac.md | AC-v1 | 01—08 教学确认；09 阻塞 |
| shared/ac-review.md | AC-REVIEW-v1 | 评审样例 |

追溯映射：

| Story／约束 | 需求 | AC | 原型 |
|---|---|---|---|
| US-01 新增 | REQ-01/02/04 | AC-01/02/03/05/06 | PAGE-01/03 |
| US-02 历史编辑 | REQ-03/04 | AC-01/04/05/06 | PAGE-02/03 |
| 共同范围约束 | REQ-05 | AC-07/08；AC-09 待补 | 全部页面的范围说明 |

允许继续：管理端必填／清理／失败不写入的方案与测试设计。
保留：BLOCK-01 完整旧格式／唯一性回归，归产品与 DEV 补充依据。
变更规则：新增业务口径先更新 DEC、AC 与本索引，再同步三角色。
没有真实提交或文件哈希，不填虚构 Git SHA。

## 讲解检查点

基线让人知道这轮依据哪份规则；写了版本号不代表没有未决项。

[BA 示例索引](README.md) · [全部示例](../README.md)
