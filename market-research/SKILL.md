---
name: market-research
version: 3.0
description: |
  Thu thập và tổ chức data thị trường toàn diện để feed vào Product Tower T1-T9.
  Product Tower Tầng 0 (Data Foundation). Sử dụng Google Deep Research mega-prompt
  để generate báo cáo 8 phần với 40+ citations.
  Kích hoạt khi user nói "research market", "thu thập data", "tầng 0", "T0",
  "deep research", "market data", hoặc cần data thị trường cho product mới.
triggers:
  - "research market"
  - "thu thập data"
  - "market data"
  - "tầng 0"
  - "market research"
  - "deep research"
  - "T0"
---

# Instructions

# Goal

Thu thập data thị trường toàn diện (8 phần, 40+ citations) trong 10 phút bằng
Deep Research, thay vì 2 tuần research thủ công. Output = 1 file `.md` mà
Product Tower T1-T9 đọc trực tiếp.

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

## MEGA PROMPT TEMPLATE (v2 — 8 Phần)

> Copy prompt dưới đây, thay `[PLACEHOLDER]`, paste vào Google Deep Research.
> Upgraded từ BDSmetro forensic audit case study.

````markdown
Tôi đang nghiên cứu thị trường để xây dựng sản phẩm: [TÊN SẢN PHẨM]

Thị trường mục tiêu: [QUỐC GIA / KHU VỰC]
Ngành: [NGÀNH / LĨNH VỰC]

Hãy nghiên cứu TOÀN DIỆN và trả lời TẤT CẢ 8 phần sau.
Mỗi data point PHẢI có source link.
Mỗi phần PHẢI có ÍT NHẤT 1 TABLE. Minimum 8 tables tổng.

---

## PHẦN 1: MARKET SIZE & GROWTH (cho T1 Target Market)

Trình bày bằng TABLE:

| Phân loại | Tiêu chí | Giá trị (Năm) | Dự phóng | CAGR | Source |
|-----------|----------|---------------|----------|------|--------|
| TAM (Global) | ... | ... | ... | ... | [link] |
| SAM (Regional) | ... | ... | ... | ... | [link] |
| SOM (Local) | ... | ... | ... | ... | [link] |

1. Market drivers (5 yếu tố thúc đẩy — mỗi yếu tố có SỐ LIỆU kèm source)
2. Market inhibitors (5 yếu tố kìm hãm — mỗi yếu tố có SỐ LIỆU)
3. Timing catalysts (tại sao BÂY GIỜ là đúng lúc — sự kiện cụ thể, năm cụ thể)

---

## PHẦN 2: SEGMENTS & CUSTOMER PROFILES (cho T2-T3 Segmentation)

Trình bày bằng TABLE:

| Segment | Demographics | Quy mô | Chi tiêu/tháng | Behavior | Growth |
|---------|-------------|--------|----------------|----------|--------|
| ... | ... | ... | ... | ... | ... |

1. Segment nào tăng trưởng nhanh nhất? (% YoY)
2. Segment nào bị underserved (chưa ai phục vụ tốt)?
3. Pricing sensitivity theo từng segment (elasticity)

---

## PHẦN 3: COMPETITOR LANDSCAPE (cho T0 + T6 Unmet Needs)

Trình bày bằng TABLE:

| Tên | Funding/Revenue | Segment | Market Share | Điểm mạnh | Điểm yếu | Pricing |
|-----|----------------|---------|-------------|-----------|----------|---------|
| ... | ... | ... | ...% | ... | ... | ... |

1. Competitive positioning map:
   - Trục X: Price (low→high)
   - Trục Y: Feature (basic→advanced)
   - Vẽ vị trí của từng competitor

2. Gap analysis: Điều gì CHƯA AI LÀM? (minimum 3 gaps)
3. Barriers to entry cho new players (vốn, tech, regulatory, network effects)

---

## PHẦN 4: USER BEHAVIOR & NEEDS (cho T4-T5 Personas + Needs)

1. Hành vi hiện tại:
   - Họ đang giải quyết vấn đề này bằng cách nào?
   - Pain points lớn nhất (top 5, MỖI CÁI CÓ % hoặc survey data)
   - Frequency of need (daily/weekly/monthly — có số liệu)

2. User journey: Discovery → Evaluate → Purchase → Use → Churn/Retain
3. Willingness to pay: khách sẵn sàng trả bao nhiêu? (theo segment)
4. Decision factors: giá/chất lượng/tốc độ/brand/trust?

5. **🎭 VANITY METRIC ANALYSIS (Emotion vs Value):**
   - Bao nhiêu % khách mua vì GIẢI PHÁP THỰC SỰ vs mua vì FOMO/status/hype?
   - Brand premium: gap giữa cost base vs giá bán là bao nhiêu %?
   - Nếu bỏ brand, khách có chuyển sang alternative rẻ hơn không?
   - "Thuế ngu" (Stupidity Tax): khách đang trả premium cho cái gì — substance hay vỏ bọc?

---

## PHẦN 5: RISKS & FAILURES (cho Counter Search AB1)

1. Case studies thất bại (3-5 cases, TABLE format):

| Công ty | Năm | Funding | Lý do chết | Bài học |
|---------|-----|---------|-----------|---------|
| ... | ... | ... | ... | ... |

2. Rủi ro pháp lý / regulatory:
   - Luật hiện hành liên quan (tên luật + số + năm)
   - Xu hướng regulatory (đang siết hay nới?)
   - Enforcement cases: có ai bị phạt/cấm chưa?

3. Rủi ro công nghệ:
   - Tech stack đang thay đổi thế nào?
   - Commoditization risk? (feature trở thành commodity?)

4. Counter-arguments cho 3 giả định lạc quan nhất

5. **🛡️ FRAGILITY TEST (Taleb-style):**
   - Nếu top 1 player biến mất ngày mai, thị trường này collapse hay vẫn chạy?
   - Single points of failure trong ngành ở đâu? (1 regulation, 1 tech, 1 player)
   - "Skin in the game": founders/leaders đang ALL-IN hay đang rút dần?
   - Antifragile elements: phần nào của ngành MẠNH HƠN khi gặp stress?

---

## PHẦN 6: SUPPLY & DEMAND DYNAMICS (cho T1 + T3 Filter)

1. Supply side: Ai đang cung cấp? Có đủ không? Bottleneck ở đâu?
2. Demand side: Demand tăng hay giảm? Seasonal patterns?
3. Price trends: Giá đang tăng hay giảm? Tại sao?
4. Search trends: Google Trends cho [3-5 KEYWORDS CHÍNH] — rising hay declining?

5. **🐋 WHALE WATCH (Market Power Analysis):**
   - Top 3 players đang MỞ RỘNG hay THU HẸP? (hiring? firing? closing offices?)
   - VC/Funding direction: tiền đang RÓT VÀO hay RÚT RA khỏi ngành?
   - Media manipulation: có campaign "bơm thổi" bất thường không? (PR surge + thực tế ngược lại)
   - Consolidation signals: M&A, acqui-hire, exit — ai đang nuốt ai?

---

## PHẦN 7: BUSINESS MODEL PATTERNS (cho T7 PMF + T8 Features)

1. Revenue models phổ biến trong ngành (TABLE format):

| Model | Ví dụ | Avg Revenue/User | Margin | Phù hợp khi |
|-------|-------|-------------------|--------|-------------|
| SaaS subscription | ... | ... | ... | ... |
| Usage-based | ... | ... | ... | ... |
| Commission | ... | ... | ... | ... |
| Freemium → premium | ... | ... | ... | ... |

2. Unit economics benchmark:
   - CAC (Customer Acquisition Cost) — theo segment
   - LTV (Lifetime Value) — theo segment
   - LTV/CAC ratio (benchmark ngành)
   - Churn rate (monthly + annual)
   - Payback period

3. **💰 CASHFLOW SIMULATION (Tàn nhẫn mode):**
   - Mô phỏng P&L cho 1 user/unit trong tháng đầu tiên:
     - Revenue per user: [số cụ thể]
     - Cost to serve: [hosting, support, payment processing]
     - Gross margin: [%]
     - CAC payback: [tháng]
   - Breakeven point: cần bao nhiêu users/MRR để hòa vốn?
   - "Vulture Price": mức pricing nào khiến unit economics dương?

4. Go-to-market strategies đang hoạt động:
   - Channels hiệu quả nhất
   - Community-led hay sales-led?
   - Viral coefficient (nếu có data)

---

## PHẦN 8: DUE DILIGENCE / FORENSIC AUDIT (cho Anti-Bias Layer)

> Phần này đào sâu vào "vùng xám" mà desk research thường bỏ qua.

1. **Power Structure (Ai đứng đằng sau?):**
   - Top 5 players: parent company, backing, political connections (nếu relevant)
   - Founder backgrounds: serial entrepreneur hay first-timer?
   - "Skin in the game": founders bỏ bao nhiêu tiền túi vs dùng tiền VC?

2. **Scandal & Fraud History:**
   - Có công ty nào trong top 10 dính scandal/lawsuit/regulatory action?
   - Data breaches, user complaints, class action suits?
   - Glassdoor/employee reviews: nội bộ có vấn đề gì?

3. **Hidden Costs & Traps:**
   - Chi phí ẩn mà user không thấy khi sign up?
   - Lock-in mechanisms: switching cost cao không?
   - "Bait and switch": pricing thay đổi sau khi acquire users?

4. **Market Manipulation Signals:**
   - Fake reviews / inflated metrics?
   - Vanity metrics (MAU, downloads) vs real engagement (DAU, revenue)?
   - Đang báo lỗ nhưng vẫn raise vốn — sustainable hay ponzi?

---

## FORMAT YÊU CẦU

- Mỗi data point phải có **SOURCE LINK**
- Phân biệt: data thật (📊) vs estimate (🔮) vs opinion (💭)
- Nếu không tìm được data cho [QUỐC GIA], dùng data regional/global và ghi rõ
- Ưu tiên data từ **2024-2026**
- Output bằng **tiếng Việt**, thuật ngữ chuyên ngành giữ tiếng Anh
- **BẮT BUỘC**: Mỗi phần có ÍT NHẤT 1 TABLE. Tối thiểu 8 tables tổng
- **BẮT BUỘC**: Mỗi phần có ≥500 words
- **BẮT BUỘC**: Mỗi claim số liệu phải ghi rõ năm + nguồn
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

# Examples

## Ví dụ 1: Ví Điện Tử Việt Nam (FinTech)

**Input:**
```
Tôi đang nghiên cứu thị trường để xây dựng sản phẩm: Ví Điện Tử
Thị trường: Việt Nam | Ngành: FinTech
```

**Output tóm tắt** (200 dòng, 10KB, 40+ citations):
- P1: TAM $2,140B global, SOM $41.6B VN, CAGR 13.9% 📊
- P2: 4 segments (Gen Z, Văn phòng, Tiểu thương, Nông thôn) 📊
- P3: 10 competitors (MoMo, ZaloPay, VNPAY, ShopeePay...) với market share 📊
- P4: Top pain = Feature Bloat 57%, Loyalty 35% chỉ 📊
- P5: Moca chết 07/2024, VietQR commoditize QR payment 📊
- P6: 58M ví kích hoạt, 34M active, bão hòa ảo 📊
- P7: LTV/CAC gần 1:1 ở B2C → nguy hiểm 📊
- P8: MoMo 33M users nhưng 46% số dư <500K 📊
- Saturation: ✅ 7/7 phần, confidence 📊 80%

## Ví dụ 2: Cơm Văn Phòng Delivery (F&B)

**Input:**
```
Sản phẩm: Cơm văn phòng delivery
Thị trường: HCMC | Ngành: F&B
```

**Output tóm tắt** (T0 + Timing check):
- P1: Thị trường food delivery VN $2.1B, CAGR 15% 📊
- P3: GrabFood 45%, ShopeeFood 30%, Baemin exit 2023 📊
- P5: Baemin chết (CAC quá cao), Now -> ShopeeFood (tích hợp) 📊
- Timing: 🟡 WAIT — margin thấp, 2 ông lớn đang đốt tiền, không phải lúc
- Saturation: ⚠️ 5/7 (thiếu field data + interviews)

---

## FALLBACK MODE (khi Deep Research không dùng được)

> Nếu không có Gemini Advanced / Deep Research offline:

```
Fallback Path:
1. Dùng `search_web` + `read_url_content` để research từng phần
2. AI tổng hợp từ kết quả search → fill vào 8 phần
3. Tag tất cả data là 🤖 60% (AI-synthesized, không phải Deep Research)
4. PMF penalty: -2.0 (như desk research only)
5. KHUYẾN CÁO: upgrade lên Deep Research khi có thể
```

| Mode | Tool | Confidence | PMF Penalty | Thời gian |
|------|------|------------|-------------|----------|
| 🟢 Deep Research | Gemini Advanced | 📊 80% | -1.0 | 10 phút |
| 🟡 Fallback | search_web + AI | 🤖 60% | -2.0 | 30-60 phút |
| 🔴 Manual only | User tự research | 👤 varies | depends on AB | 1-2 tuần |

---

# Constraints

- 🚫 **KHÔNG** giả định data — phải có source hoặc ghi rõ 🤖
- 🚫 **KHÔNG** skip Phần 5 (Risks & Failures) — đây là AB1 data
- 🚫 **KHÔNG** chạy T7 PMF nếu T0 chưa SATURATED
- ✅ **LUÔN** save output thẳng `data/t0_deep_research.md`
- ✅ **LUÔN** ghi Data Sources Inventory ở đầu file
- ✅ **LUÔN** chạy Data Saturation Check ở cuối file
- ✅ **LUÔN** tag confidence (📊/🤖/🔮/💭) trên mỗi data point
- ✅ **LUÔN** chọn industry template phù hợp (nếu có) và append vào mega-prompt
