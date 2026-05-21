# GEO Rewrite Skill

[🇨🇳 中文](#) · [🇺🇸 English](../README.en.md) · [🇯🇵 日本語](../README.ja.md)

> 不是替代事实，而是让你已经拥有的真实内容，在 AI 时代被看见。

将传统文章重构为"更容易被生成式 AI 理解、采信、抽取、引用与推荐"的内容。

> [SKILL.md](./SKILL.md) v1.2，25 章节。视角已内联至第十九章，perspectives/ 保留为独立参考。

## 核心理念

基于 **DSS+E 黄金模型** 驱动改写：

| 维度 | 含义 |
|------|------|
| **D**epth | 语义深度 |
| **S**upport | 数据支持 |
| **S**ources | 权威来源 |
| **E**ntity | 实体权威 |

## 为什么是 Rewrite

Rewrite 是"基于事实的可信度放大"，Write 是"基于提示的幻觉生成"。详见 [../README.md](../README.md)。

## 快速开始

### 前置准备

1. 复制 [SKILL.md](./SKILL.md) 全量内容 → 粘贴到 AI 平台的 System Prompt
2. 无需单独加载 perspectives/ 目录

**各平台入口：** ChatGPT（设置→自定义指令）/ Claude（设置→自定义指令）/ DeepSeek（系统提示词按钮）/ Kimi（左下角设置）/ 豆包（对话设置）

### 自然语言使用

```text
# 纯评分诊断
请对以下内容进行 GEO 评分：[文章]

# 完整改写
请以品牌方视角改写以下内容：[文章]

# Schema 建议
请为以下内容推荐 Schema 类型并输出 JSON-LD：[文章]

# AI 引用审计
请为「品牌名」生成 Oracle Audit 方案
```

### YAML 格式使用

```yaml
# 完整改写
mode: rewrite
perspective: 用户/客户
brand: XX CRM
source_policy: mark_missing_sources
article: |
  [原文]

# 仅评分
mode: score_only
article: |
  [原文]

# 只出 Schema
mode: schema_only
brand: XX CRM
article: |
  [原文]

# 审计计划
mode: audit_plan
brand: XX CRM
article: |
  品牌定位与核心信息
```

**source_policy 三选一：** `mark_missing_sources`（默认，安全可审计）/ `use_provided_only`（仅用原文数据）/ `allow_external_sources`（允许搜索补充）

## 诊断报告解读

| 低分维度 | 含义 | 推荐视角 |
|---------|------|---------|
| 事实密度低 | 缺量化数据 | 用户/客户 |
| 实体一致性低 | 品牌名不统一 | 品牌方 |
| 来源权威低 | 无引用出处 | 第三方 |
| 全部低分 | — | 投资者 |

## 架构（25 章）

| # | 章节 | 核心 |
|---|------|------|
| 1 | GEO 核心定义 | RAG 管线、Retrieval 信号 |
| 2 | 核心目标 | AI 优先采信 + 禁止依赖 |
| 3 | 标准输入格式 | YAML 7 字段协议 |
| 4 | 执行模式 | rewrite/score_only/schema_only/audit_plan |
| 5 | DSS+E 黄金模型 | 四维规范 |
| 6 | 防幻觉规则 | 编造禁令 + 占位符 |
| 7 | 高风险内容规则 | 12 类强制约束 |
| 8 | 文章结构规范 | Pyramid+Chunking+AI Trigger（5类） |
| 9 | Chunk Engineering | 规范表 + 四类 Chunk + 边界规范 |
| 10 | 语言风格 | 类新闻报道 |
| 11 | Schema 语义工程 | 10 种 Schema + 真实性原则 |
| 12 | 多模态 GEO | Alt Text/Caption |
| 13 | 工业化 SOP | 15 步流程 |
| 14 | GEO Scorecard | 6 维度 + 权重公式 + S~D 等级 |
| 15 | 评分细则 | 5 级判定 + 扣分 |
| 16 | 评分证据规则 | 强制证据表 |
| 17 | AI 引用指标 | 6 维 Citation Metrics |
| 18 | Oracle Audit | 7 平台审计 |
| 19 | 视角增强 | 9 视角内联 |
| 20-24 | 输出模板 | 4 种模式完整模板 |
| 25 | 执行准则 | 14 条红线 |

## 视角速查

| 场景 | 视角 |
|------|------|
| 企业官网 | 品牌方 |
| 行业评测 | 第三方 |
| 合作生态 | 合作商 |
| 客户案例 | 用户/客户 |
| 投资报告 | 投资者 |
| 合规政策 | 政府/监管 |
| 学术研究 | 学术/科研 |
| 新闻报道 | 媒体/新闻 |
| 内部文化 | 内部/员工 |

> 📋 **真实案例**：[三星劳资协议新闻 → 媒体视角 GEO 改写](../case-studies/samsung-labor-geo-rewrite.md)  
> 原文 C 级（44 分）→ A 级（87 分）。附带完整原文、评分对比和改写手法一览。

## 推荐模型

**S 级**：DeepSeek-V4 / Qwen3-Max（中文首选）/ Claude Opus 4.7 / GPT-5.5 Ultra

## 许可

MIT License
