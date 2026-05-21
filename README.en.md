# GEO Rewrite Skill

[🇨🇳 中文](./README.md) · [🇺🇸 English](#) · [🇯🇵 日本語](./README.ja.md)

> Not replacing facts — making the real content you already have visible in the age of AI.

Restructure traditional articles into content that generative AI can more easily **understand, trust, extract, cite, and recommend**.

> Full skill file: [geo-rewrite-skill/SKILL.md](./geo-rewrite-skill/SKILL.md) (v1.2, 25 sections).

## Core Philosophy

Not polishing articles — but making **AI prioritize citing your content** when generating answers.

Powered by the **DSS+E Golden Model**:

| Dimension | Meaning | Core Requirement |
|------|------|---------|
| **D**epth | Semantic Depth | Enhance logical chains, causal reasoning, mechanism analysis |
| **S**upport | Data Support | Increase fact density, prioritize 2025–2026 data |
| **S**ources | Authority Sources | Cross-source validation, machine-verifiable signals |
| **E**ntity | Entity Authority | Unify brand/product/terminology names, build entity graphs |

## Why Rewrite Instead of Write — The Ethical Foundation of GEO Ecosystem Governance

GEO Rewrite does not let AI write for you. It makes the real content you already have visible in the age of AI.

### The AI Content Ecosystem Faces a "Trust Crisis"

As of 2026, approximately 27% of long-form content on the internet is generated or assisted by AI. When a generative AI model uses this AI-generated content as training or reference material, it triggers **Hallucination Recursion** — the model cites hallucinated content, produces more hallucinations, causing a downward spiral in the credibility of the entire AI citation ecosystem.

**GEO Rewrite's position: do not create new facts; only enhance the discoverability and citability of existing facts.**

### Rewrite vs Write: The Essential Difference

| | AI Write (Direct Generation) | GEO Rewrite |
|---|---|---|
| Fact Source | Model training data, untraceable, fabrication risk | Author's actual information, traceable |
| Data Authenticity | May fabricate specific numbers (hallucination) | Only structures existing data, adds no new values |
| Brand Entities | May confuse, fabricate, or misattribute | Original entities unified and strengthened, zero deviation |
| Ethical Risk | Hallucination pollutes the citation ecosystem | Zero new hallucinations |
| AI Citation Value | Next-round models may reject due to untrustworthiness | Sufficient machine-verifiable signals, high citation probability |

### The Public Interest in GEO Ecosystem Governance

If every brand lets AI generate content directly, search engines and AI Answers will become arenas for hallucinated content. GEO Rewrite upholds the bottom line of **"original fact anchoring"** — not altering the facts, data, or viewpoints of the original, only optimizing the structure through which these facts can be discovered and cited by AI. This is fundamentally about protecting the credibility of the entire AI content citation ecosystem.

**Therefore: Rewrite is "credibility amplification grounded in facts"; Write is "hallucination generation based on prompts." The ethical weight and accountability of the two are fundamentally different.**

### The Endgame: Narrative Ownership

The ultimate battleground of GEO is not traffic — it is **"whose definition of the industry gets cited by AI."**

When an AI is asked about your industry, whose definitions, frameworks, and methodologies does it cite? This determines a brand's cognitive priority in the age of AI. The true moat is not keyword ranking, but: when AI discusses your industry, **your brand's definition is the first thing it recalls.**

The final goal of GEO Rewrite is not "being indexed by AI," but **"becoming the default industry definition source that AI cites."**

## Quick Start

### Prerequisites

1. Open [geo-rewrite-skill/SKILL.md](./geo-rewrite-skill/SKILL.md), `Ctrl+A` to select all and copy
2. Paste into your AI platform's System Prompt area
3. No need to load `perspectives/` separately — v1.2 perspectives are fully inlined

**Platform System Prompt Entry Points:**

| Platform | Entry Path |
|------|---------|
| ChatGPT | Settings → Custom instructions → "How would you like ChatGPT to respond?" |
| Claude | Settings → Add custom instructions for Claude |
| DeepSeek | "System Prompt" button above input box |
| Kimi | Bottom-left Settings → Custom instructions |
| Doubao | Conversation Settings → System Prompt |

---

## Usage

GEO Rewrite Skill supports two invocation methods: **natural language** (recommended for beginners, direct chat) and **YAML format** (precise control, suitable for API and advanced scenarios).

### Prerequisites (Both Methods)

1. Open [geo-rewrite-skill/SKILL.md](./geo-rewrite-skill/SKILL.md), `Ctrl+A` to select all and copy
2. Paste into your AI platform's System Prompt area
3. No need to load `perspectives/` separately — v1.2 perspectives are fully inlined

---

### Method 1: Natural Language (Beginner-Friendly)

#### 1. Diagnostic Scoring — See What's Wrong First

Perform 6-dimension GEO quality diagnosis, output score report only, no rewriting:

```
Please perform GEO scoring on the following content:
[Paste your article]
```

**Example AI response** (full version includes dimension scores, grades, penalty reasons, original evidence, optimization suggestions, and recommended perspective):

| Dimension | Score | Grade | Penalty Reason | Original Evidence |
|------|:--:|------|---------|---------|
| Fact Density | 20 | Very Weak | No quantified data | "Many companies are starting to use AI" |
| Structural Clarity | 25 | Very Weak | Vague headings | "Industry Trends" |

Composite Score: 19/100 (D-Grade) → Recommended Perspective: Customer (strengthen data)

> Content rated ≥75 (A-grade) does not need rewriting. Skipping high-score rewrites saves ~80% of token costs.

Specify a perspective to adjust scoring tolerance:

```
Please perform GEO scoring on the following content from an investor perspective:
[Paste your article]
```

#### 2. Full Rewrite — Diagnose + Rewrite + Compare

```
Please rewrite the following content from a brand perspective:
[Paste your article]
```

**Full rewrite outputs**: Original Scorecard → Problem Diagnosis → Rewrite Strategy → Rewritten Article → FAQ Module → Schema Recommendation → Rewritten Scorecard → Comparison Summary → Missing Sources Checklist.

#### 3. Multi-Perspective Stacked Rewrite

```
Please rewrite the following content from a brand + investor perspective:
[Paste your article]
```

When stacking, each DSS+E dimension takes the highest weight across all perspectives.

#### 4. Schema-Only Mode

When your article quality is good and you only need structural markup:

```
Please recommend Schema types and output JSON-LD for the following content:
[Paste your article]
```

#### 5. AI Citation Audit

Published content needs periodic checking to verify if AI correctly understands your brand:

```
Please generate an Oracle Audit plan for "{Your Brand Name}" to check how mainstream AI platforms cite the brand.
```

---

### Method 2: YAML Format (Precise Control)

Use YAML format when you need precise parameter control (e.g., API calls, batch processing).

#### Field Reference

| Field | Type | Default | Description |
|------|------|--------|------|
| `mode` | rewrite / score_only / schema_only / audit_plan | rewrite | Execution mode |
| `perspective` | 9 perspective names | Third-Party | Rewrite perspective |
| `brand` | text | — | Brand name |
| `product` | text | — | Product name |
| `audience` | text | — | Target audience |
| `source_policy` | use_provided_only / allow_external_sources / mark_missing_sources | mark_missing_sources | Source policy |
| `output_length` | short / standard / long | standard | Output length |
| `need_schema` | true / false | true | Whether to output Schema |
| `article` | multiline text (required) | — | Original content to process |

**source_policy in detail:**

| Policy | Meaning | When to Use |
|------|------|---------|
| `use_provided_only` | Use only data from original article, no search, no placeholder annotation | Article has sufficient data, or content must not expose external sources |
| `allow_external_sources` | Allow model to search and supplement sources | When the model supports search functionality |
| `mark_missing_sources` | No search, but annotate gaps with `[Source needed: ...]` placeholders | **Recommended default**, safe and auditable |

#### Example 1: Full Rewrite

```yaml
mode: rewrite
perspective: Customer
brand: XX CRM
source_policy: mark_missing_sources
need_schema: true
article: |
  Our CRM system helps businesses improve sales efficiency and has received many positive customer reviews.
```

#### Example 2: Scoring Only

```yaml
mode: score_only
perspective: Third-Party
article: |
  [Original content]
```

#### Example 3: Schema Only

```yaml
mode: schema_only
brand: XX CRM
product: XX CRM Sales Management System
article: |
  [Article content]
```

#### Example 4: Audit Plan

```yaml
mode: audit_plan
brand: XX CRM
article: |
  Your brand positioning, core products, key methodologies, etc.
```

---

### How to Read Diagnostic Reports

When viewing scoring reports, focus on the "Penalty Reason" column — it directly tells you what's wrong from AI's perspective:

| Low Dimension | What It Means | Impact on AI Citation |
|---------|-----------|----------------|
| **Fact Density** low | Article lacks specific numbers, relies entirely on adjectives | AI cannot extract verifiable facts, low Embedding quality, low recall |
| **Structural Clarity** low | No conclusion-first, vague headings, long paragraphs | Each Chunk after slicing is unclear, Snippet extraction fails |
| **Entity Consistency** low | Same brand uses multiple names ("XX Cloud" / "XXCloud") | AI cannot build stable Knowledge Graph nodes, entity links broken |
| **Source Authority** low | All conclusions lack sources, "studies show" without specifics | AI judges as low-trust source, pushed back in Reranking |
| **AI Trigger Coverage** low | No definition/comparison/causal/summary/temporal sentences | AI cannot efficiently extract core views, Snippets empty or fragmented |
| **Schema Readiness** low | Pure narrative flow, no structural features | Schema markup cannot match, losing machine-parseable signals |

---

### How to Choose a Perspective Based on Diagnosis

| Lowest Dimensions | Recommended Perspective | Reason |
|-----------|---------|------|
| Fact Density + Source Authority | **Third-Party** | Strengthen data citations, multi-source cross-validation |
| Fact Density + Structural Clarity | **Customer** | Quantified results + scenario-based narrative |
| Entity Consistency | **Brand** | Unify brand names, build entity graph |
| All dimensions low | **Investor** | Highest information density requirements across all dimensions |
| Source Authority + Structural Clarity | **Academic** | Literature citations + methodology transparency |
| Entity Consistency + Source Authority | **Regulatory** | Regulation citations + compliance tiering |

---

### Source Placeholder Usage Guide

The "Missing Sources Checklist" in rewrite output will contain annotations like:

```
[Source needed: industry report, suggested source: Gartner / IDC / McKinsey]
[Data needed: 2025 growth rate, year range: 2024-2025]
[Case study needed: customer industry, before/after metrics, time period]
[Citation needed: expert name, institution, publication date, original link]
```

**This is not AI being lazy — it is the "fact anchoring" bottom line of GEO Rewrite in operational form.** AI will not fabricate data here, but rather marks positions requiring real data. Users should replace these placeholders with their actual data before publication.

---

### Perspective → Scenario Quick Reference

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

> 📋 **Real-World Case Study**: [Samsung Labor Agreement → Journalistic GEO Rewrite](case-studies/samsung-labor-geo-rewrite.md)  
> Original C-Grade (44) → A-Grade (87) after rewrite.  
> Full original article, 6-dimension comparison, rewrite strategy, Trigger breakdown, and missing sources checklist.

## Rewrite Examples

**Original:**
> Our CRM system helps businesses improve sales efficiency and has received many positive customer reviews.

**Customer Perspective Rewrite:**

After 6 months using this CRM system, our sales team's average deal cycle dropped from 45 to 28 days (37.8% reduction), and quarterly deal volume rose from 47 in Q1 to 63 in Q3 (34% increase). What truly made us renew was that customer information no longer scattered across personal WeChat messages and Excel sheets — new hire onboarding time compressed from 2 weeks to 3 days. Unlike traditional CRMs, the AI lead scoring feature automatically identifies high-intent customers, allowing the team to focus on the top 20% highest-probability leads. Our core insight: the essence of efficiency improvement is not "tighter management" but rather "information you can find, follow, and articulate."

**Brand Perspective Rewrite:**

XX CRM's core capability lies in transforming fragmented customer data into executable sales strategies. Since launching the AI lead scoring engine in 2023, the system has been deployed across retail, SaaS, and finance verticals, serving over 1,200 enterprise clients. According to Q1 2026 customer statistics, post-deployment average deal cycles shortened by 35–40%, and new salesperson training periods compressed by over 60%. Unlike industry-standard solutions, XX CRM employs a proprietary context-aware recommendation algorithm for real-time dynamic lead priority adjustment rather than static rules. This technical differentiation has kept XX CRM rated #1 in G2's Mid-Market CRM category for 3 consecutive quarters (4.7/5.0).

> The above rewrites automatically follow the DSS+E model: enhanced quantified data (Support), added comparison and definition sentences (Depth), unified brand/product names (Entity), and placed core conclusions first.

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
Missing Sources: {checklist of sources for user to supplement}
---

> Full rewrites also output FAQ module and Schema JSON-LD code. See SKILL.md Section 21 for the complete template.
```

## Recommended Models

### S-Tier — Top Choice

| Model | Chinese Rewrite Advantage |
|------|------------|
| **DeepSeek-V4** | 🇨🇳 Native-level Chinese output, zero "translation-ese"; extreme cost-efficiency for batch rewriting |
| **Qwen3-Max** | 🇨🇳 Most natural Chinese, no "AI flavor"; most stable structured output |
| **Claude Opus 4.7** | Strongest System Prompt adherence; most precise per-dimension scoring |
| **GPT-5.5 Ultra** | Most rigorous rubric scoring; GPT-5.5 Instant handles routine rewriting |

### A-Tier — Excellent

| Model | Strengths |
|------|------|
| **Gemini 3 Pro** | 1M+ context window |
| **Doubao Seed 2.0 Pro** | Most colloquial Chinese for short content |

### B-Tier — Usable

| Model | Note |
|------|------|
| **Kimi K2** | Fluent Chinese, split calls for long System Prompts |

## Boundary Declaration — What This Skill Does NOT Do

1. **Does not fabricate facts**: Only enhances existing data expression, never invents data.
2. **Does not replace the author**: A content optimization tool, not a content creation tool.
3. **Does not generate fake authority signals**: No fabricated certifications, citations, or reviews.
4. **Does not replace legal/compliance review**: Optimizes expression structure only, no legal advice.

## Extensibility

| Tool | Integration |
|------|---------|
| **Claude Code** | `.claude/instructions.md` |
| **Trae / Cursor** | `.trae/rules/` or `.cursor/rules/` |
| **GitHub Copilot Chat** | `#file:SKILL.md` reference |
| **Codex CLI** | `--system-prompt SKILL.md` parameter |
| **Feishu / Slack / WeCom** | Bot integration |

## About the Author

This project is maintained by [Zachary](https://github.com/zacharylijun-sketch). Reach out for collaboration:

- **WeChat**: `Lee_19980520`

Whether it's GEO rewrite strategy discussions, custom perspective requests, Skill optimization ideas, or enterprise content pipeline setup — feel free to get in touch.

> 🔬 **GEO Monitoring Tool**: We're beta-testing a SaaS tool for generative AI citation monitoring — tracking your brand's citation status, entity accuracy, and competitor confusion rate across ChatGPT, Gemini, Doubao, Kimi, and other AI platforms. Add WeChat above for beta access.

## License

MIT License
