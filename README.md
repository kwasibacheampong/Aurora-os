# Aurora OS

### The Operating System for Marketing in the Age of AI Customers

[![Status](https://img.shields.io/badge/Status-Phase%201%20Build-orange?style=flat-square)]()
[![Live App](https://img.shields.io/badge/Live%20App-base44-00A8CC?style=flat-square)](https://kwasi-acheampong-capability-portfolio.base44.app)
[![Built With](https://img.shields.io/badge/Intelligence-Claude%20API-FF6B35?style=flat-square)](https://anthropic.com)
[![Platform](https://img.shields.io/badge/Platform-Base44-0099BB?style=flat-square)]()
[![By](https://img.shields.io/badge/Built%20by-Fruitful%20Bough-C9A84C?style=flat-square)](https://github.com/kwasibacheampong)

> **[Fruitful Bough](https://github.com/kwasibacheampong)** · Strategic architect of measurable value. Not advisory — structural. Not consultancy — engineering.

---

## What this is

The digital landscape has shifted from **search-driven discovery to AI-driven discovery.**

When someone asks ChatGPT, Claude, Gemini, or Perplexity which brand to choose — your brand's presence (or absence) in that answer is now a commercial event. Aurora OS is the intelligence platform that tracks, scores, and optimises that presence.

Aurora OS connects five capabilities into a closed-loop growth intelligence system:

```
AI Discovery Intelligence
        ↓
Influence Share Index (ISI)
        ↓
GEO Optimisation Engine
        ↓
Demand Incrementality Modelling
        ↓
Customer Lifetime Value Intelligence
```

The goal: link AI visibility directly to commercial outcomes — not as a vanity metric, but as an operational growth lever.

---

## Architecture

Aurora OS is built on two integrated layers:

| Layer | Technology | Role |
|-------|-----------|------|
| **Intelligence** | Claude API (Anthropic) | Extraction, scoring, gap analysis, brief generation, digest narration |
| **Application** | Base44 | App shell, data model, UI, scheduling, alerting, multi-brand support |

Claude acts as the reasoning engine throughout — not a chatbot wrapper, but a structured output machine producing typed JSON at every stage of the pipeline.

---

## Phase 1 — Build Plan (10 Weeks)

### Module 1 · AI Visibility Intelligence

| Phase | Weeks | Output |
|-------|-------|--------|
| Foundation & Data Ingestion | 1–2 | Working app shell, auth (OAuth2), prompt management UI, brand/competitor data model |
| AI Answer Extraction Engine | 3–4 | Scheduled prompt runner firing across GPT, Claude, Gemini, Perplexity — extracting structured brand mentions, sentiment, ranking position, citations daily |
| Influence Share Index (ISI) Scoring | 5–6 | Live ISI dashboard with trend lines (7d / 30d / 90d), competitor benchmarks, and automated drop alerts |

### Module 2 · GEO Optimisation Engine

| Phase | Weeks | Output |
|-------|-------|--------|
| GEO Optimisation Engine | 7–8 | AI-readability scorer (URL audit), citation opportunity mapper, content gap detector, automated brief generator |
| Alerts, Reports & Polish | 9–10 | Shippable product: alerting engine, weekly digest emails, onboarding wizard, CSV/PDF export, multi-brand support |

---

## Claude API Prompts — Prompt Library

Aurora OS exposes five structured Claude prompts as the core intelligence layer. Each returns typed JSON.

### 1. Brand Mention Extraction
**When called:** Once per AI response, per prompt (Weeks 3–4)  
**Input:** Raw response string from GPT / Gemini / Perplexity  
**Output:** Structured JSON — `brand_mentioned`, `mention_count`, `ranking_position`, `sentiment`, `sentiment_score`, `competitor_mentions[]`, `citations[]`, `summary`

### 2. ISI Score Computation
**When called:** Daily, after batch prompt runs complete (Weeks 5–6)  
**Input:** Batch of extraction records for a brand across all models  
**Output:** `isi_overall`, `isi_by_model` (GPT / Claude / Gemini / Perplexity), `isi_vs_competitors[]`, `trend`, `key_insight`, `recommended_action`

### 3. GEO Readability Scorer
**When called:** On user URL submission for audit (Weeks 7–8)  
**Input:** Page content + target prompts  
**Output:** `geo_score`, `factual_density`, `citation_likelihood`, `strengths[]`, `gaps[]` (with impact + fix), `schema_recommendations[]`, `priority_fix`

### 4. Content Brief Generator
**When called:** On user "Generate Brief" action for a detected gap (Weeks 7–8)  
**Input:** Brand, gap prompt, product description, current citations  
**Output:** Full structured brief — `content_type`, `word_count_target`, `headline_options[]`, `key_sections[]`, `schema_markup_needed[]`, `estimated_citation_impact`

### 5. Weekly Digest Narrative
**When called:** Once per brand per week via scheduled job (Weeks 9–10)  
**Input:** ISI current/previous/delta, top prompt, biggest gap, competitor movement  
**Output:** CMO-ready 3-paragraph digest with subject line, section headlines, and `one_line_summary`

> Full prompt schemas (system + user templates) available in [`/prompts`](./prompts/).

---

## Key Metrics Targeted

| Metric | Definition |
|--------|-----------|
| **ISI — Influence Share Index** | (Brand mentions ÷ total mentions) × sentiment weight × position weight, per AI model |
| **GEO Score** | AI-readability rating for a given URL, scored 0–100 |
| **Citation Likelihood** | High / Medium / Low probability of being cited by AI assistants for a target prompt |
| **Content Gap Count** | Number of target prompts where brand is absent but competitors are present |

---

## Live Application

> **[kwasi-acheampong-capability-portfolio.base44.app](https://kwasi-acheampong-capability-portfolio.base44.app)**

The Phase 1 application is deployed on Base44. The intelligence layer runs on the Claude API (Anthropic) via structured prompt calls returning validated JSON at each pipeline stage.

---

## Roadmap

| Version | Scope |
|---------|-------|
| **Phase 1 (Now)** | AI visibility tracking, ISI scoring, GEO optimisation, weekly digests |
| **Phase 2** | Machine customer simulation — AI agents as purchasing decision-makers |
| **Phase 3** | Demand incrementality modelling — linking AI influence to conversion lift |
| **Phase 4** | CLV intelligence — lifetime value modelling for AI-influenced customer cohorts |

---

## Part of the Fruitful Bough Platform Portfolio

Aurora OS is the flagship platform in the **Fruitful Bough** commercial intelligence suite:

| Platform | Domain | Status |
|----------|--------|--------|
| **Aurora OS** (this repo) | AI discovery & growth intelligence | Phase 1 build |
| [ACE-OS](../ace-os) | Airport commerce & experience operating system | Architecture complete |
| [ACO](../aviation-capacity-orchestrator) | Aviation digital twin capacity orchestrator | PRD complete |
| [FMCG GTM Accelerator](../uk-fmcg-gtm-accelerator) | UK grocery channel decision intelligence | PRD complete |
| [SIGFA](../sigfa) | Social impact growth & funding accelerator | Pilot proven (CAHN, £1M+) |

---

## Repository Structure

```
aurora-os/
├── README.md
├── prompts/
│   ├── 01-brand-extraction.md       # System + user prompt templates
│   ├── 02-isi-computation.md
│   ├── 03-geo-readability.md
│   ├── 04-content-brief.md
│   └── 05-weekly-digest.md
├── architecture/
│   ├── data-model.md                # Brand, Prompt, AI_Response, Citation entities
│   └── pipeline-overview.md        # End-to-end data flow
├── docs/
│   └── phase1-build-plan.html       # Interactive build plan
└── CHANGELOG.md
```

---

## Philosophy

Technology is leverage. The organisations that will win the next decade are those that build systems combining:

- Strategic thinking
- Data infrastructure  
- Automation
- Commercial impact

Aurora OS is that system for the question every brand now faces: *when AI answers on your behalf, does it answer correctly?*

---

*Built by [Kwasi Boakye Acheampong](https://github.com/kwasibacheampong) · Principal, Fruitful Bough · 2025–2026*  
*Integrity · Trust · Value*
