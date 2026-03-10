---
name: market-research
version: 2.1
description: |
  Thu thập data thị trường để feed vào Product Tower T1-T9.
  Product Tower Tầng 0 (Data Foundation).
  Workflow: Google Deep Research prompt → save t0_deep_research.md → Product Tower cascade.
  Output: data/t0_deep_research.md → Product Tower T1-T9 consume trực tiếp.
triggers:
  - "research market"
  - "thu thập data"
  - "market data"
  - "tầng 0"
  - "market research"
  - "deep research"
  - "T0"
---

# PROTOCOL: MARKET_RESEARCH (Product Tower — Tầng 0)

## VAI TRÒ

**Market Research Lead** — thu thập + tổ chức data thị trường bằng Deep Research.

> **Output**: `data/t0_deep_research.md` → Product Tower T1-T9 đọc trực tiếp
> **Tool**: Google Deep Research (Gemini Advanced) hoặc tương đương
> **Thời gian**: 2-10 phút chạy Deep Research + 10 phút review

---

## WORKFLOW: DEEP RESEARCH → FILL DATA

### Kiến trúc

```
User input (industry + market)
        │
        ▼
┌─────────────────────────────┐
│  MEGA PROMPT (7 phần)       │
│  Copy → Fill [PLACEHOLDER]  │
│  → Paste vào Deep Research  │
└──────────┬──────────────────┘
           │ 2-10 phút
           ▼
┌─────────────────────────────┐
│  Deep Research Output       │
│  (50-100KB, 40+ citations)  │
└──────────┬──────────────────┘
           │
           ▼
┌─────────────────────────────┐
│  data/t0_deep_research.md   │
│  Structured 7 sections      │
│  Confidence: 📊 80%         │
└──────────┬──────────────────┘
           │
           ▼
   Product Tower T1-T9 skills
   READ t0_deep_research.md
```

---

## MEGA PROMPT TEMPLATE

> Copy prompt dưới đây, thay `[PLACEHOLDER]`, paste vào Google Deep Research.

````markdown
Tôi đang nghiên cứu thị trường để xây dựng sản phẩm: [TÊN SẢN PHẨM]

Thị trường mục tiêu: [QUỐC GIA / KHU VỰC]
Ngành: [NGÀNH / LĨNH VỰC]

Hãy nghiên cứu TOÀN DIỆN và trả lời TẤT CẢ các phần sau. Mỗi data point PHẢI có source link.

---

## PHẦN 1: MARKET SIZE & GROWTH (cho T1 Target Market)

1. Quy mô thị trường (TAM/SAM/SOM):
   - Global market size (USD, năm gần nhất)
   - Regional market size ([KHU VỰC])
   - Local market size ([QUỐC GIA]) nếu có
   - Projected growth (CAGR, forecast đến 2030)

2. Market drivers (5 yếu tố thúc đẩy tăng trưởng)
3. Market inhibitors (5 yếu tố kìm hãm)
4. Timing catalysts (tại sao BÂY GIỜ là đúng lúc)

---

## PHẦN 2: SEGMENTS & CUSTOMER PROFILES (cho T2-T3 Segmentation)

1. Phân khúc khách hàng hiện tại (3-5 segments):
   - Ai mua? (demographic + behavioral)
   - Bao nhiêu người?
   - Chi bao nhiêu/tháng/năm?
   - Mua ở đâu? (channels)

2. Segment nào tăng trưởng nhanh nhất?
3. Segment nào bị underserved (chưa ai phục vụ tốt)?
4. Pricing sensitivity theo từng segment

---

## PHẦN 3: COMPETITOR LANDSCAPE (cho T0 + T6 Unmet Needs)

1. Top 10 competitors (trực tiếp + gián tiếp):
   - Tên, website, founding year
   - Funding/revenue (nếu có)
   - Pricing model + giá cụ thể
   - Điểm mạnh / điểm yếu
   - Target segment chính

2. Competitive positioning map:
   - Trục X: [gợi ý: Price low→high]
   - Trục Y: [gợi ý: Feature basic→advanced]

3. Gap analysis: Điều gì CHƯA AI LÀM?
4. Barriers to entry cho new players

---

## PHẦN 4: USER BEHAVIOR & NEEDS (cho T4-T5 Personas + Needs)

1. Hành vi mua sắm/sử dụng hiện tại của khách hàng:
   - Họ đang giải quyết vấn đề này bằng cách nào?
   - Pain points lớn nhất (top 5)
   - Frequency of need (daily/weekly/monthly)

2. User journey hiện tại (từ phát hiện vấn đề → chọn giải pháp → mua → dùng)
3. Willingness to pay: khách sẵn sàng trả bao nhiêu?
4. Decision factors: họ chọn dựa trên gì? (giá/chất lượng/tốc độ/brand?)

---

## PHẦN 5: RISKS & FAILURES (cho Counter Search AB1)

1. Case studies thất bại trong ngành (3-5 cases):
   - Tên công ty, năm, lý do thất bại
   - Bài học rút ra

2. Rủi ro pháp lý / regulatory:
   - Luật hiện hành liên quan
   - Xu hướng regulatory (đang siết hay nới?)

3. Rủi ro công nghệ:
   - Tech stack đang thay đổi thế nào?
   - Commoditization risk?

4. Counter-arguments cho 3 giả định lạc quan nhất về thị trường này

---

## PHẦN 6: SUPPLY & DEMAND DYNAMICS (cho T1 + T3 Filter)

1. Supply side: Ai đang cung cấp? Có đủ không? Bottleneck ở đâu?
2. Demand side: Demand tăng hay giảm? Seasonal patterns?
3. Price trends: Giá đang tăng hay giảm? Tại sao?
4. Search trends: Google Trends cho [3-5 KEYWORDS CHÍNH] — rising hay declining?

---

## PHẦN 7: BUSINESS MODEL PATTERNS (cho T7 PMF + T8 Features)

1. Revenue models phổ biến trong ngành:
   - SaaS subscription
   - Usage-based
   - Commission/marketplace
   - Freemium → premium

2. Unit economics benchmark:
   - CAC (Customer Acquisition Cost)
   - LTV (Lifetime Value)
   - Churn rate
   - Payback period

3. Go-to-market strategies đang hoạt động:
   - Channels hiệu quả nhất
   - Content marketing hay paid ads?
   - Community-led hay sales-led?

---

## FORMAT YÊU CẦU

- Mỗi data point phải có SOURCE LINK
- Phân biệt: data thật (📊) vs estimate (🔮) vs opinion (💭)
- Nếu không tìm được data cho [QUỐC GIA], dùng data regional hoặc global và ghi rõ
- Ưu tiên data từ 2024-2026
- Output bằng tiếng Việt, thuật ngữ chuyên ngành giữ tiếng Anh
````

---

## CÁCH DÙNG (Step-by-Step)

```
Bước 1: Copy mega prompt ở trên
Bước 2: Thay [PLACEHOLDER] bằng info sản phẩm cụ thể
Bước 3: Paste vào Google Deep Research (Gemini Advanced)
Bước 4: Đợi 2-10 phút để Deep Research chạy
Bước 5: Save output → data/t0_deep_research.md
Bước 6: Chạy Product Tower:
        "chạy product tower cho [project], dùng data trong t0_deep_research.md"
```

### Multi-source (Optional — nâng confidence)

Nếu muốn tăng data quality, chạy thêm 1-2 Deep Research engine:

```
Source 1: Google Gemini Deep Research (primary)     → 50-100KB
Source 2: Grok Deep Search (cross-validate)          → 5-10KB  
Source 3: Perplexity Pro Search (supplement)          → 5-10KB

→ Merge tất cả vào 1 file: data/t0_deep_research.md
→ Ghi rõ source inventory ở đầu file
```

---

## OUTPUT FORMAT (data/t0_deep_research.md)

File output PHẢI có structure sau:

```markdown
# T0: Deep Research — [TÊN SẢN PHẨM] [THỊ TRƯỜNG]

> **Product Tower T0 — Market Research Data**
> **Ngày:** [YYYY-MM-DD]
> **Sources:** [list Deep Research engines used]
> **Confidence:** 📊 80% (cited research data)

---

## DATA SOURCES INVENTORY

| # | Source | Type | Size | Coverage |
|---|--------|------|------|----------|
| 1 | [Engine 1] | [type] | [size] | [sections covered] |

**Total citations:** [N]+ sources

---

## PHẦN 1: MARKET SIZE & GROWTH
[data...]

## PHẦN 2: SEGMENTS & CUSTOMER PROFILES
[data...]

## PHẦN 3: COMPETITOR LANDSCAPE
[data...]

## PHẦN 4: USER BEHAVIOR & NEEDS
[data...]

## PHẦN 5: RISKS & FAILURES (Counter-Search AB1 Data)
[data...]

## PHẦN 6: SUPPLY & DEMAND DYNAMICS
[data...]

## PHẦN 7: BUSINESS MODEL PATTERNS
[data...]

---

## DATA SATURATION CHECK

| Phần | Coverage | Sources | Confidence |
|------|----------|---------|------------|
| Market Size | ✅/⚠️/❌ | [N] sources | 📊/🤖 |
| ... | ... | ... | ... |

> **T0 Status: ✅ SATURATED / ⚠️ PARTIAL / ❌ INSUFFICIENT**
```

---

## CONFIDENCE & PMF PENALTY

| Data source | Tag | Confidence | PMF Penalty |
|-------------|-----|------------|-------------|
| Không có gì | — | 0% | ❌ Cannot run |
| AI self-guess (không Deep Research) | 🤖 | 60% | -2.0 |
| Deep Research (1 source) | 📊 | 80% | -1.0 |
| Deep Research + Counter-search (AB1) | 📊 | 80% | -0.5 |
| Deep Research + Full AB (AB1-AB4) | 📊👤 | 90%+ | 0 |

> ✅ **LUÔN** ghi confidence tag trên mỗi data point trong output

---

## MAP VỚI 3-LOOP PROTOCOL

```
LOOP 1 — Deep Research (data/loop1/)
   Chạy mega prompt → save t0_deep_research.md
   AI chạy T1-T6 từ data này
   Confidence: 📊 80% | PMF penalty: -1.0

LOOP 2 — Counter-Research (data/loop2/)
   AB1: search_web "thất bại [industry]"
   AB2: @sparring-partner challenge
   Update t0_deep_research.md (Phần 5 enriched)
   Tạo delta_report.md
   Confidence: 📊 80% | PMF penalty: -0.5

LOOP 3 — Real Human Data (data/loop3/)
   AB3: Field observation
   AB4: 5+ interviews (Mom Test)
   Validate/kill hypotheses từ Loop 1-2
   Tạo delta_report.md
   Confidence: 👤 90%+ | PMF penalty: 0
```

---

## DATA SATURATION CRITERIA

T0 đủ data khi:

| Criteria | Threshold | Check |
|----------|-----------|-------|
| Tất cả 7 phần có data | 7/7 sections filled | □ |
| Mỗi phần có ≥3 cited sources | ≥21 total citations | □ |
| TAM/SAM/SOM có số cụ thể | 3 numbers with sources | □ |
| ≥3 competitors với detail | Name + funding + pricing | □ |
| ≥3 user pain points | With survey % hoặc quote | □ |
| ≥1 failure case study | With year + reason | □ |
| Business model benchmarks | CAC, LTV, churn | □ |

> Nếu ≥5/7 criteria pass → **T0 SATURATED** → Proceed to T1-T9
> Nếu <5/7 → Chạy thêm Deep Research hoặc manual research

---

## TOOL REFERENCE

| Tool | Dùng cho | Khi nào |
|------|----------|---------|
| Google Deep Research (Gemini Advanced) | Primary data collection | Loop 1 |
| Grok Deep Search | Cross-validation | Loop 1 (optional) |
| Perplexity Pro | Supplement | Loop 1 (optional) |
| `search_web` | Counter-search (failures, risks) | Loop 2 (AB1) |
| `@sparring-partner` | Red team challenge | Loop 2 (AB2) |
| Manual interview | Real human validation | Loop 3 (AB4) |
| Field observation | Market ground truth | Loop 3 (AB3) |

---

## CONSTRAINTS

- 🚫 **KHÔNG** giả định data — phải có source hoặc ghi rõ 🤖
- 🚫 **KHÔNG** skip Phần 5 (Risks & Failures) — đây là AB1 data
- 🚫 **KHÔNG** chạy T7 PMF nếu T0 chưa SATURATED
- ✅ **LUÔN** save output thẳng `data/t0_deep_research.md`
- ✅ **LUÔN** ghi Data Sources Inventory ở đầu file
- ✅ **LUÔN** chạy Data Saturation Check ở cuối file
- ✅ **LUÔN** tag confidence (📊/🤖/🔮/💭) trên mỗi data point
