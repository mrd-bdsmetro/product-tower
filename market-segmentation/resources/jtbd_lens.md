# JTBD: Jobs-to-be-Done Lens

> Phân khúc theo VIỆC CẦN LÀM, không theo NGƯỜI LÀ AI.
> "People don't want a quarter-inch drill. They want a quarter-inch hole." — Theodore Levitt

---

## Core Concept

```
TRUYỀN THỐNG:                    JTBD:
"Nam, 35 tuổi, HCM"  →  ❌     "Cần tìm BĐS gần metro
                                  để đầu tư dài hạn,
                                  ít rủi ro"          →  ✅
```

**Lý do JTBD quan trọng:**
- 2 người cùng demographic → KHÁC job hoàn toàn
- 2 người khác demographic → CÙNG job
- Segment theo job = hiểu user thật sự cần gì

---

## Job Statement Format

```
Khi [SITUATION / TRIGGER],
tôi muốn [MOTIVATION / JOB],
để [EXPECTED OUTCOME].
```

### Ví dụ

**BĐS Metro:**
| Persona | Job Statement |
|---------|-------------|
| Nhà đầu tư mới | "Khi có 1-2 tỷ tiết kiệm, tôi muốn tìm BĐS gần metro có tiềm năng tăng giá, để passive income + bảo toàn vốn" |
| Broker | "Khi có khách hỏi BĐS quận 9, tôi muốn data giá nhanh + so sánh, để tư vấn chính xác + chốt deal nhanh" |
| Serious investor | "Khi phân tích deal, tôi muốn data lịch sử giá + khoảng cách metro, để ra quyết định dựa trên số, không cảm tính" |

**SaaS B2B:**
| Persona | Job Statement |
|---------|-------------|
| Marketing Manager | "Khi cần báo cáo ROI hàng tháng, tôi muốn dashboard tự động, để tiết kiệm 2 ngày/tháng làm report thủ công" |
| Sales Rep | "Khi follow up lead, tôi muốn biết lead đọc email chưa, để gọi đúng lúc hot" |

---

## 3 Loại Job

| Loại | Mô tả | Ví dụ |
|------|-------|-------|
| **Functional** | Công việc cụ thể cần hoàn thành | "Tìm giá BĐS gần metro" |
| **Emotional** | Cảm xúc muốn đạt được / tránh | "Yên tâm khi đầu tư" |
| **Social** | Hình ảnh xã hội | "Được coi là nhà đầu tư thông minh" |

> 💡 **Sản phẩm tốt** solve cả 3 loại. Sản phẩm trung bình chỉ solve Functional.

---

## Cách Thu Thập Jobs

### Interview Questions (dùng khi nói chuyện user)

```
TÌNH HUỐNG:
"Lần gần nhất anh/chị [TASK] là khi nào? Kể tao nghe."

HÀNH VI HIỆN TẠI:
"Anh/chị đang dùng cách gì để [TASK]?"
"Cách đó có gì khó chịu?"

JOB DISCOVERY:
"Kết quả cuối cùng anh/chị muốn là gì?"
"Nếu có đũa thần, anh/chị muốn thay đổi gì?"

PRIORITIZATION:
"Trong [tất cả pain points đã nói], cái nào ĐAU NHẤT?"
"Cái nào tốn THỜI GIAN / TIỀN nhất?"
```

### Pattern Recognition (sau 5+ interviews)

```
JOB PATTERN TABLE:
┌──────────────────────┬────────┬──────────┐
│ Job Statement        │ # Nói  │ Priority │
├──────────────────────┼────────┼──────────┤
│ "Tìm giá nhanh"     │ 4/5    │ ⭐ HIGH   │
│ "So sánh khu vực"   │ 3/5    │ 🟡 MED   │
│ "Dự đoán giá"       │ 2/5    │ 🟢 LOW   │
└──────────────────────┴────────┴──────────┘

3+ người nói cùng 1 job = REAL JOB
1 người nói = EDGE CASE (ghi nhận, chưa build)
```

---

## JTBD Segmentation (thay vì Demographic)

```
BEFORE (demographic):           AFTER (JTBD):
├── Trẻ 25-35                   ├── "Quick lookup" jobs
├── Trung niên 35-50            │   (cần data nhanh, casual)
├── Broker                      ├── "Deep analysis" jobs
└── Institutional               │   (cần data chi tiết, so sánh)
                                └── "Advisory" jobs
                                    (cần data cho tư vấn khách)
```

> 💡 1 segment JTBD có thể chứa nhiều demographic groups.
> Đó là lý do JTBD mạnh hơn: focus vào VIỆC, không vào NGƯỜI.
