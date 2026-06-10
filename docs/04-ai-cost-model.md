# AI Cost Model

This document provides an illustrative cost model for the AI CV Parser platform.

The objective is not to provide exact financial forecasts, but to demonstrate how AI operating costs can be estimated and incorporated into product decisions.

---

## Assumptions

| Parameter | Value |
|------------|---------|
| Average CV Length | 3,500 tokens |
| Average CV Size | 3-4 pages |
| Validation Calls | 1 |
| Translation Calls | 1 |
| Extraction Calls | 5 |
| JSON Structuring Calls | 1 |
| Embedding Generation | 1 |
| Total AI Operations per CV | 9 |

---

## Processing Pipeline

| Step | Purpose |
|--------|---------|
| Validation | Verify uploaded file is a valid CV |
| Translation & Formatting | Normalize content into a consistent language and structure |
| Summary Extraction | Generate candidate summary |
| Personal Information Extraction | Extract profile data |
| Experience Extraction | Extract employment history |
| Skills Extraction | Extract technical and business skills |
| Language Extraction | Extract language proficiencies |
| JSON Structuring | Convert extracted data into structured format |
| Embedding Generation | Enable semantic search and matching |

---

# Cost Scenario 1: GPT-4.1 Mini

## Estimated Cost Breakdown Per CV

| Component | Estimated Cost |
|------------|---------|
| Validation | $0.0016 |
| Translation & Formatting | $0.0070 |
| Parallel Extraction Calls | $0.0110 |
| JSON Structuring | $0.0025 |
| Embedding Generation | $0.0001 |
| **Total Cost Per CV** | **$0.0222** |

---

## Monthly Processing Cost

| Monthly Volume | Estimated Cost |
|----------------|----------------|
| 10,000 CVs | $222 |
| 50,000 CVs | $1,110 |
| 100,000 CVs | $2,220 |
| 500,000 CVs | $11,100 |
| 1,000,000 CVs | $22,200 |

---

# Cost Scenario 2: Gemini 2.5 Flash

## Estimated Cost Breakdown Per CV

| Component | Estimated Cost |
|------------|---------|
| Validation | $0.0004 |
| Translation & Formatting | $0.0015 |
| Parallel Extraction Calls | $0.0024 |
| JSON Structuring | $0.0006 |
| Embedding Generation | $0.0001 |
| **Total Cost Per CV** | **$0.0050** |

---

## Monthly Processing Cost

| Monthly Volume | Estimated Cost |
|----------------|----------------|
| 10,000 CVs | $50 |
| 50,000 CVs | $250 |
| 100,000 CVs | $500 |
| 500,000 CVs | $2,500 |
| 1,000,000 CVs | $5,000 |

---

# Comparative Analysis

| Metric | GPT-4.1 Mini | Gemini 2.5 Flash |
|----------|----------|----------|
| Cost Per CV | $0.022 | $0.005 |
| Cost Per 100K CVs | $2,220 | $500 |
| Relative Cost | 100% | 23% |
| Processing Speed | Good | Faster |
| Expected Accuracy | Higher | Good |
| Enterprise Scalability | Good | Excellent |

---

# Product Implications

Several important product decisions emerge from this analysis:

1. AI model selection has a direct impact on platform gross margins.

2. A 4x difference in processing costs can significantly affect pricing strategy and profitability.

3. Different customer segments may justify different model selections.

4. Model selection should be treated as an ongoing product decision rather than a one-time technical decision.

5. Multi-provider architecture creates flexibility to optimize for accuracy, speed, or cost depending on customer requirements.

---

# Future Optimization Opportunities

Potential cost reduction opportunities include:

- Aggressive caching of previously processed CVs
- Dynamic model routing
- Smaller models for low-risk extraction tasks
- Batch processing workflows
- Hybrid keyword + semantic search approaches
- Prompt optimization to reduce token consumption

