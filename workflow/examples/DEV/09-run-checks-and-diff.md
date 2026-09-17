# DEV 09｜运行检查并查看 diff：输入输出示例

[对应提示词](../../DEV/09-run-checks-and-diff.md) · 实际工作模式：**Build**

> 静态教学样例。源码路径、版本、评审与结果均为虚构；未修改或运行业务项目。

## 输入示例

输入教学变更 DEMO-CHANGE-A。为压缩静态叙事，假设 TASK-02 已按相同小步流程完成前端提醒。
DEV 自测只覆盖旧规则样本、新增空值、规范化和编辑显式空串，漏掉编辑省略字段。

## 输出产物示例

### dev/checks.md

**模拟结果，未实际执行。SIM-DEV-A-01，DEMO-CHANGE-A。**

| 项目 | 模拟结果 |
|---|---|
| 后端单元测试 | 10 项全部通过，原进程退出码 0 |
| 前端构建 | 成功，退出码 0 |
| 后端打包（跳过测试） | 成功，退出码 0；单列，不能重复算测试 |
| diff 范围 | AdminEmailPolicy、AdminUserService、对应测试、UserEdit.vue |
| 范围检查 | 未改实体全局约束、DB、ProfileService、导入或权限配置 |

### dev/runs/SIM-DEV-A-01/（产物形态）

run.md、unit.log、surefire/*.xml、web-build.log、server-package.log、changes.diff。
都是教学路径示意，没有真实文件或哈希。

diff 摘要：新增管理端规范化方法；create 调用；update 仍保留非空条件；Vue 增加必填提示。
覆盖限制：10 个测试是这批样例的数量，不代表完整 AC 覆盖。服务 update 省略字段分支漏测，绿色结果不能发现它。

## 讲解检查点

从绿色数字追问“测了哪些入口和数据”。用数量代替覆盖判断会漏掉关键分支。

[DEV 示例索引](README.md) · [全部示例](../README.md)

