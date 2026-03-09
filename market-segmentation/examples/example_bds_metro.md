# Example: BDSmetro — BĐS Metro HCM (Complexity: Medium)

> Case study thực tế chạy qua Tầng 1-3 cho sản phẩm data BĐS metro.

---

## TẦNG 1: TARGET MARKET

**Thị trường:** Dịch vụ data/analytics cho BĐS khu vực metro HCM

**Decision Matrix:**
- Expertise: **4/5** — Sale BĐS 5+ năm, hiểu thị trường HCM
- Market Size: Metro HCM 3 tuyến, ~50,000 giao dịch BĐS/năm trong bán kính 2km
- Growth: ↗ Metro đang xây, giá BĐS gần metro tăng 15-30%/năm
- Competition: Batdongsan.com, CafeF, nhưng **KHÔNG AI** có data theo khoảng cách metro
- Timing: Metro tuyến 1 sắp vận hành → demand data tăng cao

**GO/NO-GO:** ✅ GO — Expertise cao + market đang grow + gap rõ ràng

---

## TẦNG 2: SEGMENTATION

| # | Segment | Demographic | JTBD | TAM | SOM |
|---|---------|------------|------|-----|-----|
| 1 | **Newbie Investor** | 25-35, lương 15-30tr, mua BĐS lần đầu | "Khi muốn mua BĐS đầu tiên, tôi muốn biết khu nào gần metro có giá hợp lý, để không mua hớ" | 200K người | 2K users |
| 2 | **Serious Investor** | 35-50, portfolio 3+, capital 5-20 tỷ | "Khi phân tích deal, tôi muốn data lịch sử giá theo khoảng cách metro, để ra quyết định bằng số" | 30K người | 500 users |
| 3 | **Broker/Agent** | Sale BĐS chuyên nghiệp | "Khi khách hỏi BĐS gần metro, tôi muốn data nhanh + so sánh, để tư vấn chính xác + chốt deal" | 50K người | 1K users |
| 4 | **Researcher/Media** | Nhà báo, analyst, chuyên gia | "Khi viết báo cáo thị trường, tôi muốn data trực quan + charts, để bài viết có data backing" | 5K người | 100 users |

---

## TẦNG 3: FILTER + POSITIONING

### Filter

| Segment | Giữ/Loại | Lý do |
|---------|----------|-------|
| Newbie Investor | ✅ **Giữ (Primary)** | Lớn nhất, dễ serve bằng free tier, viral potential |
| Serious Investor | ✅ **Giữ (Secondary)** | Willingness to pay cao nhất, paid tier |
| Broker/Agent | ✅ **Giữ (Tertiary)** | Multiplier effect (1 broker = 10+ clients) |
| Researcher/Media | ❌ **Loại** | Quá nhỏ (5K), serve tốt = marketing tự nhiên, không cần product riêng |

### Positioning

**Primary (Newbie):**
```
Cho NHÀ ĐẦU TƯ MỚI mà cần BIẾT GIÁ BĐS GẦN METRO,
BDSMETRO là BẢN ĐỒ GIÁ BĐS THÔNG MINH
mang lại DATA GIÁ REAL-TIME THEO KHOẢNG CÁCH METRO
khác biệt bởi DỮ LIỆU CHUYÊN SÂU VỀ BĐS METRO (duy nhất trên thị trường).
```

**Secondary (Serious):**
```
Cho NHÀ ĐẦU TƯ CHUYÊN NGHIỆP mà cần DATA PHÂN TÍCH DEAL,
BDSMETRO PRO là CÔNG CỤ PHÂN TÍCH BĐS
mang lại LỊCH SỬ GIÁ + SO SÁNH KHU VỰC + DỰ BÁO
khác biệt bởi METRO-CENTRIC DATA (focus duy nhất vào BĐS gần metro).
```

---

## KẾT QUẢ

```
✅ Foundation hoàn thành.
   Filtered segments: Newbie (Primary) + Serious (Secondary) + Broker (Tertiary)
   Total SOM: ~3,500 users × $4/tháng avg = $168K/năm
   Positioning: "Dữ liệu BĐS metro duy nhất trên thị trường"

→ Bước tiếp: @user-discovery — interview 5-10 nhà đầu tư thật
```
