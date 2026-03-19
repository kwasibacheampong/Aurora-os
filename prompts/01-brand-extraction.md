# Prompt 01 — Brand Mention Extraction

**Module:** 1 — AI Visibility Intelligence  
**Phase:** Week 3–4  
**When called:** Once per AI response, per prompt run  
**Model:** `claude-sonnet-4-20250514`

---

## Purpose

Given a raw response string from any AI assistant (ChatGPT, Gemini, Perplexity, etc.), extract structured brand intelligence. This is the entry point of the Aurora OS pipeline — every downstream metric (ISI, GEO gaps, digest) derives from this extraction.

---

## System Prompt

```
You are an AI response analyst. Given a raw response from an AI assistant (ChatGPT, Gemini, Perplexity, etc.), extract structured brand intelligence.

Return ONLY valid JSON in this exact format:
{
  "brand_mentioned": boolean,
  "mention_count": number,
  "ranking_position": number | null,
  "sentiment": "positive" | "neutral" | "negative" | "not_mentioned",
  "sentiment_score": number,
  "competitor_mentions": [
    { "brand": string, "position": number, "sentiment": "positive" | "neutral" | "negative" }
  ],
  "citations": [
    { "url": string | null, "domain": string | null, "context": string }
  ],
  "summary": string
}
```

---

## User Prompt Template

```
Brand to analyse: {brand_name}
Competitors to track: {competitor_list}

AI Response to analyse:
{ai_response_text}
```

---

## Variables

| Variable | Type | Description |
|----------|------|-------------|
| `brand_name` | string | The brand being tracked (e.g. "Nike") |
| `competitor_list` | string | Comma-separated list of competitors to detect |
| `ai_response_text` | string | Raw text response from GPT / Gemini / Perplexity |

---

## Output Schema

| Field | Type | Notes |
|-------|------|-------|
| `brand_mentioned` | boolean | Whether the brand appears at all |
| `mention_count` | number | How many times the brand is mentioned |
| `ranking_position` | number \| null | Position in a ranked list, if applicable |
| `sentiment` | enum | Tone of brand mention |
| `sentiment_score` | number | 0–1 float, 1 = most positive |
| `competitor_mentions` | array | Each competitor found, with position + sentiment |
| `citations` | array | URLs or domains cited by the AI in context |
| `summary` | string | 1–2 sentence human-readable summary of the mention |

---

## Usage in Pipeline

```javascript
const response = await fetch("https://api.anthropic.com/v1/messages", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    model: "claude-sonnet-4-20250514",
    max_tokens: 1000,
    system: SYSTEM_PROMPT,
    messages: [{
      role: "user",
      content: `Brand to analyse: ${brandName}\nCompetitors to track: ${competitors}\n\nAI Response to analyse:\n${aiResponseText}`
    }]
  })
});
const data = await response.json();
const extraction = JSON.parse(data.content[0].text);
```

---

*Aurora OS · Fruitful Bough · 2025–2026*
