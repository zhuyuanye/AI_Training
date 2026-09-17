# TEST 11｜修复、复测与回归：输入输出示例

[对应提示词](../../TEST/11-fix-retest-regression.md) · 实际工作模式：**Build**

> 静态教学样例；业务确认、实现、脚本与结果均为示意，未执行真实测试。

## 输入示例

输入 DEF-01、ENV-01、原失败批次；保持 AC-v1 和 TC-v1 不变。
静态叙事：DEV 修复后交付 DEMO-FIX-B；环境负责人纠正测试身份配置；TEST 建新批次。

## 输出产物示例

### 修复输入样例（DEV 负责，TEST 接收）

AdminUserService.update 节选：

```diff
-if (cmd.getEmail() != null) {
-    cmd.setEmail(adminEmailPolicy.requiredAndNormalize(cmd.getEmail()));
-}
+cmd.setEmail(adminEmailPolicy.requiredAndNormalize(cmd.getEmail()));
 repository.update(cmd);
```

新增回归应覆盖编辑省略字段、null、空串、纯空白与失败数据不变。
教学中假设 DEV 已按 DEV 08—11 重新验证并交付 B；不把 TEST 的任务默认为可直接修改产品规则。

### test/retest-log.md

**模拟复测，未实际执行。**
DEF-01：DEMO-FIX-B，TC-05 返回邮箱错误，前后快照一致，模拟复测通过。
ENV-01：修正身份配置，TC-11 到达登录／查询业务断言并模拟通过。
回归：API TC-01—12 全部通过；UI TC-13 通过；人工 TC-14/15 重新核对，通过。
BLOCK-01／TC-16 仍阻塞。

### test/runs/SIM-TEST-B-01/（应有形态）

新 run.md、API 日志／XML、UI Trace／截图、人工记录、证据清单。
本案例没有这些原始文件；没有复制 A 的绿色条目假装 B 已验证。

### test/execution-index.md（追加）

| 模拟批次 | API | UI | 人工 | 阻塞 |
|---|---|---|---|---|
| SIM-TEST-A-01 | 10 通过／1 失败／1 错误 | 1 通过 | 2 通过 | 1 |
| SIM-TEST-B-01 | 12 通过／0 失败／0 错误 | 1 通过 | 2 通过 | 1 |

保留 A 的失败记录，B 为新记录；不能覆盖 A。

## 讲解检查点

看见修改不等于缺陷关闭；要用修复版本的新证据验证，并回归受影响范围。

[TEST 示例索引](README.md) · [全部示例](../README.md)

