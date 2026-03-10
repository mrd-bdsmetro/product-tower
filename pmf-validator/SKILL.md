---
name: pmf-validator
description: |
  Validate Product-Market Fit bằng 10 PMF signals, Sean Ellis Test, 
  Revenue Model check, và Anti-Bias penalty scoring. Product Tower tầng 7 
  (Strategy — HARD GATE). Kích hoạt khi user nói "PMF", "validate idea",
  "product-market fit", "check PMF", hoặc cần quyết định CÓ NÊN BUILD KHÔNG.
triggers:
  - "PMF"
  - "product-market fit"
  - "validate idea"
  - "validate PMF"
  - "check PMF"
  - "có nên build"
  - "đáng để build"
---

# Goal

Quyết định sản phẩm CÓ NÊN BUILD hay không. Tầng 7 là **HARD GATE** — 
fail ở đây = KHÔNG được lên tầng 8+. Chấm 10 PMF signals + Sean Ellis Test +
Revenue Model → output GO/NO-GO decision với adjusted score.

> **Ai quyết**: CEO / Founder + Data
> **Input**: T1-T6 data + Anti-Bias Layer (AB1-AB4)
> **Output**: PMF score (raw + adjusted) + GO/NO-GO decision

---

# Instructions

## GATE CHECK — TRƯỚC KHI BẮT ĐẦU

```
🛑 PRE-VALIDATION GATE CHECK

Checking required inputs...
  □ data/t4_personas.md        → [EXISTS/MISSING]
  □ data/t5_user_needs.md      → [EXISTS/MISSING]
  □ data/t6_unmet_needs.md     → [EXISTS/MISSING]

Checking Anti-Bias Layer...
  □ data/counter_search.md     → [EXISTS/MISSING]
  □ data/red_team_challenge.md → [EXISTS/MISSING]
  □ data/field_notes.md        → [EXISTS/MISSING]
  □ data/interview_notes.md    → [EXISTS/MISSING]

IF T4-T6 MISSING:
  → BLOCKED. "Hoàn thành Discovery (T4-T6) trước."

IF Anti-Bias MISSING:
  → WARNING. Proceed nhưng apply PMF penalty.
  → User có thể: "force skip AB[X]" → ghi nhận risk
```

---

## 10 PMF SIGNALS

Đánh giá tuần tự, mỗi signal = STRONG / MODERATE / WEAK / NO DATA:

| # | Signal | Câu hỏi cần trả lời | Source |
|---|--------|---------------------|--------|
| 1 | **Market demand exists** | Thị trường đủ lớn? CAGR bao nhiêu? | T1 data, reports |
| 2 | **Users actively searching** | Có người tìm kiếm solution? Google Trends? | Search data |
| 3 | **Problem is real & painful** | Có pain point thật? Documented? | T5, T6 data |
| 4 | **No existing solution** | Đã có ai solve chưa? | T6 unmet needs |
| 5 | **Precedent exists** | Có ai đã thành công ở thị trường khác? | Desk research |
| 6 | **Willingness to pay** | User sẵn sàng trả tiền? Bao nhiêu? | Interviews, surveys |
| 7 | **Timing is right** | Tại sao BÂY GIỜ? Catalyst event? | Market context |
| 8 | **Solo founder feasible** | 1 người có thể build Phase 1? | Tech + resource check |
| 9 | **Distribution channel** | Có kênh reach user miễn phí? | Marketing audit |
| 10 | **Competitive moat** | Có gì unique mà đối thủ không copy dễ? | Strategy analysis |

### Scoring

```
STRONG   = 1.0 điểm  (có evidence mạnh, ≥2 sources)
MODERATE = 0.5 điểm  (có evidence nhưng chưa chắc chắn)
WEAK     = 0.25 điểm (chỉ có giả định, 1 source)
NO DATA  = 0 điểm    (không có gì)
```

**PMF Raw Score** = Tổng / 10 × 10 (scale to 10)

---

## SEAN ELLIS TEST

> "Nếu [product] không tồn tại nữa, bạn sẽ thấy thế nào?"

Cho MỖI persona trong T4:

| Persona | Response (predicted/real) | Level |
|---------|--------------------------|-------|
| [Tên] | "[trả lời]" | Very Disappointed / Somewhat / Not |

**Benchmark:** ≥40% "Very Disappointed" = PASS

### Nếu có interview data (AB4):
- Dùng câu trả lời THẬT → score cao hơn
- Nếu chỉ predict → tag 🤖 60%

---

## REVENUE MODEL VALIDATION

Kiểm tra 4 yếu tố:

| Check | Câu hỏi | Red Flag |
|-------|---------|----------|
| **WTP** | User trả bao nhiêu? Có precedent? | "Free forever" mindset |
| **Pricing tiers** | Free → Paid → Enterprise make sense? | Single tier only |
| **Unit economics** | CAC < LTV? Margin dương? | CAC > LTV |
| **Revenue timeline** | Bao lâu mới có revenue? | > 12 tháng = risky cho solo |

---

## PMF PENALTY TABLE (từ Product Tower v3.0)

```
Data quality              │ Penalty │ Adjusted PMF
──────────────────────────┼─────────┼─────────────
Desk research only        │ -2      │ raw - 2
+ Counter-search (AB1)    │ -1      │ raw - 1
+ Red team (AB1+AB2)      │ -0.5    │ raw - 0.5
+ Full anti-bias (AB1-4)  │  0      │ raw
```

---

## OUTPUT TEMPLATE

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🎯 PMF VALIDATION — [Tên Project]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📋 PMF SIGNAL CHECKLIST
| # | Signal             | Evidence                    | Score     |
|---|--------------------|-----------------------------| ----------|
| 1 | Market demand      | [evidence + source tag]     | ✅/⚠️/❌ |
| ...                                                               |

PMF RAW:      ___/10
PENALTY:      -___ (reason: ___)
PMF ADJUSTED: ___/10

📊 SEAN ELLIS TEST
| Persona | Response | Level |
|...                         |
Result: ___% Very Disappointed → [PASS/FAIL]

💰 REVENUE MODEL
| Check | Result | Flag |
|...                    |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
VERDICT: [GO ✅ / NO-GO ❌ / BORDERLINE ⚠️]
PMF: ___/10 (raw ___, adjusted ___, penalty -___)
ANTI-BIAS: AB1 [✅/❌] AB2 [✅/❌] AB3 [✅/❌] AB4 [✅/❌]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Verdict Rules

```
PMF(adjusted) ≥ 8    → GO ✅ "Build it."
PMF(adjusted) 7-7.9  → BORDERLINE ⚠️ "1 thêm iteration — strengthen weak signals."
PMF(adjusted) < 7    → NO-GO ❌ "Pivot hoặc kill."
```

---

## KHỞI ĐỘNG (INITIALIZATION)

```
🎯 PMF Validator — Product Tower Tầng 7

Anh muốn validate PMF cho project nào? Cho tao biết:
1. Tên project
2. Đã có data T4-T6 chưa? (personas, needs, unmet needs)
3. Đã chạy Anti-Bias Layer chưa? (AB1-AB4)

Tao sẽ chấm 10 PMF signals → Sean Ellis Test → Revenue Model → GO/NO-GO.

⚠️ Chưa có Anti-Bias = PMF bị -2 penalty. Friction = feature.
```

---

# Examples

## Ví dụ 1: GO — BĐS Metro với full anti-bias

**Input:** "Validate PMF cho BDSmetro. Có đầy đủ T0-T6 + AB1-AB4."

**Output:**
```
🎯 PMF VALIDATION — BDSmetro
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📋 PMF SIGNALS (tóm tắt):
| # | Signal | Score | Source |
|---|--------|-------|--------|
| 1 | Market demand | ✅ STRONG (1.0) | 📊 $12B metro BĐS |
| 2 | Users searching | ✅ STRONG (1.0) | 📊 Google Trends ↑35% |
| 3 | Problem real | ✅ STRONG (1.0) | 👤 7/7 interview nói "giá ảo" |
| 6 | WTP | ⚠️ MODERATE (0.5) | 👤 4/7 sẵn sàng trả 50-100K/tháng |
| 10 | Moat | ⚠️ MODERATE (0.5) | 🤖 Metro-focused = niche advantage |

PMF RAW:      7.5/10
PENALTY:      -0 (full anti-bias AB1-4 ✅)
PMF ADJUSTED: 7.5/10

VERDICT: BORDERLINE ⚠️ — Strengthen WTP + Moat, thêm 1 iteration
ANTI-BIAS: AB1 ✅ AB2 ✅ AB3 ✅ AB4 ✅

→ Recommend: 1 thêm iteration — validate pricing model
```

## Ví dụ 2: NO-GO — E-wallet desk research only

**Input:** "Check PMF cho ví điện tử tiểu thương. Chỉ có desk research."

**Output:**
```
🎯 PMF VALIDATION — E-wallet MSME
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🛑 ANTI-BIAS GATE CHECK:
  ❌ AB1 counter_search.md MISSING
  ❌ AB2 red_team_challenge.md MISSING
  ❌ AB3 field_notes.md MISSING
  ❌ AB4 interview_notes.md MISSING
  → PENALTY: -2.0 (desk research only)

PMF RAW:      6.9/10
PENALTY:      -2.0 (desk research only)
PMF ADJUSTED: 4.9/10

VERDICT: ❌ NO-GO (adjusted < 7)

→ Options:
  A) Chạy AB1-AB4 → re-score (estimated adjusted: 6.9-7.5)
  B) Pivot market → quay @market-segmentation
  C) Kill → move on
```

---

# Constraints

- 🚫 **KHÔNG** output PMF score mà không ghi rõ: raw vs adjusted vs penalty
- 🚫 **KHÔNG** cho GO khi PMF(adjusted) < 7
- 🚫 **KHÔNG** skip Sean Ellis Test — bắt buộc cho mọi persona
- ✅ **LUÔN** tag confidence (🤖/📊/👤/✅) trên mỗi evidence
- ✅ **LUÔN** check Anti-Bias files tồn tại trước khi chấm
- ✅ **LUÔN** ghi penalty reason rõ ràng
- ⚠️ PMF 7-8 (borderline) → recommend thêm 1 iteration

## 🔄 ERROR RECOVERY
- Nếu thiếu T4-T6 → BLOCK hoàn toàn, redirect sang @user-discovery
- Nếu thiếu Anti-Bias → proceed nhưng apply penalty, cảnh báo rõ
- Nếu PMF fail → suggest 4 options: pivot market, pivot persona, iterate, kill
- Nếu user "force skip" AB → ghi nhận, apply penalty, tag ⚠️ trên output
- Nếu PMF borderline (7-8) → suggest iterate, KHÔNG rush sang T8

---

## HANDOFF

Khi PMF validated:
```
✅ PMF VALIDATED — [Project]
   PMF: ___/10 (raw ___, adjusted ___, penalty -___)
   Verdict: [GO/BORDERLINE]

→ Bước tiếp: Chạy @feature-scoping để define features + MVP scope.
  Input: T5 (user needs) + T6 (unmet needs) + T7 (PMF signals)
```

Khi PMF fail:
```
❌ PMF FAILED — [Project]
   PMF: ___/10 (adjusted < 7)

→ Options:
  A) Pivot target market → quay lại @market-segmentation (T1)
  B) Pivot personas → quay lại @user-discovery (T4)
  C) Strengthen weak signals → iterate T0 data
  D) Kill project → move on
```
