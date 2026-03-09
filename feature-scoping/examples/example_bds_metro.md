# Example: BDSmetro — Feature Scoping (Medium)

## Input từ @pmf-validator
- PMF Score: 43% ✅
- Unmet needs: Giá metro, So sánh khu vực, Lịch sử giá
- HXC: Serious investors (35-50, portfolio 3+)

---

## TẦNG 8: FEATURE SET (MoSCoW)

| Priority | Feature | Map to Need | Effort |
|----------|---------|------------|--------|
| **MUST** | Metro Map Search | Giá metro | 5 days |
| **MUST** | Price Display | Giá metro | 3 days |
| **MUST** | Distance Filter | Giá metro | 2 days |
| **SHOULD** | Area Compare | So sánh | 4 days |
| **SHOULD** | Price History (6mo) | Lịch sử | 3 days |
| **COULD** | Export PDF | So sánh | 2 days |
| **COULD** | Price Alert | — | 3 days |
| **WON'T** | AI Price Prediction | — | 15 days |
| **WON'T** | Mobile App | — | 20 days |

**MVP Scope:** 3 MUST + 1 SHOULD = 14 days (2 tuần)

---

## TẦNG 9: USER STORIES (MVP)

### Story 1 (MUST — Core)
```
Là NHÀ ĐẦU TƯ MỚI,
tôi muốn TÌM BĐS THEO KHOẢNG CÁCH TỪ TRẠM METRO,
để BIẾT GIÁ TRUNG BÌNH TỪNG KHU VỰC.

AC: GIVEN tôi ở trang chủ,
    WHEN chọn "Metro Bến Thành" + bán kính 1km,
    THEN thấy map + danh sách BĐS + giá TB.
INVEST: 6/6 ✅  |  Size: M (3 days)
```

### Story 2 (MUST — Filter)
```
Là NHÀ ĐẦU TƯ,
tôi muốn LỌC THEO GIÁ VÀ DIỆN TÍCH,
để CHỈ XEM BĐS TRONG NGÂN SÁCH.

AC: GIVEN kết quả search hiển thị,
    WHEN chọn range giá 2-3 tỷ + diện tích 50-80m²,
    THEN danh sách filter realtime.
INVEST: 6/6 ✅  |  Size: S (1 day)
```

### Story 3 (MUST — Detail)
```
Là NHÀ ĐẦU TƯ,
tôi muốn XEM CHI TIẾT 1 BĐS,
để ĐÁNH GIÁ DEAL.

AC: GIVEN danh sách kết quả,
    WHEN click vào 1 BĐS,
    THEN thấy: giá, diện tích, khoảng cách metro (m), ảnh, source.
INVEST: 6/6 ✅  |  Size: M (2 days)
```

### Story 4 (SHOULD — Compare)
```
Là NHÀ ĐẦU TƯ CHUYÊN NGHIỆP,
tôi muốn SO SÁNH 2 KHU VỰC,
để TÌM KHU VỰC UNDERVALUED.

AC: GIVEN tôi đã chọn 2 trạm metro,
    WHEN click "So sánh",
    THEN thấy bảng side-by-side: giá TB, số lượng, trend.
INVEST: 6/6 ✅  |  Size: L (4 days)
```

---

## Story Map

```
DISCOVER     →    EVALUATE    →    DECIDE
    │                 │              │
  Search            Compare       Detail View
  Filter            Charts        Contact
═══════════════ MVP LINE ════════════════
  AI suggest       Save list     Price Alert
  Voice search     Share         Export PDF
```

```
✅ MVP: 4 stories | 14 days | Ship in 2 weeks
→ @ui-ux-pro-max cho design
```
