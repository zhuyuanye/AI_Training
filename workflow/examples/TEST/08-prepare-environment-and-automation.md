# TEST 08｜准备自动化与人工检查：输入输出示例

[对应提示词](../../TEST/08-prepare-environment-and-automation.md) · 实际工作模式：**Plan → Build**

> 静态教学样例；业务确认、实现、脚本与结果均为示意，未执行真实测试。

## 输入示例

输入 TC-v1、分层策略、CODE-v1 的教学接口和权限约定。
本次分享不需要实际环境；下面脚本为结构节选，辅助展示 Agent 应生成什么，**不是可直接运行的完整项目**。

## 输出产物示例

### test/automation-plan.md（Plan）

优先实现 TC-05，以历史用户和独立快照验证疑似编辑绕过；再覆盖 API 其他 11 项。
UI 实现 TC-13。数据每例独立；读取凭据使用真实环境配置，不写入报告。
真实执行前必须完成 fixture、客户端、断言与查询权限核验。

### test/automation/README.md（Build 产物样例）

框架示意：JUnit 5 API、Playwright UI。
API 接入层提供 fixtures / adminApi / readerApi / cleanup。
示例命令形态：server 下 mvn test；web 下 npx playwright test。以真实项目脚本与输出目录为准，课堂不执行。
无真实依赖清单、认证和 fixture 实现，因此这些片段不能直接运行。

### test/automation/api/（测试方法节选）

```java
// 教学伪装配：fixtures/adminApi/readerApi 等须由真实项目提供。
@Test void rejectsEditWithoutEmailAndKeepsData() {
    var user = fixtures.historicalUserWithNullEmail();
    try {
        var before = readerApi.get(user.id());
        var response = adminApi.update(user.id(),
            Map.of("displayName", "尝试修改")); // 故意省略 email
        var after = readerApi.get(user.id()); // 在断言前取快照，失败也保留实际值
        assertAll(
            () -> assertEquals(400, response.status()), // CODE-v1 的假设约定
            () -> assertEquals("email", response.errorField()),
            () -> assertEquals(before, after)
        );
    } finally {
        fixtures.remove(user.id()); // 正式实现还需保留清理失败信息
    }
}
```

### test/automation/ui/（核心流程节选）

```typescript
// 编辑页已登录、独立历史用户已准备；selectors 与配置需按真实页面适配。
await page.getByRole('button', { name: '保存' }).click();
await expect(page.getByText('请输入邮箱', { exact: true })).toBeVisible();
await page.getByLabel('邮箱', { exact: true }).fill(' alice@example.com ');
await page.getByRole('button', { name: '保存' }).click();
// 完整脚本还应重新打开该用户并断言持久化结果。
await expect(page.getByText('保存成功', { exact: true })).toBeVisible();
```

正式实现需在配置中开启 Trace，按真实页面保存关键截图；API／UI 要补完整数据准备、持久化断言和清理。本例节选不作为自动化完成证据。

### test/manual-checklist.md

TC-14：提示可理解、权限入口不扩大、已知其他字段行为不变。
TC-15：范围外入口的调用链、代表操作与通知行为对照。
两项均初始“未执行”；只有实际人做了检查才填写结果。

## 讲解检查点

生成脚本、脚本可运行、实际执行通过是三个不同状态。这里展示产物形态，现场不安装工具。

[TEST 示例索引](README.md) · [全部示例](../README.md)

