---
name: user-discovery
description: |
  Khám phá user: build personas, map user needs, tìm unmet needs. 
  Product Tower tầng 4-6 (Discovery). Kích hoạt khi user nói "persona", 
  "user needs", "interview user", "unmet needs", "khảo sát khách hàng",
  "user research", hoặc cần hiểu USER THẬT SỰ CẦN GÌ trước khi build.
triggers:
  - "persona"
  - "user persona"
  - "user needs"
  - "unmet needs"
  - "interview user"
  - "user research"
  - "khảo sát"
  - "khách hàng cần gì"
---

# Goal

Giúp founder hiểu user THẬT SỰ cần gì (không phải founder NGHĨ user cần gì). 
Tầng này quyết định build CÁI GÌ — sai ở đây = build thứ không ai dùng.

> **Ai quyết**: Product Manager (mũ PM)
> **Input**: Filtered segments từ `@market-segmentation`
> **Output**: Unmet needs list → input cho `@pmf-validator`

---

# Instructions

## Tầng 4: USER PERSONAS — "Ai là user thật?"

> ⚠️ **Persona ≠ Market Segment!**
> - Segment: phân theo demographic (tuổi, thu nhập)
> - Persona: phân theo **HÀNH VI + MỤC ĐÍCH** khi dùng sản phẩm

**Cách build personas:**

1. **Thu thập data** (chọn ít nhất 1):
   - Interview 5-10 người trong target segment
   - Survey online (Google Forms, Typeform)
   - Quan sát hành vi thật (contextual inquiry)
   - Phân tích data có sẵn (analytics, forum, review)

2. **Gom pattern** — tìm nhóm người có cùng:
   - Mục đích khi dùng sản phẩm (goal)
   - Hành vi tiêu biểu (behavior)
   - Pain points chính (frustration)
   - Kênh tiếp cận (touchpoint)

3. **Đặt tên + mô tả** — 2-4 personas, mỗi persona:

```
┌─────────────────────────────────────────┐
│ PERSONA: [Tên đại diện]                │
├─────────────────────────────────────────┤
│ Demographic: [tuổi, nghề, thu nhập]    │
│ Goal:        [mục đích khi dùng SP]    │
│ Behavior:    [hành vi tiêu biểu]       │
│ Pain Point:  [vấn đề lớn nhất]         │
│ Touchpoint:  [kênh tiếp cận]           │
│ Quote:       "[câu nói đại diện]"      │
└─────────────────────────────────────────┘
```

> 💡 **Lưu ý**: Có personas NGOÀI target segment nhưng VẪN quan trọng.
> VD: Thư ký book phòng cho sếp — không phải target nhưng là touchpoint quan trọng.

---

## Tầng 5: USER NEEDS (PRIORITIZED) — "Họ cần gì?"

**Quy trình:**

1. **Hỏi đúng câu hỏi** — cho mỗi persona:
   ```
   "Khi [situation liên quan thị trường], bạn cần gì?"
   "Việc khó nhất trong [domain] của bạn là gì?"
   "Bạn đang dùng công cụ gì? Cái gì khó chịu nhất?"
   ```

2. **Liệt kê TẤT CẢ needs** (không lọc, không đánh giá):
   - Sử dụng post-it method: 1 need = 1 card
   - Group theo category

3. **Prioritize** bằng Impact × Frequency matrix:

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

**Output tầng 5:** Danh sách needs xếp hạng từ cao → thấp

---

## Tầng 6: UNMET NEEDS ⭐ — "Cái gì CHƯA AI solve?"

**3 câu hỏi filter (cho từng need trong danh sách):**

| # | Câu hỏi | "Có" → | "Không" → |
|---|---------|--------|-----------|
| 1 | "Đã có ai solve chưa?" | LOẠI (đã có solution) | GIỮ |
| 2 | "Có trong khả năng mình không?" | GIỮ | LOẠI (ngoài scope) |
| 3 | "Mình có thể solve hơn competitor?" | ⭐ UNMET NEED! | LOẠI (không differentiate) |

**Output format:**

```
📋 UNMET NEEDS ANALYSIS — [Project]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Need: _______________
  ├ Đã có ai solve? [Có/Không] → [Ai?]
  ├ Trong khả năng? [Có/Không] → [Tại sao?]
  └ Solve hơn competitor?  [Có/Không] → [Bằng cách nào?]
  → STATUS: [⭐ UNMET / ❌ LOẠI / 🟡 MAYBE]

... (repeat for each need)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
UNMET NEEDS FOUND: [số]
→ Đây là CƠ HỘI KINH DOANH → input cho @pmf-validator
```

---

## RESOURCE: INTERVIEW SCRIPT (Tiếng Việt, 15-20 phút)

> Script dùng khi interview user để validate tầng 4-6.
> Gọi điện / gặp mặt / Zoom. KHÔNG dùng form — cần follow-up questions.

### Mở đầu (2 phút)
```
"Chào anh/chị [tên], cảm ơn đã dành thời gian.
Tôi đang tìm hiểu về [domain] để build 1 công cụ hỗ trợ.
Không có câu trả lời đúng/sai — tôi muốn hiểu trải nghiệm thật của anh/chị.
Cuộc nói chuyện khoảng 15 phút, bắt đầu nhé?"
```

### Phần 1: Context + Behavior (5 phút)
```
1. "Anh/chị làm gì liên quan [domain]?" (→ demographic + role)
2. "Thường thì khi cần [task], anh/chị làm thế nào?" (→ behavior)
3. "Mức độ thường xuyên?" (→ frequency)
4. "Đang dùng công cụ/dịch vụ gì để hỗ trợ?" (→ current solution)
```

### Phần 2: Pain Points (5 phút)
```
5. "Có gì KHÔNG HÀI LÒNG với cách hiện tại?" (→ pain point)
6. "Nếu có đũa thần, anh/chị muốn thay đổi gì?" (→ ideal state)
7. "Lần gần nhất gặp khó khăn với [task] là khi nào? Chuyện gì xảy ra?"
   (→ specific story, CỰC GIÁ TRỊ)
```

### Phần 3: Willingness to Pay (3 phút)
```
8. "Nếu có tool giải quyết [pain point], anh/chị có dùng không?"
9. "Sẵn sàng trả bao nhiêu / tháng cho giải pháp đó?"
10. "Đã từng trả tiền cho công cụ tương tự chưa? Bao nhiêu?"
```

### Kết thúc (2 phút)
```
"Cảm ơn anh/chị! Có gì anh/chị muốn chia sẻ thêm không?
Khi tool sẵn sàng, anh/chị có muốn thử trước không?"
(→ lấy early adopter)
```

### Hướng dẫn phân tích sau interview

| Sau 5 interviews | Tìm |
|-------------------|-----|
| **Patterns** | 3+ người nói cùng 1 pain point = real need |
| **Outliers** | 1 người nói khác = có thể là edge case hoặc insight mới |
| **Quotes** | Ghi lại câu nói hay → dùng cho marketing sau |
| **Numbers** | Bao nhiêu % sẵn sàng trả tiền? Trả bao nhiêu? |

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

Tao sẽ giúp build personas → map needs → tìm unmet needs.
```

---

# Examples

## Ví dụ 1: BĐS — Có interview data

**Input:** "Tao đã interview 7 người mua nhà lần đầu ở khu metro HCM. Data đây."

**Output:**
```
🔍 USER DISCOVERY — BDSmetro (First-time Buyer segment)

T4. PERSONAS (from 7 interviews):

┌─────────────────────────────────────────┐
│ PERSONA 1: "So sánh kỹ Tùng"           │
├─────────────────────────────────────────┤
│ Demo:      IT, 28 tuổi, 25-30tr/tháng  │
│ Goal:      Mua căn đầu tiên, ở lâu dài │
│ Behavior:  Search 3-5 trang, so giá,   │
│            xem review, cuối tuần đi coi │
│ Pain:      "Giá trên web khác giá thật" │
│ Touch:     Zalo group, batdongsan.com.vn│
│ Quote:     "Tao mất 3 tháng chỉ để biết│
│            giá thật khu này bao nhiêu"  │
│ Source:    👤 Interview #2, #5, #7      │
└─────────────────────────────────────────┘

T5. USER NEEDS (Impact × Frequency):
| # | Need | Impact | Freq | Priority | Source |
|---|------|--------|------|----------|--------|
| 1 | Giá thật (không fake) | ⭐ CAO | CAO | ⭐ MUST SOLVE | 👤 7/7 nói |
| 2 | So sánh khu vực nhanh | CAO | CAO | ⭐ MUST SOLVE | 👤 5/7 nói |
| 3 | Biết tiện ích quanh | THẤP | CAO | 🟢 CONVENIENCE | 👤 3/7 nói |

T6. UNMET NEEDS:
| Need | Đã có solve? | Khả năng? | Hơn competitor? | Status |
|------|-------------|-----------|-----------------|--------|
| Giá thật | ❌ Không (web toàn giá ảo) | ✅ Có (crawl + verify) | ✅ Differentiate | ⭐ UNMET |
| So sánh | 🟡 Partial (batdongsan có nhưng UX kém) | ✅ Có | ✅ Metro-focused | ⭐ UNMET |

UNMET NEEDS: 2 → input cho @pmf-validator
```

## Ví dụ 2: E-wallet — Chưa có interview (desk research only)

**Input:** "Tao target tiểu thương, chưa interview ai"

**Output:**
```
🔍 USER DISCOVERY — E-wallet MSME

⚠️ WARNING: Chưa interview user thật. Output sẽ tag 🤖 60%.
   Recommend: interview 5+ tiểu thương trước khi proceed.

T4. PERSONAS (🤖 AI inference — 60% confidence):

┌─────────────────────────────────────────┐
│ PERSONA 1: "Chị Lan Bán Vải" 🤖        │
├─────────────────────────────────────────┤
│ Demo:      Tiểu thương, 35-50, chợ     │
│ Goal:      Thu tiền nhanh, không mất    │
│ Behavior:  Dùng điện thoại cơ bản,     │
│            chuyển khoản bằng SMS banking│
│ Pain:      "Đếm tiền mặt cuối ngày mệt"│
│ Source:    🤖 AI guess từ desk research │
└─────────────────────────────────────────┘

⚠️ Persona này cần validate bằng interview thật.
   PMF penalty: -2 (desk research only)

→ RECOMMEND: Đi chợ, nói chuyện 5 tiểu thương → re-run discovery
```

---

# Constraints

- 🚫 **KHÔNG** build personas từ giả định — phải có data (dù ít)
- 🚫 **KHÔNG** skip interview — minimum 5 conversations
- 🚫 **KHÔNG** nhầm Segment với Persona (demographic ≠ behavioral)
- ✅ **LUÔN** hỏi "đã validate với user thật chưa?" cho mỗi need
- ✅ **LUÔN** phân biệt: Need đã có solution vs Need chưa ai solve
- ⚠️ **Solo founder trap**: Founder nghĩ mình biết user cần gì = NGUY HIỂM NHẤT

## 🔄 ERROR RECOVERY
- Nếu thiếu T3 filter → cảnh báo "Foundation chưa xong. Chạy @market-segmentation trước"
- Nếu chỉ có desk research → proceed nhưng tag 🤖 60%, cảnh báo PMF penalty
- Nếu interview < 5 người → cảnh báo "Chưa đủ sample. Patterns chưa reliable"
- Nếu không tìm thấy unmet needs → suggest pivot segment hoặc broaden scope
- Nếu user skip interview → tag toàn bộ output ⚠️ UNVALIDATED

---

## HANDOFF

Khi tầng 4-6 hoàn thành:
```
✅ Discovery hoàn thành.
   Personas: [list]
   Unmet Needs: [list]

→ Bước tiếp: Chạy @pmf-validator để validate Value Proposition 
  và check Product-Market Fit signals.
```
