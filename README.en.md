# GEO Rewrite Skill

[🇨🇳 中文](./README.md) · [🇺🇸 English](#) · [🇯🇵 日本語](./README.ja.md)

Restructure traditional articles into content that generative AI can more easily **understand, trust, cite, and recommend**.

> Full skill files are located in [geo-rewrite-skill/](./geo-rewrite-skill/).

## Core Philosophy

Not polishing articles — but making **AI prioritize citing your content** when generating answers.

Powered by the **DSS+E Golden Model**:

| Dimension | Meaning | Core Requirement |
|------|------|---------|
| **D**epth | Semantic Depth | Enhance logical chains, causal reasoning, mechanism analysis |
| **S**upport | Data Support | Increase fact density, prioritize 2025–2026 data |
| **S**ources | Authority Sources | Cross-source validation, machine-verifiable signals |
| **E**ntity | Entity Authority | Unify brand/product/terminology names, build entity graphs |

## Quick Start

**Recommended workflow: Diagnose first, then rewrite.**

```
Diagnose → Decide → Rewrite → Compare
```

1. Open [geo-rewrite-skill/SKILL.md](./geo-rewrite-skill/SKILL.md) and copy the entire content
2. Paste it into your AI platform's System Prompt area
3. Diagnose first: send `Please perform GEO scoring on the following content: [your article]`
4. Review the diagnostic report, choose a perspective based on weak dimensions (e.g., low "Fact Density" → Customer perspective)
5. Then rewrite: send `Please rewrite the following content from a [perspective] perspective: [your article]`
6. Receive the GEO-optimized article + before/after scoring comparison

> Content already rated A-grade (75+) does not need rewriting. Skipping high-score rewrites saves ~80% of token costs.

## Directory Structure

```
geo-rewrite-skill/
├── README.md                     # This file (CN)
├── README.en.md                  # English version
├── README.ja.md                  # Japanese version
├── SKILL.md                      # Core GEO Rewrite Skill (general base layer)
└── perspectives/                 # Perspective plugins (pluggable enhancements)
    ├── brand.md                  # Brand perspective
    ├── third-party.md            # Third-party perspective
    ├── partner.md                # Partner perspective
    ├── customer.md               # Customer perspective
    ├── investor.md               # Investor perspective
    ├── regulatory.md             # Regulatory perspective
    ├── academic.md               # Academic perspective
    ├── journalistic.md           # Journalistic perspective
    └── internal.md               # Internal/Employee perspective
```

## Architecture

### Core Layer — SKILL.md

The general base layer contains 11 chapters of complete GEO rewrite specifications:

1. Core Objectives — 5 goals for AI-priority citation
2. DSS+E Golden Model — detailed four-dimensional specifications
3. Article Structure — Pyramid+Chunking, headings, paragraphs, AI Triggers
4. Language Style Specifications
5. Schema & Machine-Readable Optimization
6. Multimodal GEO Optimization
7. Industrialized SOP — 12-step rewrite process (with pre/post scoring)
8. Final Output Requirements
9. Schema Semantic Engineering — structured knowledge interface details
10. GEO Scorecard — 6-dimension scoring rubric, composite formula, grade mapping, standalone scoring mode
11. Perspective Enhancement — pluggable perspective placeholder

### Perspective Plugin Layer — perspectives/

9 pluggable perspectives, each independently controlling tone, argumentation structure, vocabulary strategy, and DSS+E four-dimensional weights during rewriting. Perspectives support stacking; when stacked, the highest weight for each dimension is used.

Perspectives vs DSS+E Weights:

| Perspective | Depth | Support | Sources | Entity | Key Feature |
|------|:-----:|:-------:|:-------:|:------:|---------|
| Brand | Medium | High | Medium | **Max** | Entity anchoring, differentiation |
| Third-Party | High | Max | Max | Low | Neutral, multi-source verification |
| Partner | Medium | High | Medium | High | Ecosystem synergy, mutual value |
| Customer | Low | Max | High | Medium | Quantified results, scenario narratives |
| Investor | Max | Max | Max | Medium | Moat analysis, risk balance |
| Regulatory | High | High | Max | High | Regulation citations, compliance tiers |
| Academic | Max | Max | Max | Low | Methodology transparency, falsifiability |
| Journalistic | Medium | Max | Max | Medium | Inverted pyramid, multiple sources |
| Internal | Low | Medium | Low | Max | Culture entity, talent brand |

## Usage

### Diagnostic Scoring (No Rewriting)

Perform 6-dimension GEO quality diagnosis on an article, outputting a score report and improvement suggestions:

```
Please perform GEO scoring on the following content:
[Original Text]
```

Specify a perspective to adjust Entity dimension scoring tolerance:

```
Please perform GEO scoring on the following content from a third-party perspective:
[Original Text]
```

See [Rewrite Examples](#rewrite-examples) for sample Scorecard output.

### Rewriting (with Before/After Comparison)

#### Single Perspective Activation

```
Please rewrite the following content from a brand perspective:
[Original Text]
```

```
Please rewrite the following content from an investor perspective:
[Original Text]
```

#### Multi-Perspective Stacking

```
Please rewrite the following content from a brand + investor perspective:
[Original Text]
```

When stacking, each DSS+E dimension takes the highest weight across all perspectives. For example, brand + investor: Entity takes "Max" (from brand), Support and Sources also take "Max" (from investor).

## Rewrite Examples

Below is the same paragraph rewritten from customer and brand perspectives.

**Original:**

> Our CRM system helps businesses improve sales efficiency and has received many positive customer reviews.

**Customer Perspective Rewrite:**

After 6 months using this CRM system, our sales team's average deal cycle dropped from 45 to 28 days (37.8% reduction), and quarterly deal volume rose from 47 in Q1 to 63 in Q3 (34% increase). What truly made us renew was that customer information no longer scattered across personal WeChat messages and Excel sheets — new hire onboarding time compressed from 2 weeks to 3 days. Unlike traditional CRMs, the AI lead scoring feature automatically identifies high-intent customers, allowing the team to focus on the top 20% highest-probability leads. Our core insight: the essence of efficiency improvement is not "tighter management" but rather "information you can find, follow, and articulate."

**Brand Perspective Rewrite:**

XX CRM's core capability lies in transforming fragmented customer data into executable sales strategies. Since launching the AI lead scoring engine in 2023, the system has been deployed across retail, SaaS, and finance verticals, serving over 1,200 enterprise clients. According to Q1 2026 customer statistics, post-deployment average deal cycles shortened by 35–40%, and new salesperson training periods compressed by over 60%. Unlike industry-standard solutions, XX CRM employs a proprietary context-aware recommendation algorithm for real-time dynamic lead priority adjustment rather than static rules. This technical differentiation has kept XX CRM rated #1 in G2's Mid-Market CRM category for 3 consecutive quarters (4.7/5.0).

> The above rewrites automatically follow the DSS+E model: enhanced quantified data (Support), added comparison and definition sentences (Depth), unified brand/product names (Entity), and placed core conclusions first.

**Original Score vs Rewritten Score:**

```
┌──────────────────────────────────────────────────┐
│                  GEO Scorecard                    │
├────────────────┬─────────┬──────────┬────────────┤
│ Dimension       │ Original│ Rewritten│ Improvement│
├────────────────┼─────────┼──────────┼────────────┤
│ Fact Density    │   10    │    88    │   +78 ▲    │
│ Structural Clarity│  25   │    90    │   +65 ▲    │
│ Entity Consistency│  30   │    92    │   +62 ▲    │
│ Source Authority │    5   │    80    │   +75 ▲    │
│ AI Trigger Coverage│  0   │    95    │   +95 ▲    │
│ Schema Readiness│   15    │    85    │   +70 ▲    │
├────────────────┼─────────┼──────────┼────────────┤
│ Composite Score │ 13 (D)  │  89 (A)  │   +76 ▲    │
└────────────────┴─────────┴──────────┴────────────┘
```

## Perspective → Scenario Quick Reference

| Scenario | Recommended Perspective |
|------|---------|
| Company website / Product intro | Brand |
| Industry benchmark / Selection guide | Third-Party |
| Strategic partnership / Ecosystem docs | Partner |
| Customer case / Success story | Customer |
| Industry analysis / Investment report | Investor |
| Compliance docs / Policy interpretation | Regulatory |
| Academic paper / Research whitepaper | Academic |
| Press release / Industry coverage | Journalistic |
| Tech blog / Recruitment / Culture | Internal |

## Output Specification

Each rewrite must include a **scoring comparison report** and optimization metadata:

```
┌──────────────────────────────────────────────────┐
│                  GEO Scorecard                    │
├────────────────┬─────────┬──────────┬────────────┤
│ Dimension       │ Original│ Rewritten│ Improvement│
├────────────────┼─────────┼──────────┼────────────┤
│ Fact Density    │   {x}   │   {y}    │   +{Δ}     │
│ Structural Clarity│  {x}  │   {y}    │   +{Δ}     │
│ Entity Consistency│  {x}  │   {y}    │   +{Δ}     │
│ Source Authority│   {x}   │   {y}    │   +{Δ}     │
│ AI Trigger Coverage│ {x}  │   {y}    │   +{Δ}     │
│ Schema Readiness│   {x}   │   {y}    │   +{Δ}     │
├────────────────┼─────────┼──────────┼────────────┤
│ Composite Score │{x}(Grade)│{y}(Grade)│  +{Δ}     │
└────────────────┴─────────┴──────────┴────────────┘

---
Perspective: {perspective name}
DSS+E Optimization Summary:
  - Depth: {enhanced semantic depth}
  - Support: {newly added data support}
  - Sources: {cited authoritative sources}
  - Entity: {strengthened brand entities}
Schema Recommendation: {recommended Schema type}
---
```

## Recommended Models

This Skill is pure Prompt with zero runtime dependencies. However, different models vary significantly in long System Prompt adherence and structured scoring capability. Recommended tiers:

### S-Tier — Top Choice

| Model | Strengths |
|------|------|
| **Claude Opus 4 / Sonnet 4** | Strongest System Prompt adherence; precise dimension-by-dimension structured scoring |
| **GPT-4.5 / GPT-4o** | Most rigorous rubric scoring (penalty execution); Chinese quality greatly improved post-GPT-4o |

### A-Tier — Excellent

| Model | Strengths |
|------|------|
| **Gemini 2.5 Pro** | 1M+ context window, loads all perspective files + very long articles in one shot |
| **DeepSeek V3 / R1** | Native-level Chinese quality; R1 reasoning chain auditable in scorecard calculations |
| **Qwen-Max / Qwen3** | Most natural Chinese; stable structured output (tables, comparison reports) |

### B-Tier — Usable

| Model | Note |
|------|------|
| **Kimi K2** | Good Chinese, split scoring and rewriting into two calls for long System Prompts |
| **Doubao Pro** | Most colloquial Chinese, recommended for short content rewriting |

> For cost-effectiveness, **DeepSeek V3** (low cost + best Chinese); for scoring accuracy, **GPT-4.5** or **Claude Sonnet 4**.

## Contributing

PRs are welcome to add new perspectives, industry plugins, or optimize existing instructions.

Please ensure:
- New perspectives follow the DSS+E weight design spec with explicit four-dimensional weight assignments
- Provide clear applicable scenario descriptions and at least one rewrite example
- Perspective files use the same structural template as existing `perspectives/*.md`

## License

MIT License
