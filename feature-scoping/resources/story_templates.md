# User Story Templates — INVEST + Acceptance Criteria

---

## Standard Format

```
Là [PERSONA],
tôi muốn [HÀNH ĐỘNG],
để [MỤC ĐÍCH / GIÁ TRỊ].

Acceptance Criteria:
  GIVEN [bối cảnh],
  WHEN  [hành động],
  THEN  [kết quả mong đợi].
```

---

## Ví dụ theo Category

### Core Feature Story
```
Là NHÀ ĐẦU TƯ MỚI,
tôi muốn TÌM KIẾM BĐS THEO KHOẢNG CÁCH TỪ TRẠM METRO,
để BIẾT ĐƯỢC GIÁ BĐS TRONG BÁN KÍNH 500M-2KM.

AC1: GIVEN tôi ở trang chủ,
     WHEN nhập "Metro Bến Thành" và chọn bán kính 1km,
     THEN hiển thị danh sách BĐS trong 1km + giá trung bình.

AC2: GIVEN kết quả hiển thị,
     WHEN click vào 1 BĐS,
     THEN thấy chi tiết: giá, diện tích, khoảng cách chính xác.
```

### Supporting Feature Story
```
Là NHÀ ĐẦU TƯ CHUYÊN NGHIỆP,
tôi muốn SO SÁNH GIÁ GIỮA 2 KHU VỰC,
để TÌM KHU VỰC UNDERVALUED.

AC1: GIVEN tôi đã chọn 2 khu vực,
     WHEN click "So sánh",
     THEN thấy bảng so sánh side-by-side (giá TB, trend, supply).
```

### Infrastructure Story
```
Là USER,
tôi muốn ĐĂNG NHẬP BẰNG GOOGLE,
để KHÔNG CẦN NHỚ MẬT KHẨU.

AC1: GIVEN tôi ở màn login,
     WHEN click "Login with Google",
     THEN redirect sang Google OAuth → quay lại app đã login.
```

---

## INVEST Checklist Template

```
Story: "Là ___, tôi muốn ___, để ___"

[I] Independent?    □ Có thể build riêng, không block story khác
[N] Negotiable?     □ Implementation flexible, không fix cứng
[V] Valuable?       □ Mang giá trị rõ ràng cho user
[E] Estimable?      □ Dev ước lượng được (≤ X ngày)
[S] Small?          □ Build trong ≤ 1 sprint (1 tuần)
[T] Testable?       □ Có acceptance criteria rõ ràng

Score: ___/6 (target: 6/6)
```

---

## Story Sizing (T-shirt)

| Size | Effort | Solo founder | Ví dụ |
|------|--------|-------------|-------|
| **XS** | < 0.5 ngày | ✅ Easy | Fix text, add button |
| **S** | 0.5-1 ngày | ✅ | Simple form, basic filter |
| **M** | 2-3 ngày | ✅ | Search with params, chart |
| **L** | 4-5 ngày | ⚠️ Tách ra | Compare feature, dashboard |
| **XL** | > 5 ngày | ❌ PHẢI tách | AI integration, real-time |

> **Rule**: Nếu > L, tách thành 2+ stories nhỏ hơn.
