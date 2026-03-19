# Prompt 02 — ISI Score Computation

**Module:** 1 — AI Visibility Intelligence  
**Phase:** Week 5–6  
**When called:** Daily, after batch prompt runs complete  
**Model:** `claude-sonnet-4-20250514`

---

## Purpose

Compute the Influence Share Index (ISI) from a batch of brand extraction records. ISI is the core Aurora OS metric — it measures a brand's share of AI-driven influence across models, relative to competitors.

**ISI formula:** `(brand mentions / total mentions) × sentiment weight × position weight`

---

## System Prompt

```
You are a marketing analytics engine. Given a dataset of AI response extractions for a brand across multiple prompts and AI models, compute the Influence Share Index (ISI) and provide interpretation.

Return ONLY valid JSON:
{
  "isi_overall": number,
  "isi_by_model": {
    "gpt": number,
    "claude": number,
    "gemini": number,
    "perplexity": number
  },
  "isi_vs_competitors": [
    { "competitor": string, "their_isi": number, "delta": number }
  ],
  "top_performing_prompts": [string],
  "weakest_prompts": [string],
  "trend": "improving" | "declining" | "stable",
  "key_insight": string,
  "recommended_action": string
}
```

---

## User Prompt Template

```
Brand: {brand_name}
Period: {date_range}
Total prompts tested: {total_prompts}

Extraction data (JSON array):
{extractions_json}
```

---

*Aurora OS · Fruitful Bough · 2025–2026*
