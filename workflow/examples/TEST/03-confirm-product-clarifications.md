# TEST 03｜整理产品确认：输入输出示例

[对应提示词](../../TEST/03-confirm-product-clarifications.md) · 实际工作模式：**Plan**

> 静态教学样例；业务确认、实现、脚本与结果均为示意，未执行真实测试。

## 输入示例

输入 TEST 02 的问题；此时才展开教学产品回复。
可共享 BA 已归档的 [DEC-v1](../reference/decisions.md)，不要求产品对同一问题重复确认。

## 输出产物示例

### shared/decisions.md

复用 [DEC-v1](../reference/decisions.md)。TEST 新发现但没有回答的问题保留，不覆盖 BA 的来源。

### test/questions.md（更新）

TQ-01 → DEC-01/08；TQ-02 → DEC-02/03；TQ-03 → DEC-04；
TQ-04 → DEC-05；TQ-05 → DEC-06；TQ-06 → DEC-07 与 BLOCK-01。
教学回复已覆盖 TQ-01—05；旧格式／唯一性明细仍待补，不能整体填“全部已解决”。

### test/clarification-review.md

核对重点：编辑保存即使只改显示名也必须补邮箱；API 与 UI 同业务规则；失败不能部分写入。
已采用：P01—P09 中对应问题的教学口径。
未确定：真实错误结构、完整格式／唯一性细则。
状态：允许形成可测试的 AC 候选；没有发生真实产品签字。
Plan 先展示，实际归档按原提示词切 Build。

## 讲解检查点

TEST 可以复用已确认决策；独立分析不等于隔绝真实澄清。

[TEST 示例索引](README.md) · [全部示例](../README.md)

