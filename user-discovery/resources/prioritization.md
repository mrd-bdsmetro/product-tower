# Prioritization Frameworks — RICE, Kano, Impact×Effort

> Có 50 needs? Chọn 5 build trước. Đây là cách chọn.

---

## 1. RICE Scoring (Recommended)

```
RICE Score = (Reach × Impact × Confidence) ÷ Effort
```

| Factor | Đo gì | Scale | Ví dụ |
|--------|-------|-------|-------|
| **Reach** | Bao nhiêu user/quarter | Số cụ thể | 5,000 users/quý |
| **Impact** | Mức ảnh hưởng | 3=massive, 2=high, 1=med, 0.5=low, 0.25=minimal | Solve pain chính = 3 |
| **Confidence** | Chắc chắn bao nhiêu | 100%=data, 80%=strong gut, 50%=guess | Có interview data = 80% |
| **Effort** | Bao lâu để build | Person-weeks | 2 tuần 1 người = 2 |

### Ví dụ RICE Table

```
┌──────────────────────┬───────┬────────┬──────┬────────┬───────┐
│ Need                 │ Reach │ Impact │ Conf │ Effort │ RICE  │
├──────────────────────┼───────┼────────┼──────┼────────┼───────┤
│ Bản đồ giá real-time │ 5000  │ 3      │ 80%  │ 4      │ 3000  │
│ So sánh khu vực      │ 3000  │ 2      │ 80%  │ 2      │ 2400  │
│ Alert giá giảm       │ 2000  │ 1      │ 50%  │ 3      │  333  │
│ Dự đoán giá AI       │ 1000  │ 2      │ 30%  │ 8      │   75  │
└──────────────────────┴───────┴────────┴──────┴────────┴───────┘

→ Build order: Bản đồ giá → So sánh khu vực → Alert → Dự đoán AI
```

---

## 2. Kano Model — Phân loại Needs

```
SATISFACTION ↑
  ↑                    ╱ EXCITEMENT
  │                   ╱  (wow, delight)
  │                  ╱
  │         ╱─────────── PERFORMANCE
  │        ╱              (more = better)
  │       ╱
  │  ────────────────── BASIC
  │  (must have,       (expect by default)
  │   no delight)
  │
  └────────────────────────→ FULFILLMENT →
```

| Loại | Không có? | Có? | Ví dụ |
|------|----------|-----|-------|
| **Basic** | 😤 User BỎ ĐI | 😐 Bình thường | Login, search, loading speed |
| **Performance** | 😟 Kém | 😀 Hài lòng (linear) | Response time, data accuracy |
| **Excitement** | 😐 Không biết | 🤩 WOW delight | AI predictions, smart alerts |

### Kano Survey Format

Cho mỗi feature, hỏi 2 câu:

```
FUNCTIONAL:  "Nếu CÓ feature X, bạn cảm thấy thế nào?"
             1=Thích  2=OK  3=Không quan tâm  4=Chấp nhận  5=Không thích

DYSFUNCTIONAL: "Nếu KHÔNG CÓ feature X, bạn cảm thấy thế nào?"
             1=Thích  2=OK  3=Không quan tâm  4=Chấp nhận  5=Không thích
```

---

## 3. Impact × Effort Matrix (Quick)

```
              Effort THẤP          Effort CAO
             ┌──────────────────┬──────────────────┐
Impact       │  ⭐ QUICK WIN     │  🟡 MAJOR PROJECT │
CAO          │  LÀM NGAY!       │  Lên plan kỹ      │
             ├──────────────────┼──────────────────┤
Impact       │  🟢 FILL-IN       │  ❌ MONEY PIT      │
THẤP         │  Khi rảnh         │  TRÁNH             │
             └──────────────────┴──────────────────┘
```

---

## Cách chọn Framework

| Tình huống | Framework | Tại sao |
|-----------|-----------|---------|
| Có data, cần rank chính xác | **RICE** | Objective, data-driven |
| Phân loại basic vs wow | **Kano** | Hiểu loại giá trị |
| Quick decision, ít data | **Impact×Effort** | Simple, fast |
| Có nhiều stakeholders | **RICE + Kano** | Combine cho explain rõ |

> 💡 **Pro tip**: Dùng RICE làm primary, Kano làm sanity check.
> RICE nói "build this first", Kano nói "đây là basic hay excitement?"
