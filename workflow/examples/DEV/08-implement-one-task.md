# DEV 08｜按方案实施一个小步：输入输出示例

[对应提示词](../../DEV/08-implement-one-task.md) · 实际工作模式：**Build**

> 静态教学样例。源码路径、版本、评审与结果均为虚构；未修改或运行业务项目。

## 输入示例

输入 TASK-01、SOL-v1；课堂展示 DEMO-BASE → DEMO-CHANGE-A 的预制代码节选。
这是故意包含缺陷的教学输出，不是建议照抄的最终实现；没有真的修改源码。

## 输出产物示例

### 业务源码变更节选

文件位置：CODE-v1 中的 AdminUserService.java。

```diff
 // create：增加统一必填规范化。
+cmd.setEmail(adminEmailPolicy.requiredAndNormalize(cmd.getEmail()));
 repository.insert(cmd);

 // update：错误保留了原先的非空条件。
 if (cmd.getEmail() != null) {
-    legacyEmailFormat.check(cmd.getEmail());
+    cmd.setEmail(adminEmailPolicy.requiredAndNormalize(cmd.getEmail()));
 }
 repository.update(cmd);
```

相关测试片段形态（示意，不是可直接编译的测试文件）：

```java
assertThrows(EmailRequired.class, () -> policy.requiredAndNormalize(""));
assertEquals("alice@example.com",
             policy.requiredAndNormalize(" alice@example.com "));
// 本轮漏了 update 请求省略 email 的服务入口测试。
```

### dev/implementation-log.md

教学小步 TASK-01：新增 AdminEmailPolicy，修改 create/update 调用，补规则级测试。
偏差：update 保留 if 分支，省略字段未进入必填；后续 TEST 暴露 DEF-01。
此处写出偏差方便讲师备课；展示时可先遮住，让学员看 diff 找问题。

### dev/tasks.md（增量）

TASK-01：实现草稿完成、待验证。不能只因为文件写完就标为验收完成。
TASK-02/03：待做。

## 讲解检查点

先让学员检查哪条调用路径能跳过新规则，再展示解释。

[DEV 示例索引](README.md) · [全部示例](../README.md)

