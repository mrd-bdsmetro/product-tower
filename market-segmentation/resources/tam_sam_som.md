# TAM-SAM-SOM: Market Sizing Framework

> Sizing thị trường — biến "lớn/nhỏ" thành CON SỐ CỤ THỂ.

---

## 3 Vòng Tròn

```
┌─────────────────────────────────────────┐
│                 TAM                      │
│    Total Addressable Market              │
│    "Nếu 100% thị phần → bao nhiêu?"     │
│                                          │
│    ┌───────────────────────────────┐     │
│    │           SAM                 │     │
│    │  Serviceable Available Market │     │
│    │  "Mình CÓ THỂ serve?"        │     │
│    │                               │     │
│    │    ┌─────────────────────┐    │     │
│    │    │       SOM           │    │     │
│    │    │  Serviceable        │    │     │
│    │    │  Obtainable Market  │    │     │
│    │    │  "Thực tế chiếm?"   │    │     │
│    │    └─────────────────────┘    │     │
│    └───────────────────────────────┘     │
└─────────────────────────────────────────┘
```

---

## Cách Tính

### Cách 1: Top-Down (từ trên xuống)

Dùng khi có industry report:

```
TAM = [Tổng revenue ngành] × [% liên quan đến product]
SAM = TAM × [% filter theo geo/model/channel]
SOM = SAM × [realistic market share % year 1-3]
```

**Ví dụ BĐS Metro HCM:**
```
TAM = Thị trường BĐS khu vực metro HCM ≈ 50,000 giao dịch/năm × 5 tỷ VND avg
    = 250,000 tỷ VND giao dịch
TAM (dịch vụ data) = 250,000 tỷ × 0.1% (tỷ lệ chi cho data/tools)
    = 250 tỷ VND/năm

SAM = TAM × 60% (chỉ HCM, chỉ BĐS gần metro)
    = 150 tỷ VND/năm

SOM = SAM × 2% (market share năm 1, mới vào)
    = 3 tỷ VND/năm ≈ $120K/năm
```

### Cách 2: Bottom-Up (từ dưới lên)

Dùng khi CÓ dữ liệu thực:

```
SOM = [Số khách hàng thực tế reach được] × [ARPU] × [Conversion rate]
SAM = SOM ÷ [Market share ước tính]
TAM = SAM ÷ [% filter]
```

**Ví dụ SaaS B2B:**
```
SOM = 500 leads/tháng × $49/tháng × 3% conv = $735/tháng = $8.8K/năm
SAM = $8.8K ÷ 1% = $880K/năm
TAM = $880K ÷ 30% = $2.9M/năm
```

### Cách 3: Value Theory (giá trị tạo ra)

Dùng khi không có data:

```
TAM = [Số người gặp vấn đề] × [Giá trị giải pháp mang lại]
```

---

## Quick Sizing Table

| Metric | Câu hỏi | Data source |
|--------|---------|-------------|
| **TAM** | "Tổng cộng bao nhiêu người/công ty CÓ vấn đề này?" | Industry reports, Google Trends, census |
| **SAM** | "Trong đó, mình REACH được bao nhiêu?" | Geo filter, channel filter, model filter |
| **SOM** | "Thực tế năm 1, chiếm bao nhiêu?" | Competitor benchmarks, own traction |

---

## Red Flags

| 🚩 Flag | Ý nghĩa |
|---------|---------|
| SOM < $50K/năm | Thị trường quá nhỏ cho solo founder |
| TAM-to-SOM ratio > 1000x | Giả định phi thực tế |
| Không tìm được TAM data | Có thể thị trường chưa tồn tại |
| SOM tính dựa trên "10% market" | SOM thực tế thường 1-3% năm 1 |

---

## Template

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 TAM-SAM-SOM — [Segment Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Phương pháp tính: [Top-Down / Bottom-Up / Value Theory]

TAM: _____________ (source: ________)
SAM: _____________ (filter: ________)
SOM: _____________ (share: ____%, timeframe: ____)

Assumptions:
- _______________
- _______________

Confidence: [Low / Medium / High]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```
