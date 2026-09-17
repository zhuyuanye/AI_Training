# BA / DEV / TEST 工作流图片生成提示词

生成方式：内置 image_gen 工具，每张独立生成。目标：用于 PPT 的 16:9 横版流程图。

## BA

```text
Use case: infographic-diagram.
Create ONE polished, presentation-ready workflow diagram image for a Chinese team training deck. This is a final flat infographic, not a photo of a slide or laptop. Landscape 16:9, target 3840 x 2160 pixels, high resolution, extremely crisp readable Simplified Chinese typography. Full-bleed clean white background, generous safe margins, dark navy text, pale blue process boxes, pale amber manual-confirmation boxes, pale mint deliverable boxes. Minimal business consulting aesthetic, flat vector-like shapes, no 3D, no illustrations, no gradients, no watermarks or invented logos. Modern Chinese sans-serif equivalent to Noto Sans SC. Consistent typography, alignment and spacing.
Layout: large role title at top left; small subtitle beneath it. Main flow uses FOUR equal-width vertical stage lanes across the slide, with spacious white gutters. Each lane has a restrained blue stage heading and THREE numbered process boxes stacked vertically, linked with clear downward arrows. Between stage lanes use a clear left-to-right connector in the gutter indicating stage order. Each process box has a bold short title and 1–3 lines of supporting text, legible at presentation size. Use the exact numbered labels and Chinese text below. Human review steps are amber; deliverables mint. Use dashed muted orange return arrows with concise labels, routed through margins without crossing text, only as specified. A thin full-width footer contains the shared handoff statement and a small legend: “蓝色：Agent 执行   黄色：人工确认   绿色：交付产物   虚线：回退或复测”. Do not duplicate nodes, invent steps, or add extra prose. Maintain strong visual hierarchy with text large enough for a conference-room screen. All connectors must clearly attach to correct nodes; avoid crossing and ambiguity. Render only the specified slide, one image.
Title verbatim: “BA｜从会议转写到可交付需求”
Subtitle verbatim: “OpenCode · Agent 辅助工作流”
FOUR STAGES / 12 BOXES, in this order:
Stage 1 heading “01  理解输入与现状”
Box 01 title “准备输入”; supporting “Teams 会议转写\n现有页面、业务规则、历史需求”
Box 02 title “提取需求与依据”; supporting “保留来源或时间戳\n区分决策、建议、冲突与待确认”
Box 03 title “明确本次变化”; supporting “现状 → 目标\n新增、修改、保留、不做”
Stage 2 heading “02  澄清业务需求”
Box 04 title “生成澄清问题”; supporting “优先处理影响范围、规则与方案的问题”
Box 05 title “BA／产品确认”; supporting “确认关键规则、边界与范围”; AMBER HUMAN CHECKPOINT
Box 06 title “记录确认结果”; supporting “补充资料与决策依据\n保留尚未解决的问题”
Stage 3 heading “03  文档与原型评审”
Box 07 title “形成需求草稿”; supporting “User Story ＋ PRD\n关联规则与需求来源”
Box 08 title “生成 HTML 原型”; supporting “主流程、异常状态、权限差异”
Box 09 title “业务／产品评审”; supporting “检查需求与原型是否一致、完整”; AMBER HUMAN CHECKPOINT
Stage 4 heading “04  验收与交接”
Box 10 title “三方联合评审 AC”; supporting “BA：业务含义 · DEV：可实现性\nTEST：可测试性”; AMBER HUMAN CHECKPOINT
Box 11 title “确认需求基线”; supporting “User Story · PRD · AC · HTML 原型”; MINT DELIVERABLE
Box 12 title “交接 DEV 与 TEST”; supporting “同步需求变更、待办问题与影响”; MINT DELIVERABLE
Feedback arrows: from box 05 back to box 04, label “需澄清”; from box 09 back to box 07, label “需修订”; from box 10 back toward stage 2, label “规则有缺口”. Forward progress out of checkpoints means confirmed/pass. Feedback paths are subtle and subordinate, but clear.
Footer shared handoff statement verbatim: “共同基线：三方确认同一份 AC，需求变更同步更新文档、原型与用例。”
Small top-right slide index “01 / 03”.
Important: literal \n in the specification means actual visible line breaks; never print backslashes or the characters n as a line-break code.
```

## DEV

```text
Use case: infographic-diagram.
Create ONE polished, presentation-ready workflow diagram image for a Chinese team training deck. This is a final flat infographic, not a photo of a slide or laptop. Landscape 16:9, target 3840 x 2160 pixels, high resolution, extremely crisp readable Simplified Chinese typography. Full-bleed clean white background, generous safe margins, dark navy text, pale blue process boxes, pale amber manual-confirmation boxes, pale mint deliverable boxes. Minimal business consulting aesthetic, flat vector-like shapes, no 3D, no illustrations, no gradients, no watermarks or invented logos. Modern Chinese sans-serif equivalent to Noto Sans SC. Consistent typography, alignment and spacing.
Layout: large role title at top left; small subtitle beneath it. Main flow uses FOUR equal-width vertical stage lanes across the slide, with spacious white gutters. Each lane has a restrained blue stage heading and THREE numbered process boxes stacked vertically, linked with clear downward arrows. Between stage lanes use a clear left-to-right connector in the gutter indicating stage order. Each process box has a bold short title and 1–3 lines of supporting text, legible at presentation size. Use the exact numbered labels and Chinese text below. Human review steps are amber; deliverables mint. Use dashed muted orange return arrows with concise labels, routed through margins without crossing text, only as specified. A thin full-width footer contains the shared handoff statement and a small legend: “蓝色：Agent 执行   黄色：人工确认   绿色：交付产物   虚线：回退或复测”. Do not duplicate nodes, invent steps, or add extra prose. Maintain strong visual hierarchy with text large enough for a conference-room screen. All connectors must clearly attach to correct nodes; avoid crossing and ambiguity. Render only the specified slide, one image.
Title verbatim: “DEV｜从理解代码到小步交付”
Subtitle verbatim: “OpenCode · Agent 辅助工作流”
FOUR STAGES / 12 BOXES:
Stage 1 heading “01  熟悉项目与需求”
Box 01 title “接收开发输入”; supporting “现有代码库\n已确认的 Story、PRD、AC、原型”
Box 02 title “建立项目地图”; supporting “首次梳理，后续按需更新\n模块、入口、启动与测试方式”
Box 03 title “定位相关实现”; supporting “页面 → API → 服务 → 数据\n确认当前行为与需求差异”
Stage 2 heading “02  确认基线与方案”
Box 04 title “运行修改前检查”; supporting “相关测试、构建与启动检查\n记录已有失败和环境问题”
Box 05 title “分析风险与方案”; supporting “兼容、权限、数据与回归范围\n明确修改边界和验证方式”
Box 06 title “开发者评审”; supporting “确认方案、范围与完成条件\n业务规则变化交 BA／产品确认”; AMBER HUMAN CHECKPOINT
Stage 3 heading “03  小步实现与检查”
Box 07 title “拆分小任务”; supporting “每个任务都有可检查的完成条件”
Box 08 title “实现一个小任务”; supporting “修改代码，补充必要测试”
Box 09 title “运行检查并看 diff”; supporting “测试、构建及其他检查\n检查逻辑、遗漏与无关变更”
Stage 4 heading “04  验证完成与交付”
Box 10 title “确认符合方案”; supporting “开发者检查范围与变更\n确认没有越界”; AMBER HUMAN CHECKPOINT
Box 11 title “完成任务与约定验证”; supporting “汇总实际检查结果\n标明未验证项与已知风险”
Box 12 title “交付 TEST”; supporting “实现、变更说明、自测证据\n环境或数据变化、剩余风险”; MINT DELIVERABLE
Feedback arrows: from 06 back to 05 labeled “调整方案”; from 09 back to 08 labeled “本次修改失败”; a small subordinate note directly near 09 verbatim “已有或环境问题 → 重新确认基线”; from 10 back to 08 labeled “需修正”; from 11 back to 08 labeled “还有任务／验证”. Make these return arrows clean and non-crossing using a shared outer return track if necessary.
Footer shared handoff statement verbatim: “开发依据：三方确认的需求与 AC；交付说明必须包含实际验证证据。”
Small top-right slide index “02 / 03”.
Important: literal \n in the specification means actual visible line breaks; never print backslashes or the characters n as a line-break code.
```

## TEST

```text
Use case: infographic-diagram.
Create ONE polished, presentation-ready workflow diagram image for a Chinese team training deck. This is a final flat infographic, not a photo of a slide or laptop. Landscape 16:9, target 3840 x 2160 pixels, high resolution, extremely crisp readable Simplified Chinese typography. Full-bleed clean white background, generous safe margins, dark navy text, pale blue process boxes, pale amber manual-confirmation boxes, pale mint deliverable boxes. Minimal business consulting aesthetic, flat vector-like shapes, no 3D, no illustrations, no gradients, no watermarks or invented logos. Modern Chinese sans-serif equivalent to Noto Sans SC. Consistent typography, alignment and spacing.
Layout: large role title at top left; small subtitle beneath it. Main flow uses FOUR equal-width vertical stage lanes across the slide, with spacious white gutters. Each lane has a restrained blue stage heading and THREE numbered process boxes stacked vertically, linked with clear downward arrows. Between stage lanes use a clear left-to-right connector in the gutter indicating stage order. Each process box has a bold short title and 1–3 lines of supporting text, legible at presentation size. Use the exact numbered labels and Chinese text below. Human review steps are amber; deliverables mint. Use dashed muted orange return arrows with concise labels, routed through margins without crossing text, only as specified. A thin full-width footer contains the shared handoff statement and a small legend: “蓝色：Agent 执行   黄色：人工确认   绿色：交付产物   虚线：回退或复测”. Do not duplicate nodes, invent steps, or add extra prose. Maintain strong visual hierarchy with text large enough for a conference-room screen. All connectors must clearly attach to correct nodes; avoid crossing and ambiguity. Render only the specified slide, one image.
Title verbatim: “TEST｜从独立分析到证据与结论”
Subtitle verbatim: “OpenCode · Agent 辅助工作流”
FOUR STAGES / 12 BOXES:
Stage 1 heading “01  独立分析与澄清”
Box 01 title “接收原始需求”; supporting “业务需求与现状材料\n不预置 AC 和测试答案”
Box 02 title “分析规则与风险”; supporting “识别歧义、边界、异常与遗漏”
Box 03 title “BA／产品现场确认”; supporting “确认业务问题，记录决策依据”; AMBER HUMAN CHECKPOINT
Stage 2 heading “02  共同验收与设计”
Box 04 title “生成并评审 AC”; supporting “可测试、可追溯\nBA、DEV、TEST 三方确认”; AMBER HUMAN CHECKPOINT
Box 05 title “设计测试用例”; supporting “正常、异常、边界、相关回归\n建立需求 → AC → 用例关联”
Box 06 title “确定测试分层”; supporting “API 为主 · UI 核心流程\n人工与探索性测试补充”
Stage 3 heading “03  对照实现与执行”
Box 07 title “对照 Java／Vue 实现”; supporting “记录需求差异，补充覆盖场景\n规则冲突交 BA／产品确认”
Box 08 title “准备环境与自动化”; supporting “账号、数据、依赖及清理方式\nAPI 脚本、UI 脚本、人工步骤”
Box 09 title “真实执行并留证”; supporting “运行 API、UI 与人工测试\n保留日志、XML、Trace、截图”
Stage 4 heading “04  诊断、复测与结论”
Box 10 title “诊断异常与阻塞”; supporting “区分产品、脚本、环境问题\n证据不足则保留待定位”
Box 11 title “修复后复测与回归”; supporting “对应责任人处理问题\n复测修复，并检查相关旧功能”
Box 12 title “形成测试结论”; supporting “通过 · 失败 · 阻塞 · 未执行\nAC 覆盖、缺陷证据、剩余风险”; MINT DELIVERABLE
Critical logical connectors: main route 01→02→03→04→05→06→07→08→09. From 09 to 10 label “发现异常”; additionally a clearly separate clean outer forward arrow from 09 straight to 12 labeled “无异常”. 10→11 labeled “可修复”; 11 uses a dashed return arrow to 09 labeled “复测与回归”; 10 also has a distinct outer arrow to 12 labeled “暂未解决／阻塞”. Do NOT draw a success shortcut from 11 directly to 12: retesting must execute again. Add small dashed feedback 04→02 labeled “AC 需补充”; optional 07→03 feedback label “规则冲突” if it can remain uncluttered.
Footer shared handoff statement verbatim: “TEST 在需求阶段参与；UI 单核心流程为本次演示范围；证据关联版本与环境。”
Small top-right slide index “03 / 03”.
Important: literal \n in the specification means actual visible line breaks; never print backslashes or the characters n as a line-break code.
```

