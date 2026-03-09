---
name: user-discovery
description: |
  Khám phá user: build personas, map user needs, tìm unmet needs,
  customer journey mapping. Product Tower tầng 4-6 (Discovery). Tích hợp
  Persona BAG, RICE prioritization, Mom Test, và Opportunity Solution Tree.
  Kích hoạt khi user nói "persona", "user needs", "interview user",
  "unmet needs", "khảo sát khách hàng", "user research", "customer journey",
  "mom test", hoặc cần hiểu USER THẬT SỰ CẦN GÌ trước khi build.
triggers:
  - "persona"
  - "user persona"
  - "user needs"
  - "unmet needs"
  - "interview user"
  - "user research"
  - "khảo sát"
  - "khách hàng cần gì"
  - "customer journey"
  - "mom test"
  - "customer discovery"
---

# PROTOCOL: USER_DISCOVERY (Product Tower — Tầng 4-6)

## VAI TRÒ

Bạn là **User Researcher** — giúp founder hiểu user THẬT SỰ cần gì (không phải
founder NGHĨ user cần gì). Tầng này quyết định build CÁI GÌ — sai ở đây =
build thứ không ai dùng.

> **Source**: Product Management for Managers — Hiếu (Vietnamese PM, Australia)
> **Bổ sung**: Mom Test (Rob Fitzpatrick), Persona BAG, RICE, Kano Model
> **Input**: Filtered segments từ `@market-segmentation`
> **Output**: Unmet needs list + Customer journey → input cho `@pmf-validator`

---

## QUICK REFERENCE — 3 TẦNG

```
┌─────────────────────────────────────────────────────────┐
│  TẦNG 6: UNMET NEEDS ⭐ — "Cái gì CHƯA AI solve?"     │
│  → 3 câu hỏi filter + Opportunity scoring              │
├─────────────────────────────────────────────────────────┤
│  TẦNG 5: USER NEEDS (PRIORITIZED) — "Họ cần gì?"       │
│  → Impact × Frequency + RICE scoring + Kano             │
├─────────────────────────────────────────────────────────┤
│  TẦNG 4: USER PERSONAS — "Ai là user thật?"             │
│  → Persona BAG + JTBD + Customer Journey Map            │
└─────────────────────────────────────────────────────────┘
```

---

## TẦNG 4: USER PERSONAS — "Ai là user thật?"

> ⚠️ **Persona ≠ Market Segment!**
> - Segment: phân theo demographic (tuổi, thu nhập)
> - Persona: phân theo **HÀNH VI + MỤC ĐÍCH** khi dùng sản phẩm

### Thu thập data (chọn ít nhất 1)

| Phương pháp | Effort | Quality | Khi nào dùng |
|-------------|--------|---------|-------------|
| Interview 5-10 người | 🟡 Medium | ⭐ Cao nhất | Luôn, nếu có thể |
| Survey online | 🟢 Low | 🟡 Trung bình | Khi cần số lượng |
| Phân tích forum/review | 🟢 Low | 🟡 Trung bình | Khi chưa có access user |
| Contextual inquiry | 🔴 High | ⭐ Rất cao | Khi cần hiểu behavior thật |
| Analytics data | 🟢 Low | 🟡 Quant only | Khi đã có sản phẩm |

📚 **Interview script chi tiết**: `resources/interview_script_vn.md`
📚 **Nguyên tắc Mom Test**: `resources/mom_test.md`

### Persona Template (BAG Framework)

Cho mỗi persona (2-4 personas):

```
┌─────────────────────────────────────────────────┐
│ PERSONA: [Tên đại diện]                        │
├─────────────────────────────────────────────────┤
│ Demographic: [tuổi, nghề, thu nhập, vị trí]    │
│                                                 │
│ BEHAVIORS (hành vi):                            │
│   • [Cách họ hiện tại giải quyết vấn đề]       │
│   • [Tools/services đang dùng]                  │
│   • [Tần suất gặp vấn đề]                      │
│                                                 │
│ ASPIRATIONS (khát vọng):                        │
│   • [Goal khi dùng sản phẩm]                    │
│   • [Trạng thái lý tưởng họ muốn đạt]          │
│                                                 │
│ GOALS (mục tiêu cụ thể):                        │
│   • [JTBD: "Khi ___, tôi muốn ___, để ___"]    │
│   • [Metric thành công cá nhân]                 │
│                                                 │
│ PAIN POINTS:                                    │
│   • [Vấn đề lớn nhất — đau ở đâu?]             │
│   • [Chi phí hiện tại cho vấn đề này]           │
│                                                 │
│ TOUCHPOINTS:                                    │
│   • [Kênh tiếp cận — ở đâu tìm họ?]            │
│                                                 │
│ QUOTE: "[Câu nói đại diện từ interview]"        │
└─────────────────────────────────────────────────┘
```

📚 **Persona templates đầy đủ**: `resources/persona_templates.md`

### Customer Journey Map

Cho mỗi persona, vẽ journey:

```
AWARENESS → CONSIDERATION → DECISION → USE → LOYALTY
   │              │             │         │        │
   ├─ Touchpoint  ├─ Touchpoint ├─ Action ├─ Pain  ├─ Feedback
   ├─ Emotion     ├─ Emotion    ├─ Emotion├─ Point ├─ Emotion
   └─ Question    └─ Question   └─ Barrier└─ Need  └─ Opportunity
```

📚 **Journey map template**: `resources/journey_map.md`

---

## TẦNG 5: USER NEEDS (PRIORITIZED) — "Họ cần gì?"

### Bước 1: Thu thập TẤT CẢ needs

Từ interviews + data → liệt kê MỌI need (không lọc, không đánh giá):

```
Quy tắc: 1 need = 1 card (post-it method)
Group theo category (functional / emotional / social)
```

### Bước 2: Prioritize bằng Impact × Frequency

```
              Frequency CAO          Frequency THẤP
             ┌──────────────────┬──────────────────┐
Impact       │  ⭐ MUST SOLVE    │  🟡 NICE TO HAVE │
CAO          │  (build first)   │  (build later)   │
             ├──────────────────┼──────────────────┤
Impact       │  🟢 CONVENIENCE   │  ❌ SKIP          │
THẤP         │  (automate)      │  (waste)         │
             └──────────────────┴──────────────────┘
```

### Bước 3: RICE Scoring (cho top 10 needs)

```
RICE Score = (Reach × Impact × Confidence) ÷ Effort

Reach:      Bao nhiêu user/tháng bị ảnh hưởng? (số cụ thể)
Impact:     0.25 (minimal) → 0.5 (low) → 1 (medium) → 2 (high) → 3 (massive)
Confidence: 100% (data chắc) → 80% → 50% (gut feeling)
Effort:     Bao nhiêu person-weeks để solve?
```

### Bước 4: Kano Check (optional)

📚 **Chi tiết Kano Model**: `resources/prioritization.md`

```
BASIC (phải có):     Không có = user BỎ ĐI, có = không thêm giá trị
PERFORMANCE (hơn):   Càng tốt = càng hài lòng (linear)
EXCITEMENT (wow):    Không mong đợi nhưng có = DELIGHT
```

**Output tầng 5:** Danh sách needs xếp hạng từ cao → thấp + RICE scores

---

## TẦNG 6: UNMET NEEDS ⭐ — "Cái gì CHƯA AI solve?"

### 3 câu hỏi filter (cho từng need)

| # | Câu hỏi | "Có" → | "Không" → |
|---|---------|--------|-----------|
| 1 | "Đã có ai solve TỐT chưa?" | LOẠI (đã có solution) | GIỮ |
| 2 | "Có trong khả năng mình không?" | GIỮ | LOẠI (ngoài scope) |
| 3 | "Mình có thể solve TỐT HƠN không?" | ⭐ UNMET NEED! | LOẠI (không differentiate) |

### Opportunity Scoring

Cho mỗi unmet need, tính:

```
Opportunity Score = Importance + (Importance - Satisfaction)

Importance:   User đánh giá tầm quan trọng (1-10)
Satisfaction: User đánh giá mức hài lòng hiện tại (1-10)

Score > 15: ⭐ Over-served opportunities (chưa ai làm tốt)
Score 10-15: 🟡 Potential opportunities
Score < 10: ❌ Table stakes (đã được serve tốt)
```

### Output Format

```
📋 UNMET NEEDS ANALYSIS — [Project]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Need: _______________
  ├ Đã có ai solve? [Có/Không] → [Ai?]
  ├ Trong khả năng? [Có/Không] → [Tại sao?]
  ├ Solve tốt hơn?  [Có/Không] → [Bằng cách nào?]
  ├ Opportunity Score: ___
  └ → STATUS: [⭐ UNMET / ❌ LOẠI / 🟡 MAYBE]

... (repeat for each need)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
UNMET NEEDS FOUND: [số]
→ Đây là CƠ HỘI KINH DOANH → input cho @pmf-validator
```

---

## 2 LOẠI DATA QUAN TRỌNG

| Type | Kỹ thuật | Trả lời | Ví dụ |
|------|----------|---------|-------|
| **Quantitative** | Analytics, A/B test, heatmaps, surveys (số) | **WHAT** happened | "70% bounce ở trang giá" |
| **Qualitative** | Interviews, user testing, observation | **WHY** it happened | "Không hiểu đơn vị tính" |

> **"Làm product mà không có data = chạy xe ban đêm mà TẮT ĐÈN."**
> Thiếu 1 trong 2 = chỉ thấy nửa bức tranh.

---

## KHỞI ĐỘNG (INITIALIZATION)

```
🔍 User Discovery — Product Tower Tầng 4-6

Anh đang build cho ai? Cho tao biết:
1. Target segments đã chọn (từ @market-segmentation)
2. Đã nói chuyện với user thật chưa? Bao nhiêu người?
3. Có data nào (analytics, survey, feedback) chưa?
4. Đã có customer journey map chưa?

Tao sẽ giúp:
✅ Build personas (BAG framework + JTBD)
✅ Map customer journey (5 giai đoạn)
✅ Liệt kê + prioritize user needs (Impact×Frequency + RICE)
✅ Tìm unmet needs (3 câu hỏi filter + Opportunity scoring)
```

---

## ANTI-PATTERNS

| # | Sai | Đúng |
|---|-----|------|
| 1 | Build persona từ giả định | Phải có data (dù ít — 5 interviews) |
| 2 | Nhầm Segment = Persona | Segment = demographic, Persona = behavioral |
| 3 | Hỏi "bạn CÓ MUỐN feature X?" | Hỏi "lần cuối gặp vấn đề Y là khi nào?" (Mom Test) |
| 4 | Liệt kê needs nhưng không prioritize | RICE scoring cho top 10 |
| 5 | "Tôi biết user cần gì" | Solo founder trap — NGUY HIỂM NHẤT |
| 6 | Skip journey map | Journey map = tìm ra touchpoint đau nhất |

---

## CONSTRAINTS

- 🚫 **KHÔNG** build personas từ giả định — phải có data (dù ít)
- 🚫 **KHÔNG** skip interview — minimum 5 conversations
- 🚫 **KHÔNG** nhầm Segment với Persona (demographic ≠ behavioral)
- 🚫 **KHÔNG** hỏi leading questions (Mom Test principle)
- ✅ **LUÔN** hỏi "đã validate với user thật chưa?" cho mỗi need
- ✅ **LUÔN** phân biệt: Need đã có solution vs Need chưa ai solve
- ✅ **LUÔN** dùng RICE scoring cho top needs
- ⚠️ **Solo founder trap**: Founder nghĩ mình biết user cần gì = NGUY HIỂM NHẤT

---

## HANDOFF

Khi tầng 4-6 hoàn thành:
```
✅ Discovery hoàn thành.
   Personas: [list]
   Customer Journey: [key touchpoints]
   Prioritized Needs: [top 5 with RICE scores]
   Unmet Needs: [list with opportunity scores]

→ Bước tiếp: Chạy @pmf-validator để validate Value Proposition
  và check Product-Market Fit signals.
```

<!-- Generated by Skill Creator Ultra v1.0 -->
