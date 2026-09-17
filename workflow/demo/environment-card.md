# 案例参数卡｜静态分享

本次不用填写真实运行环境。以下只是串起样例的教学参数，不是有效地址、提交或账号。

| 参数 | 静态样例值／含义 |
|---|---|
| 主需求 | REQ-DEMO-EMAIL-001，管理端邮箱必填 |
| 复用主题 | REQ-DEMO-EXPORT-001，工单导出，仅做需求探索 |
| 假设产物目录 | artifacts/REQ-DEMO-EMAIL-001；只是业务实例路径约定 |
| 实际样例位置 | [workflow/examples](../examples/README.md) |
| 决策／需求基线 | DEC-v1、BASELINE-v1 |
| 共同 AC／用例 | AC-v1、TC-v1 |
| 虚构修改前版本 | DEMO-BASE，邮箱可空 |
| 虚构首次交付 | DEMO-CHANGE-A，编辑省略 email 漏校验 |
| 虚构修复版本 | DEMO-FIX-B，编辑始终先做必填校验 |
| 模拟开发批次 | SIM-DEV-BASE-01、SIM-DEV-A-01 |
| 模拟测试批次 | SIM-TEST-A-01、SIM-TEST-B-01 |
| 代码与接口资料 | [CODE-v1](../examples/reference/code-context.md)，纯教学示意 |
| 产品回复 | [预设澄清卡](presenter/02-product-clarification-cards.md)，不是真实确认 |
| 真实仓库／提交／环境／凭据 | 未提供，本次分享不需要 |
| 真实执行状态 | 未执行；没有原始日志、XML、Trace 或测试截图 |

原提示词中的 `{{…}}` 供课后实际使用时手工替换。不能把 DEMO 标签当 Git SHA，不能把教学 API 当实际项目协议，不能拿模拟报告替代验证。

[分享入口](README.md) · [全部样例](../examples/README.md)
