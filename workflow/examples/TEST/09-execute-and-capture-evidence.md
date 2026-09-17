# TEST 09｜展示执行与证据样例：输入输出示例

[对应提示词](../../TEST/09-execute-and-capture-evidence.md) · 实际工作模式：**Build**

> 静态教学样例；业务确认、实现、脚本与结果均为示意，未执行真实测试。

## 输入示例

教学输入：DEMO-CHANGE-A、AC-v1、TC-v1；假设上一阶段完整脚本与环境已具备。
本次课堂只阅读预制的结果样例。**真实执行数为 0；下面的日志、XML 和目录均是文本示意。**

## 输出产物示例

### test/execution-index.md

| 模拟批次 | 代码 | API | UI | 人工 | 未进入执行 |
|---|---|---|---|---|---|
| SIM-TEST-A-01 | DEMO-CHANGE-A | 12 项：10 通过、1 失败、1 错误 | 1 通过 | 2 通过 | TC-16 阻塞 |

API 进程示例退出码 1，UI 示例退出码 0。API XML 的 error 指框架报告异常，根因分类留给下一步。
TC-05 失败；TC-11 登录 fixture 401，未到目标断言；人工结果同样是教学假设，并非有人真实执行过。

### test/runs/SIM-TEST-A-01/run.md

示例元数据：需求／AC／TC 版本、代码标签、工作区差异、环境、命令、工作目录、起止时间、原进程退出码。
本例环境地址与真实时间：不适用；不是实际测试。不能为补齐表格编造提交号或凭据。

### api.log 文本示例（没有生成日志文件）

```text
SIMULATED — NOT EXECUTED
TC-05 expected HTTP 400, got 200
TC-05 before: displayName=历史用户, email=null
TC-05 after:  displayName=尝试修改, email=null
TC-11 ERROR: setup login returned 401; business assertions not reached
summary: tests=12, passed=10, failures=1, errors=1, skipped=0
```

### api.xml 形态示例（合成、非框架生成）

```xml
<testsuite name="SIMULATED-API" tests="12" failures="1" errors="1" skipped="0">
  <properties><property name="simulation" value="not-executed"/></properties>
  <testcase name="TC-01"/><testcase name="TC-02"/>
  <testcase name="TC-03"/><testcase name="TC-04"/>
  <testcase name="TC-05"><failure message="expected 400, actual 200"/></testcase>
  <testcase name="TC-06"/><testcase name="TC-07"/>
  <testcase name="TC-08"/><testcase name="TC-09"/>
  <testcase name="TC-10"/>
  <testcase name="TC-11"><error message="fixture login 401"/></testcase>
  <testcase name="TC-12"/>
</testsuite>
```

### UI 与人工记录形态

TC-13：教学假设前端拦空、修正保存成功；真实执行应保留 Trace 与成功截图。
TC-14／15：教学假设代表检查通过；记录人、检查范围、操作和结果应在真实执行后填写。

### evidence-manifest.md 形态

| 预期路径 | 用途／追溯 | 本案例实际文件 |
|---|---|---|
| api.log、api.xml | API 12 项；定位 TC-05/11 | 不存在，仅以上文本 |
| ui/trace.zip、ui/success.png | TC-13 核心流程 | 不存在，不造替代图片 |
| manual.md | TC-14/15 的检查记录 | 不存在，仅教学设定 |

真实清单需从现存文件获取大小、SHA-256 和时间；这里不提供虚构值。
清理记录形态：临时用户标识、删除结果、残留与处理人。本次没创建数据，因此无实际清理动作。

## 讲解检查点

打开这页就能讲日志、XML 和证据索引，不必现场跑测试；同时强调真实工作必须拿真实文件核验。

[TEST 示例索引](README.md) · [全部示例](../README.md)

