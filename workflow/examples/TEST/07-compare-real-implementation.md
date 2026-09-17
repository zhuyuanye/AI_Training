# TEST 07｜对照实现与需求：输入输出示例

[对应提示词](../../TEST/07-compare-real-implementation.md) · 实际工作模式：**Plan**

> 静态教学样例；业务确认、实现、脚本与结果均为示意，未执行真实测试。

## 输入示例

输入独立形成的 AC-v1／TC-v1，再读取 [CODE-v1](../reference/code-context.md)。
本次只展示虚构代码。设先对照 DEMO-BASE，首次交付后再对照 DEMO-CHANGE-A。

## 输出产物示例

### test/implementation-gap.md

| 版本／位置 | 与 AC 的比较 | 结论类型 | 下一动作 |
|---|---|---|---|
| DEMO-BASE；新增／编辑服务 | 可空，与 AC-01 不符 | 预期改动点 | 等 DEV 实施 |
| DEMO-CHANGE-A；create | 调用 requiredAndNormalize | 静态看来覆盖入口 | 用 TC-01—04 验证 |
| DEMO-CHANGE-A；update | email != null 时才校验 | 疑似绕过，GAP-01 | 用 TC-05 复现，检查数据 |
| DEMO-CHANGE-A；Vue | 页面阻止空值且有历史提醒 | 静态符合方向 | 用 TC-13 验证体验 |
| 范围外入口 | 需核对是否共用策略 | 仍需回归 | TC-15 |
| 完整旧规则 | 资料不足 | BLOCK-01 | 产品／DEV 补依据 |

重要：此处 GAP-01 是静态风险，尚没有运行失败证据；不把它写成“已执行复现”。
变更后重新对照，不能沿用 DEMO-BASE 的结论证明 DEMO-CHANGE-A。

## 讲解检查点

先定期望，再看代码。静态对照发现疑点后，测试要给它运行证据。

[TEST 示例索引](README.md) · [全部示例](../README.md)

