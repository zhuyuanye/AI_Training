# DEV 02｜建立项目地图：输入输出示例

[对应提示词](../../DEV/02-build-project-map.md) · 实际工作模式：**Plan**

> 静态教学样例。源码路径、版本、评审与结果均为虚构；未修改或运行业务项目。

## 输入示例

输入 CODE-v1 的示意目录与需求 US-01/02。要求先定位与需求有关的模块，不逐文件复述全仓库。
以下所有路径都是教学假设。

## 输出产物示例

### dev/project-map.md

| 职责 | 示例文件／符号 | 作用与关注点 |
|---|---|---|
| 表单 | web/src/views/admin/UserEdit.vue | 必填提示、历史用户提醒、提交值 |
| API 封装 | web/src/api/users.ts | 新增／编辑请求及错误展示 |
| 接口入口 | AdminUserController.create/update | 权限、参数绑定、调用服务 |
| 业务逻辑 | AdminUserService.create/update | 管理端必填、先校验后写入 |
| 格式策略 | AdminEmailPolicy.requiredAndNormalize | 首尾清理、必填、委托既有格式 |
| 持久化 | UserRepository.insert/update | 数据写入和失败无变化 |
| 范围外 | ProfileService | 检查是否被共享校验波及 |

调用关系：UserEdit → users.ts → Controller → Service → Repository。
权限与既有格式分别作为前置控制与规则依赖，不把它们混成页面职责。

地图状态：教学模型；真实产物应补准确相对路径、符号、引用证据和未知项。

## 讲解检查点

代码图谱先帮助新人找到入口、调用和风险点；越大越全不一定越有用。

[DEV 示例索引](README.md) · [全部示例](../README.md)

