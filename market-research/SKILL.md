---
name: market-research
description: |
  Thu thập data thị trường thật để feed vào Product Tower T1-T9.
  Product Tower Tầng 0 (Data Foundation). NotebookLM = RAG hub chính,
  mỗi tầng 1 notebook riêng. Extract → .md → Product Tower consume.
triggers:
  - "research market"
  - "thu thập data"
  - "market data"
  - "tầng 0"
  - "market research"
---

# PROTOCOL: MARKET_RESEARCH (Product Tower — Tầng 0)

## VAI TRÒ

**Market Research Lead** — thu thập + tổ chức data thật.

> **Pipeline**: NotebookLM → `notebooklm ask` → save .md → Product Tower consume
> **Primary Tool**: `notebooklm-py` v0.3.3 (đã cài)
> **Output**: `data/*.md` per tier → T1-T9 đọc trực tiếp

---

## KIẾN TRÚC

```
NotebookLM (5 notebooks/project)
│  📓 T0 - Raw Research      ← PDFs, URLs, YouTube, Sheets
│  📓 T1-3 - Market Segments ← segment analysis
│  📓 T4-6 - User Discovery  ← interviews, surveys
│  📓 T7 - PMF               ← validation data
│  📓 T8-9 - Features        ← stories, backlog
│
│  👤 Founder + 👥 Team + 🤖 Deep Research → cùng nạp data
│
└──► notebooklm ask "..." → save thẳng .md
                │
                ▼
     [project]/data/*.md  (cached snapshots)
                │
                ▼
     Product Tower T1-T9 skills READ .md files
```

---

## NOTEBOOK SETUP (1 lần per project)

```bash
notebooklm create "[Project] T0 - Raw Research"
notebooklm create "[Project] T1-3 - Market Segments"
notebooklm create "[Project] T4-6 - User Discovery"
notebooklm create "[Project] T7 - PMF Validation"
notebooklm create "[Project] T8-9 - Feature Scope"
```

| Notebook | Sources gì | Ai upload |
|----------|-----------|-----------|
| **T0 Raw** | PDFs, reports, URLs, YouTube | Founder + Deep Research |
| **T1-3 Segments** | T0 output + segment data | AI + Founder |
| **T4-6 Users** | Interview notes, surveys | Founder + Team |
| **T7 PMF** | Survey data, metrics | Founder + KH |
| **T8-9 Features** | User stories, wireframes | Founder |

---

## 3-PHASE WORKFLOW

### PHASE 1: SEED (30 phút)

```bash
notebooklm use <T0_ID>
notebooklm source add "./savills_2025.pdf"
notebooklm source add "https://competitor-site.com"
notebooklm source add "https://youtube.com/watch?v=relevant"
notebooklm source add "https://docs.google.com/spreadsheets/d/..."
```

### PHASE 2: ENRICH (1-2 giờ)

- NotebookLM Deep Research (web UI) → auto-add web sources
- Apify Google Trends → CSV → Google Sheets → add vào notebook
- Social scraping → add vào T4-6 notebook

### PHASE 3: EXTRACT → .md (30 phút)

```bash
# Tạo folder data
mkdir -p [project]/data

# Extract từ mỗi notebook → save .md
notebooklm use <T0_ID>
notebooklm ask "Market size, growth rate, cycle phase. Cite sources." > data/t1_target_market.md
notebooklm ask "List 3-5 buyer segments: demographics, behavior, spending." > data/t2_segments.md
notebooklm ask "Which segments keep vs discard? 3 filter criteria." > data/t3_filter.md

notebooklm use <T46_ID>
notebooklm ask "3 user personas: goals, behaviors, pain points. Cite evidence." > data/t4_personas.md
notebooklm ask "Top 10 user needs ranked by importance." > data/t5_user_needs.md
notebooklm ask "Which needs NOT served by existing solutions?" > data/t6_unmet_needs.md

notebooklm use <T7_ID>
notebooklm ask "PMF evidence: demand signals, willingness to pay." > data/t7_pmf.md

notebooklm use <T89_ID>
notebooklm ask "MoSCoW feature prioritization from unmet needs." > data/t8_features.md
notebooklm ask "User stories INVEST format for MUST features." > data/t9_user_stories.md
```

**Done. 9 lệnh = 9 files .md. Product Tower đọc trực tiếp.**

### PHASE 4: HUMAN RESEARCH (1-2 tuần)

5-10 interviews → upload notes vào T4-6 notebook → re-extract Phase 3.

```bash
notebooklm use <T46_ID>
notebooklm source add "./interview_user1.pdf"
# Re-run Phase 3 queries cho T4-T7
```

---

## INCREMENTAL UPDATE (data mới hàng tuần)

```bash
# 1. Add new sources vào notebook liên quan
notebooklm use <T0_ID>
notebooklm source add "./new_report.pdf"

# 2. Re-extract CHỈ notebooks có data mới
notebooklm ask "Summarize NEW info not in previous analysis." > data/t1_target_market_update.md

# 3. Merge hoặc replace .md file cũ
```

---

## LOCAL FILE STRUCTURE

```
[project]/data/
├── t1_target_market.md
├── t2_segments.md
├── t3_filter.md
├── t4_personas.md
├── t5_user_needs.md
├── t6_unmet_needs.md
├── t7_pmf.md
├── t8_features.md
├── t9_user_stories.md
└── _notebook_ids.json    ← { "T0": "id", "T13": "id", ... }
```

---

## TOOL REFERENCE

| Tool | Dùng cho | Phase |
|------|----------|-------|
| `notebooklm-py` | RAG hub + extract → .md | 1-3 |
| `Apify` | Google Trends, social scraping | 2 |
| `OSINT` | Deep competitor intel | 2 |
| Manual Interview | PMF validation | 4 |

---

## CONSTRAINTS

- 🚫 **KHÔNG** giả định — query notebook, cite sources
- 🚫 **KHÔNG** skip Phase 4 interviews
- 🚫 **KHÔNG** re-process unchanged notebooks
- ✅ **LUÔN** save output thẳng .md (không qua ETL layer)
- ⚠️ Free: 50 sources/notebook × 5 = 250 total | 50 chats/day | 10 Deep Research/month
