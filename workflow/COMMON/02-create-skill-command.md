# 复用示例 02｜生成 Skill 与 Command

静态分享请看[本步骤的输入输出产物示例](../examples/COMMON/02-create-skill-command.md)；本次不需要现场执行。

让 Agent 根据已核对的使用经验创建 OpenCode 项目级复用文件。这里只提供演示用提示词，执行后才会在你指定的项目生成真实配置。

## 使用模式

**Build**。需要创建 Skill 和 Command 文件。生成的 Command 也使用 `agent: build`，因为它会保存候选需求和澄清问题文档。

## 输入

- `{{产物目录}}/reuse/method-review.md`。
- 已核对的方法范围：`{{方法确认说明}}`。
- OpenCode 目标项目目录：`{{目标项目目录}}`。

## 输出

- `{{目标项目目录}}/.opencode/skills/meeting-discovery/SKILL.md`。
- `{{目标项目目录}}/.opencode/commands/meeting-discover.md`。
- `{{产物目录}}/reuse/creation-review.md`，记录变更与静态检查。

## 可复制提示词（Build）

```text
请根据 {{产物目录}}/reuse/method-review.md 中已经核对的方法，为 OpenCode 生成项目级 Skill 与 Command。
目标项目：{{目标项目目录}}
本轮方法确认说明：{{方法确认说明}}

先读取目标项目适用规则，检查同名文件是否存在。已有同名内容时保留人工编辑，说明相关差异再做限定更新；无关旧文件不要覆盖。

1. 创建 .opencode/skills/meeting-discovery/SKILL.md。
   YAML frontmatter 必须包含 name: meeting-discovery 和明确说明适用场景的 description；名称与目录相同。
   正文包含触发条件、输入、工作步骤、输出模板、来源与状态区分、最多三个优先问题、完成条件及不适用范围。
   仅写已确认的通用方法；未知业务规则只能标待确认，不能推断成正式 AC。
   本技能只负责候选需求与澄清问题，不自动扩展生成 PRD、原型或产品业务代码。

2. 创建 .opencode/commands/meeting-discover.md。
   frontmatter 包含清楚的 description 和 agent: build。
   正文要求读取当前项目规则、明确加载 meeting-discovery 技能，并通过 $ARGUMENTS 接收本轮输入材料路径和产物目录。
   Command 保持简短，把工作方法放在 Skill 中。结果保存到本轮指定产物目录，保留草案状态及来源，不把生成候选稿当产品确认。
   不要使用 mode: plan 或 mode: build 替代 agent 字段，不固定模型，也不修改全局权限或配置。

3. 静态检查名称、路径、frontmatter、参数说明与调用的技能名称是否一致。
   写 {{产物目录}}/reuse/creation-review.md，列实际创建或修改的文件、检查结果和使用方法。
   区分“文件已生成／格式已检查”与“已经在新会话实际调用成功”。

本轮只生成与检查复用资产，不运行新的业务需求分析。没有已核对的方法输入时先指出缺项，不根据空模板编造团队经验。
```

## 人工检查与下一步

确认 Skill 保存方法，Command 只提供入口，业务规则没有被写死。文件存在不代表已被运行中的 OpenCode 会话发现；下一步使用新会话验证实际加载和执行。

格式依据：[OpenCode Skills](https://opencode.ai/docs/zh-cn/skills/)与 [Commands](https://opencode.ai/docs/zh-cn/commands/)。

[下一步：新会话换材料验证](03-verify-reuse.md) · [返回总索引](../README.md)
