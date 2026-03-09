# Example: BDSmetro — User Discovery (Complexity: Medium)

> Case study: chạy Tầng 4-6 cho BDSmetro data tool.

---

## INPUT từ @market-segmentation

Filtered segments:
1. **Newbie Investor** (Primary) — mua BĐS lần đầu
2. **Serious Investor** (Secondary) — portfolio 3+

---

## TẦNG 4: PERSONAS

### Persona 1: "Anh Tuấn — Investor Mới"

```
👤 Anh Tuấn — "Tham muốn mua nhưng sợ mua hớ"

DEMOGRAPHIC: Nam, 32, IT Manager, 35tr/tháng, Q.2 HCM
BEHAVIORS:
  • Đọc Batdongsan.com, CafeF, Facebook groups BĐS hàng ngày
  • Screenshot giá rao → so sánh thủ công trên Excel
  • Hỏi bạn bè đã mua BĐS gần metro
  • Đi xem nhà 1-2x/tháng cuối tuần
ASPIRATIONS: Sở hữu BĐS đầu tiên gần metro để tăng giá
GOALS: "Khi có 1.5 tỷ, tôi muốn tìm BĐS gần metro Q.9 giá tốt, để mua trước khi metro chạy"
PAIN: Không biết giá nào hợp lý — mỗi agent nói 1 giá khác nhau
WTP: 99K/tháng
QUOTE: "Tao thấy giá rao 2.5 tỷ nhưng không biết giá thật bao nhiêu. Hổng ai cho data."
```

### Persona 2: "Chị Lan — Pro Investor"

```
👤 Chị Lan — "Data player, mua bằng số không bằng cảm xúc"

DEMOGRAPHIC: Nữ, 42, Giám đốc tài chính, 80tr/tháng, Q.7 HCM
BEHAVIORS:
  • Dùng PropzyData, Rich Nguyen Analytics
  • Có Excel tracking 50+ BĐS theo khoảng cách metro
  • Network với 3 broker chuyên metro, họp weekly
  • Deal 2-3 BĐS/năm, portfolio 8 căn
ASPIRATIONS: Tối ưu portfolio, cash flow stable
GOALS: "Khi phân tích deal mới, tôi muốn overlay data giá + khoảng cách metro + quy hoạch, để tìm undervalued"
PAIN: Data phân tán — phải tự gom từ 5 nguồn, mất 2 ngày/deal
WTP: 499K/tháng
QUOTE: "Ai cho tao data giá theo khoảng cách metro, tao trả tiền ngay. Hiện tại phải tự crawl."
```

---

## TẦNG 5: USER NEEDS (Prioritized)

### RICE Scoring

| Need | Reach | Impact | Conf | Effort | RICE |
|------|-------|--------|------|--------|------|
| Xem giá BĐS theo khoảng cách metro | 5000 | 3 | 80% | 4 | 3000 |
| So sánh giá giữa các khu vực | 3000 | 2 | 80% | 3 | 1600 |
| Lịch sử biến động giá | 2000 | 2 | 70% | 4 | 700 |
| Alert khi giá giảm | 2000 | 1 | 50% | 3 | 333 |
| Dự đoán giá AI | 1000 | 2 | 30% | 8 | 75 |

**Build order:** Xem giá → So sánh → Lịch sử → Alert → AI

---

## TẦNG 6: UNMET NEEDS

| Need | Ai solve? | Mình làm được? | Tốt hơn? | Status |
|------|-----------|---------------|----------|--------|
| Giá theo khoảng cách metro | ❌ Không ai | ✅ Crawl được | ✅ Unique data | ⭐ UNMET |
| So sánh giá khu vực | 🟡 Batdongsan (generic) | ✅ | ✅ Metro-focused | ⭐ UNMET |
| Lịch sử giá | 🟡 CafeF (stocks only) | ✅ | ✅ BĐS-specific | ⭐ UNMET |
| Alert giá giảm | ❌ Không ai | ✅ | ✅ | 🟡 MAYBE |
| Dự đoán AI | 🟡 Vài tool nước ngoài | ⚠️ Cần ML team | ❌ | ❌ LOẠI |

**Unmet needs found: 3** (Giá metro, So sánh, Lịch sử)

```
✅ Discovery hoàn thành.
   Personas: Anh Tuấn (Newbie), Chị Lan (Pro)
   Top Unmet Needs: Data giá theo metro (RICE 3000)
   Total WTP: 99-499K/tháng → validates pricing
→ Bước tiếp: @pmf-validator
```
