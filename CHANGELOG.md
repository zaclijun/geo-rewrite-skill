# Changelog

## v1.2 (2026-05-21)

### Added

- **标准输入格式**（第三章）：YAML 协议（mode/perspective/brand/product/source_policy/output_length/need_schema 7 字段）
- **执行模式定义**（第四章）：rewrite / score_only / schema_only / audit_plan 四种精确模式
- **来源与数据防幻觉规则**（第六章）：编造禁令 + 数据使用优先级 + 无法验证处理 + 来源占位符
- **高风险内容处理规则**（第七章）：医疗/法律/金融/投资等 12 类高风险主题的强制约束
- **Schema 真实性原则**（第十一章）：禁止虚构 FAQ/评分/评价/价格/作者等
- **Schema 匹配原则**（第十一章）：每种 Schema 仅当正文包含对应内容时使用
- **评分证据规则**（第十六章）：强制每个评分维度附带原文证据和优化建议
- **GEO 效果表达限制**（第一章）：可表达/禁止表达的明确边界
- **完整输出模板**（第二十一~二十四章）：rewrite / score_only / schema_only / audit_plan 四种模式的结构化 Markdown 模板
- **视角内联**（第十九章）：9 个视角从外部 perspectives/ 文件内联至 SKILL.md，总表 + 各视角适用/强化/避免
- **最终执行准则**（第二十五章）：14 条红线
- **CHANGELOG.md** 独立文件

### Changed

- SKILL.md 从 15 章 + 附录 A 重构为 25 章节，章节编号全部重新编排
- 内容工业化 SOP 从 14 步扩展为 15 步（新增"识别核心实体"步骤）
- 视角从 `{{PERSPECTIVE_PLUGIN}}` 占位符改为完整内联
- Schema 种类从 7 种扩展到 10 种（新增 ResearchProject Schema）
- YAML 版本号 `1.1` → `1.2`
- YAML description 新增"抽取"、"纯评分诊断"、"Schema 语义优化"、"Oracle Audit 审计"
- README 全部 4 个文件重新生成，架构章节更新为 25 章节表
- README 视角插件层说明：perspectives/ 目录从"加载源"改为"独立参考文档"
- 评分等级描述从"AI 优先采信级"调整为"AI 优先采信潜力级"（避免绝对化承诺）

### Fixed

- SKILL.md 缺少输入格式规范 → YAML 协议
- SKILL.md 缺少防幻觉显式禁令 → 第六章
- SKILL.md 缺少高风险内容保护 → 第七章
- SKILL.md 缺少 Schema 真实性约束 → 第十一章
- Schema JSON 示例中的 backtick 污染 → 已清理
- 评分卡缺少证据强制要求 → 第十六章
- Oracle Audit 缺少可操作模板 → 第二十四章

### Removed

- `{{PERSPECTIVE_PLUGIN}}` 占位符机制（视角已内联）

---

## v1.1 (2026-05-21)

### Added

- **AI 检索与引用机制**（SKILL.md 新章节）：解释生成式 AI 的 Chunk→Embedding→Retrieval→Re-ranking→Generation 管线，明确 GEO 的本质是 AI Retrieval Optimization
- **Chunk Engineering 内容切片工程**（SKILL.md 新章节）：Chunk 规范表、四种 AI 偏好 Chunk 类型、Anti-Patterns 反模式
- **AI 引用指标**（SKILL.md 新章节）：6 维度 Citation Metrics + 引用等级映射
- **Oracle Audit AI 引用审计**（SKILL.md 新章节）：5 平台审计矩阵 + 审计指标定义
- **附录 A：Schema 实现示例**（SKILL.md 新增）：5 个 JSON-LD Schema 完整代码示例
- **叙事主权（Narrative Ownership）**：README 三语版本新增终局竞争章节
- **README 多语言**：English（README.en.md）+ 日本語（README.ja.md）
- **GEO Scorecard 评分卡**：6 维度评分细则 + 纯评分独立模式
- **推荐模型**：S/A/B 三级体系，DeepSeek-V4 / Qwen3-Max 列入 S 级
- **边界声明 + 扩展性**：4 条不做什么 + 本地工具/平台集成/CI/CD 管线

### Changed

- SKILL.md 从 9 章扩展为 13 章 + 附录 A
- 内容工业化 SOP 从 10 步扩展为 12 步（含评分前后置）
- SECTION 编号重新对齐（十→十，十一→十三）
- README 语言切换栏（🇨🇳 🇺🇸 🇯🇵）
- 推荐模型章节全部更新至 2026 年 5 月最新模型名称

### Fixed

- SKILL.md 第九章 Review Schema 和 NewsArticle Schema 缺失 → 已补充
- SKILL.md 顶部新增 YAML frontmatter（name/description/tags/version）

---

## v1.0 (2026-05-20)

### Added

- 初始版本发布
- DSS+E 黄金模型（Depth / Support / Sources / Entity）
- 9 个可插拔视角：品牌方、第三方、合作商、用户/客户、投资者、政府/监管、学术/科研、媒体/新闻、内部/员工
- 内容工业化 SOP 10 步改写流程
- Schema 语义工程章节
- 多模态 GEO 优化规范
