---
name: market-segmentation
description: |
  Phân tích thị trường mục tiêu, phân khúc khách hàng, và lọc segment. 
  Product Tower tầng 1-3 (Foundation). Kích hoạt khi user nói "target market", 
  "phân khúc", "segmentation", "chọn thị trường", "thị trường mục tiêu",
  "segment filter", hoặc cần quyết định ĐÁNH VÀO ĐÂU trước khi build.
triggers:
  - "target market"
  - "phân khúc"
  - "segmentation"
  - "segment"
  - "chọn thị trường"
  - "thị trường mục tiêu"
  - "market analysis"
---

# Goal

Giúp founder chọn đúng thị trường, phân khúc khách hàng, và lọc ra segment 
đáng đánh. Đây là nền móng của Product Tower — sai ở đây = cascade failure 
toàn bộ tầng trên.

> **Ai quyết**: CEO / Founder (mũ CEO)
> **Output**: Filtered segment list → input cho `@user-discovery`

---

# Instructions

## Tầng 1: TARGET MARKET — "Đánh vào đâu?"

**2 yếu tố bắt buộc:**

| Yếu tố | Câu hỏi | Red Flag |
|---------|---------|----------|
| **Expertise** | "Mình BIẾT GÌ về thị trường này?" | Chọn vì "hot" nhưng 0 kinh nghiệm |
| **Market Size** | "Thị trường đủ lớn để kiếm tiền?" | Niche quá nhỏ, không scale được |

**Decision Matrix:**

```
            Expertise CAO          Expertise THẤP
           ┌──────────────────┬──────────────────┐
Market     │  ✅ IDEAL         │  ⚠️ Cần partner  │
Size LỚN   │  Đánh full force  │  hoặc học trước  │
           ├──────────────────┼──────────────────┤
Market     │  🟡 Niche play    │  ❌ TRÁNH         │
Size NHỎ   │  Có thể nhưng    │  Không biết +     │
           │  ceiling thấp    │  không có tiền    │
           └──────────────────┴──────────────────┘
```

**Output tầng 1:** 1 thị trường cụ thể (vd: "BĐS khu vực metro HCM")

---

## Tầng 2: MARKET SEGMENTATION — "Có những ai trong thị trường?"

**2 cách phân khúc (dùng cả 2):**

| Phương pháp | Phân theo | Ví dụ (BĐS) |
|-------------|----------|--------------|
| **Demographic** | Tuổi, thu nhập, nghề, vị trí | Trẻ 25-35, thu nhập 20-40tr |
| **Behavioral** | Hành vi mua, mục đích, frequency | Đầu tư lướt sóng vs mua ở |

**Quy tắc phân khúc:**
- 3-5 segments (quá ít = chung chung, quá nhiều = không focus)
- Mỗi segment phải **có hành vi mua khác nhau** (không chỉ khác tuổi)
- Phải **đo lường được** (biết bao nhiêu người, chi bao nhiêu tiền)

**Output tầng 2:** Bảng 3-5 segments với size + behavior + spending pattern

---

## Tầng 3: SEGMENT FILTER — "Loại ai ra?"

**2 loại loại bỏ:**

| Loại | Lý do | Ví dụ |
|------|-------|-------|
| **Không muốn** | Market quá nhỏ, không align strategy, margin thấp | Airbnb loại trẻ em (đi cùng gia đình) |
| **Không thể** | Yêu cầu vượt khả năng, serve không tốt → hại brand | Airbnb loại Luxury (không đáp ứng được) |

**3 câu hỏi filter:**

```
1. "Segment này có ĐỦ LỚN để kiếm tiền?" 
   → Quá nhỏ = loại

2. "Mình có THỂ serve segment này không?"
   → Không đủ năng lực = loại (serve không đạt chuẩn hại hơn không serve)

3. "Segment này có ALIGN với long-term strategy?"
   → Kiếm tiền ngắn hạn nhưng lệch hướng = loại
```

**Output tầng 3:** Remaining segments = tập khách hàng tiềm năng

---

## TEMPLATE: MARKET SEGMENTATION CANVAS

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 MARKET SEGMENTATION CANVAS — [Tên Project]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

T1. TARGET MARKET
   Thị trường: ________________
   Expertise (1-5): ___  |  Market Size: ___
   Lý do chọn: ________________

T2. SEGMENTS (3-5)
   ┌────────────┬──────────┬──────────┬──────────┐
   │ Segment    │ Size     │ Behavior │ Spending │
   ├────────────┼──────────┼──────────┼──────────┤
   │ 1. _______ │ ________ │ ________ │ ________ │
   │ 2. _______ │ ________ │ ________ │ ________ │
   │ 3. _______ │ ________ │ ________ │ ________ │
   │ 4. _______ │ ________ │ ________ │ ________ │
   │ 5. _______ │ ________ │ ________ │ ________ │
   └────────────┴──────────┴──────────┴──────────┘

T3. FILTER RESULT
   ❌ Loại: _______ (lý do: _______)
   ❌ Loại: _______ (lý do: _______)
   ✅ Giữ: _______________________
   ✅ Giữ: _______________________

→ OUTPUT: Filtered segments → input cho @user-discovery
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## CÁCH SỬ DỤNG

### Khi user cần chọn thị trường:
1. Hỏi 2 yếu tố: Expertise + Market Size
2. Dùng Decision Matrix → recommend GO / NO-GO
3. Hướng dẫn phân khúc 3-5 segments
4. Filter → output danh sách segments giữ lại

### Khi user đã có thị trường:
1. Validate: "Expertise + Size có match không?"
2. Review segments: "Đã phân đủ chưa? Có overlap không?"
3. Challenge filter: "Có loại đúng chưa? Có giữ segment nên loại không?"

---

## KHỞI ĐỘNG (INITIALIZATION)

```
📊 Market Segmentation — Product Tower Tầng 1-3

Anh đang nhắm thị trường nào? Cho tao biết:
1. Thị trường / ngành
2. Kinh nghiệm của anh trong ngành đó (1-5)
3. Đã biết ai là khách hàng tiềm năng chưa?

Tao sẽ giúp phân khúc + lọc → tìm ra nhóm KH đáng đánh nhất.
```

---

# Examples

## Ví dụ 1: BĐS Metro — Founder có expertise

**Input:** "Tao sale BĐS 5 năm ở HCM, muốn build app cho thị trường metro"

**Output:**
```
📊 MARKET SEGMENTATION CANVAS — BDSmetro

T1. TARGET MARKET
   Thị trường: BĐS khu vực metro HCM (Line 1, 2)
   Expertise: 5/5 ✅ (5 năm sale BĐS)
   Market Size: ~$12B GTV khu vực metro → ✅ ĐỦ LỚN
   → IDEAL ✅ (Expertise CAO + Market LỚN)

T2. SEGMENTS:
   | Segment | Size | Behavior | Spending |
   |---------|------|----------|----------|
   | First-time buyer 25-35 | 40% | Tìm online, so giá | 1-3 tỷ |
   | Nhà đầu tư lướt sóng | 15% | Mua nhanh, bán nhanh | 2-5 tỷ |
   | Gia đình upgrade | 25% | Nghiên cứu kỹ, tiện ích | 3-7 tỷ |
   | Investor dài hạn | 10% | Cho thuê, ROI-focused | 5-15 tỷ |
   | Corporate relocation | 10% | Bulk, cần nhanh | 10+ tỷ |

T3. FILTER:
   ❌ Corporate relocation (cần quan hệ B2B, solo không serve được)
   ❌ Investor dài hạn (cần data analytics phức tạp, Phase 2)
   ✅ Giữ: First-time buyer, Nhà đầu tư lướt sóng, Gia đình upgrade

→ 3 filtered segments → chạy @user-discovery
```

## Ví dụ 2: FinTech — Founder thiếu expertise

**Input:** "Tao muốn build ví điện tử, chưa có kinh nghiệm fintech"

**Output:**
```
📊 TARGET MARKET ASSESSMENT

Expertise: 1/5 ❌ (chưa có kinh nghiệm fintech)
Market Size: $41.6B VN mobile payment → ✅ LỚN

→ Decision Matrix: ⚠️ CẦN PARTNER hoặc HỌC TRƯỚC
  
⚠️ WARNING: E-wallet VN dominated by MoMo (60%), ZaloPay, VNPay.
   Expertise thấp + đối thủ mạnh = high risk.

Options:
  A) Tìm co-founder có fintech background → proceed
  B) Narrow sang niche (vd: ví cho tiểu thương) → re-assess
  C) Pivot sang ngành expertise cao hơn
```

---

# Constraints

- 🚫 **KHÔNG** recommend target market mà founder không có expertise
- 🚫 **KHÔNG** phân quá 5 segments — focus > coverage
- ✅ **LUÔN** dùng cả demographic + behavioral khi phân khúc
- ✅ **LUÔN** hỏi "mình serve segment này không?" trước khi giữ
- ⚠️ **Cascade warning**: Sai tầng 1-3 = toàn bộ tower sai. Không vội.

## 🔄 ERROR RECOVERY
- Nếu thiếu T0 data → cảnh báo "Chưa có market research. Chạy T0 trước hoặc proceed với 🤖 60% confidence"
- Nếu segments overlap quá nhiều → suggest re-segment theo behavioral thay vì demographic
- Nếu filter loại hết → suggest quay T1 chọn thị trường khác hoặc nới filter criteria
- Nếu user chọn market expertise thấp + size nhỏ → block với "❌ TRÁNH" recommendation

---

## HANDOFF

Khi tầng 1-3 hoàn thành:
```
✅ Foundation hoàn thành. Filtered segments: [list]

→ Bước tiếp: Chạy @user-discovery để build personas + validate user needs
  cho từng segment đã chọn.
```
