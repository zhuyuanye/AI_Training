# CODE-v1｜虚构的 Java／Vue 实现上下文

**这是为静态讲解编写的代码片段与接口设定，没有读取或修改任何业务项目。路径、类型和协议均为教学示意，不是 RuoYi 的已核实实现。**

## 示例项目地图

```text
demo-app/
├── web/src/views/admin/UserEdit.vue
├── web/src/api/users.ts
├── server/src/main/java/demo/user/AdminUserController.java
├── server/src/main/java/demo/user/AdminUserService.java
├── server/src/main/java/demo/user/AdminEmailPolicy.java
├── server/src/main/java/demo/user/UserRepository.java
├── server/src/main/java/demo/profile/ProfileService.java
└── server/src/test/java/demo/user/AdminEmailPolicyTest.java
```

教学中假设 Vue 页面 → users.ts → Controller → AdminUserService → Repository。
权限拦截发生在业务写入之前；ProfileService 采用独立入口。本段仅用于解释定位方法。

## 样例请求与状态

- 新增：`POST /api/admin/users`。
- 编辑：`PUT /api/admin/users/U-HIST-01`。这是本案例的管理表单保存语义；编辑也要求提供邮箱，不是 PATCH 式省略保留规则。
- 查询：`GET /api/admin/users/U-HIST-01`。
- 假设旧接口约定：成功 200；参数失败 400，示例体 `{"field":"email","message":"请输入邮箱"}`；无维护权限 403。
- 教学数据：U-HIST-01 初始 `{"displayName":"历史用户","email":null}`，U-VALID-01 初始邮箱 `old@example.com`。
- 教学已知格式点：`alice@example.com` 可接受、`a b@example.com` 拒绝。完整格式／唯一性策略未给出，不能称其回归完成。
- 框架示意选 JUnit 5／Maven 和 Playwright；没有真实 pom.xml、package.json 或运行环境。

## 版本片段

DEMO-BASE 假设对非空邮箱已有格式检查，但新增／编辑都允许空值。

DEMO-CHANGE-A 的错误是：编辑时先用非空判断跳过了必填校验。以下是服务方法内部的节选，不是完整可编译项目。

```java
// 新增方法：所有请求都会校验。
cmd.setEmail(adminEmailPolicy.requiredAndNormalize(cmd.getEmail()));
repository.insert(cmd);

// 编辑方法：省略 email 或传 null 时，错误地跳过必填。
if (cmd.getEmail() != null) {
    cmd.setEmail(adminEmailPolicy.requiredAndNormalize(cmd.getEmail()));
}
repository.update(cmd);
```

DEMO-FIX-B 的编辑方法节选：

```java
// 已确认编辑保存也必须提供邮箱；在任何写入前校验。
cmd.setEmail(adminEmailPolicy.requiredAndNormalize(cmd.getEmail()));
repository.update(cmd);
```

`requiredAndNormalize` 的教学契约：null／省略先拒绝；清理首尾约定空白后为空也拒绝；其余交给原有格式规则；返回清理后的值。不得把清理变成删除内部空格、自动小写化，或把管理端必填加到全局用户实体。

## 读样例时的三件事

1. 图上的节点要在真实工作中补成准确的文件、符号和调用证据；不能把这张虚构图交给 Agent 当真实项目事实。
2. DEV 首次自测样例漏掉“编辑时省略邮箱”，因此能展示 TEST 如何从 AC 独立发现缺陷；这不是推荐的开发检查标准。
3. 文档中的版本、数据和状态只是叙事约定，没有真实提交、日志、测试账户或可连接 API。

