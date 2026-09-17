# 讲师话术｜静态案例版

下面的说法配合[讲师手册](01-runbook.md)。每段展示预制材料，不需要运行 Agent。

## 开场

“今天用一个邮箱必填的需求串起 BA、DEV、TEST。我们重点看提示词需要什么输入、会形成什么产物、哪些地方要人判断。材料都是教学样例，现场不执行，测试结果也明确标为模拟。”

## BA：从原话到业务口径

“先看会议原话。运营提手机号必填，但产品说这轮不承诺，所以不能直接把它写成正式需求。”

展示 [BA 02](../../examples/BA/02-extract-requirements.md)，指向 REQ 与时间戳。

“现在还不知道历史用户只改显示名时是否必须补邮箱。Agent 应该提出问题。这里我们展开预设的产品回复：历史账号照常使用，但管理端编辑保存必须补齐。”

展示 [BA 04](../../examples/BA/04-prepare-clarification.md) → [BA 05](../../examples/BA/05-confirm-business-rules.md) → DEC-04。

## TEST 提前参与

“TEST 此时先拿业务原始材料独立分析。这样它能发现规则和风险，而不是照着 BA 提前给出的测试答案扩写。”

展示 [TEST 02](../../examples/TEST/02-analyze-rules-and-risks.md)。等讨论后再展示共同决策。

## Story、PRD 与 HTML

“Story 写管理员要完成的事情，PRD 写本次变化。HTML 把规则变成能看见的页面状态。页面看起来合理，也不能证明保存接口已经满足要求。”

展示 [BA 07](../../examples/BA/07-draft-story-prd.md)与[原型](../../examples/prototype/index.html)。

## 共同 AC

“BA、TEST 和 DEV 围绕同一份 AC 工作。比如保存失败后数据不变，后面就必须有数据前后对照。旧格式规则还不完整，这项就保留阻塞。”

展示 [AC-v1](../../examples/reference/ac.md)，重点 AC-04、06、09。

## DEV：先找链路，再改小步

“新人先找到表单、接口、服务和数据写入的关系，再判断改哪里。这里的 Java／Vue 路径都是虚构示意，真实工作要给出准确文件与调用证据。”

“看这段首次修改：新增路径总会校验，但编辑路径仍有 if。请求不传邮箱，就跳过了。方案虽然写对了，实现仍可能遗漏。”

展示 [DEV 02](../../examples/DEV/02-build-project-map.md)与[DEV 08](../../examples/DEV/08-implement-one-task.md)。

“这个例子的开发测试绿了，因为漏测了该分支。DEV 10 特意给出一份不完整 review 的反例；正确做法是在这里要求修正，不能把前端会传值作为接口不用校验的理由。”

## TEST：规则、分层与实现对照

“TC-05 来自业务规则：编辑保存也要邮箱，失败数据不变。然后才看代码。API 负责主要规则矩阵，UI 展示一个历史用户纠正后保存的完整流程，人工检查文案与范围外影响。”

展示 [用例表](../../examples/reference/test-cases.md)及[分层](../../examples/TEST/06-choose-test-layers.md)。

## 执行样例与诊断

“假设首次跑出了这份结果：12 个 API 案例，10 通过、1 失败、1 错误。这里是模拟日志和 XML 形态，没有真实日志文件。”

“TC-05 真正到了业务判断，且数据被改了，是产品实现缺陷。TC-11 在准备登录身份时就失败，尚未验证业务，需要继续核对环境，不能直接判业务不通过。”

展示 [TEST 09](../../examples/TEST/09-execute-and-capture-evidence.md)与[TEST 10](../../examples/TEST/10-diagnose-failures.md)。

## 复测与结论

“修复后另建批次，保留首次失败。模拟最新结果是 15 项通过、1 项阻塞。因为旧规则资料仍缺，不能写全部通过或批准上线。真实工作中还需要实际证据支撑这些数字。”

展示 [TEST 11](../../examples/TEST/11-fix-retest-regression.md)和[TEST 12](../../examples/TEST/12-produce-test-conclusion.md)。

## 从提示词沉淀成 Skill 与 Command

“实际工作中，先核对一次使用过程和人工纠正，再提炼方法。Skill 放如何提取来源、区分状态、优先提问；Command 只接材料和输出位置并加载 Skill。”

“这里展示生成后的文件样例。最后换成工单导出：应保留会议分析方法，不能再出现邮箱必填的业务答案。因为今天没有运行，Command 发现和 Skill 加载状态仍然是未验证。”

展示 [COMMON 01—03](../../examples/COMMON/README.md)。

## 结束

“这套资料每一步都有原提示词和输入输出样例。回到自己的项目时，从当前阶段开始，替换成真实材料，检查产物，再进入下一步。需要运行验证的地方，仍要实际运行并保留证据。”

[返回讲师手册](01-runbook.md)
