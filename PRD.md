# ZenNote - Daily Note 独立应用 PRD

## 产品定位
- **ZenNote** 是面向「日记/每日笔记」场景的独立应用，专注高效率记录与结构化整理。
- 与 `yourPXO` 并列管理；`yourPXO` 已内置 ZenNote 能力，ZenNote 提供「分体使用」选项给坚持专注写作/日志工作流的用户。
- 集成 `byenatOS`，将笔记内容映射为 HiNATA，驱动 PSP 持续个性化迭代。
- 同一账号登录多个 `byenatOS` 能力 App（如 `yourPXO`、`ZenRead`、`ZenNote`）时，默认共享唯一 HiNATA 与 PSP（账号级），支持 App 级 Overlay（可选）。

## 目标用户
- 每日写作、复盘与规划用户
- 需要 Markdown、语音转文字与模板化的用户

## 核心能力
1) 快速记录
- 富文本/Markdown、语音转文字、图片与文件附件
- 模板与快捷短语、双向链接、今日/本周视图

2) 智能整理
- 自动主题提取、情感分析、关键词与标签建议
- 时间线、项目/领域视图、回顾与复盘

3) HiNATA 映射（byenatOS）
- 规则：NoteTitle/KeySentence → `Highlight`；FullNote/Details → `Note`
- 元数据：`Source=zennote`、`Tag=[journal, source]`、`Access=Private`（默认）
- 本地算子：摘要、高亮建议、实体抽取、嵌入、质量校验

4) 检索与回顾
- 全文检索、标签/情感/主题过滤、周期性回顾

## 系统集成与共享策略
- 账号级共享（默认）：同一账号下的 App 共享唯一 HiNATA 与 PSP。
- App 级 Overlay（可选）：叠加 `ZenNote` 的输出风格（写作语气、摘要长度、结构化段落等）。
- PSP Scope：`Scope=account`（默认）或 `Scope=app`（合成账号 PSP + ZenNote Overlay）。

## 关键交互流（概要）
1) 新建/编辑日记 → 生成/更新 HiNATA → 算子增强 → 校验通过 → 入库（账号级）
2) 周/月复盘 → 派生总结 → 产出 QnA → 归档为 HiNATA（Q→Highlight, A→Note）→ 推动 PSP 迭代

## 非功能性要求
- 隐私：本地优先；向 `byenatOS` 无状态调用，不含用户标识
- 性能：新建笔记 < 200ms；检索 < 300ms；离线使用

## 与 yourPXO 的关系
- `yourPXO` 包含 ZenNote 的 Daily Note 能力；ZenNote 作为专业写作独立 App 与 `yourPXO` 并列，共享同账号的 HiNATA/PSP，构成多输入源的工作区形态。


## 并行关系与选择建议
- **All-In-One 工作流**：优先选择 `yourPXO`，在单一应用内获得收集、阅读、写作的一体化体验。
- **专注 Daily Note**：选择 `ZenNote`，保持写作/复盘流程的专注与极简。
- **自由切换**：同一账号下，`yourPXO`、`ZenNote`、`ZenRead` 默认共享「唯一」HiNATA 与 PSP（账号级），可随时在应用之间无缝切换，无需导入/导出。
- **App 级 Overlay**：可选开启 `ZenNote` 的写作风格 Overlay，不影响账号级 PSP 的连续性。

## 跨应用无缝切换（HiNATA/PSP 共享）
- **登录与共享**：使用同一账号登录 `ZenNote` 与 `yourPXO` 时，历史在 `ZenNote` 中积累的 HiNATA 与 PSP 将自动在 `yourPXO` 中可用。
- **Scope 策略**：默认 `Scope=Account`；如启用 `Scope=App`，则在账号级 PSP 基础上叠加 `ZenNote` Overlay 进行组合。
- **一致性保障**：跨应用写作产生的高亮与笔记按映射规则入库，保证检索、回顾与 AI 对话上下文一致。

## AI Chatbot 个性化（基于 PSP）
- `ZenNote` 的写作偏好、结构化模板等将沉淀为 PSP 的一部分；在 `yourPXO` 或其他 `byenatOS` 能力 App 中进行 AI 对话时，默认继承该个性化设定。
- 若开启 App 级 Overlay，则在对话侧以「账号级 PSP + ZenNote Overlay」进行推理与响应。


