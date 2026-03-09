# Example: TaskFlow — SaaS B2B User Discovery (Complexity: Simple)

> Ví dụ simple cho SaaS B2B PM tool. Focus: Small Team segment.

---

## INPUT từ @market-segmentation

Filtered segment: **Small Team (2-10 people, startup/agency)**

---

## TẦNG 4: PERSONAS

### Persona 1: "Minh — Startup CTO"

```
👤 Minh — "Viết code + manage team + report CEO. Burnout."

DEMOGRAPHIC: Nam, 28, CTO startup 6 người, 25tr/tháng, remote
BEHAVIORS:
  • Dùng Trello (free) + Slack + Google Sheets
  • Mỗi sáng 30 phút update status thủ công
  • Sprint review mỗi Friday qua Zoom
  • Context switch 10+ lần/ngày giữa code và manage
GOALS: "Khi report cho CEO, tôi muốn dashboard tự tổng hợp, để khỏi mất 1 tiếng mỗi tuần làm report"
PAIN: Update status thủ công = AI nên làm
WTP: $29/tháng cho team
QUOTE: "Nếu status update tự chạy, tao tiết kiệm 2 tiếng/tuần. Trello quá basic."
```

### Persona 2: "Hà — Agency PM"

```
👤 Hà — "Manage 5 clients, 8 người, mỗi project khác nhau"

DEMOGRAPHIC: Nữ, 31, PM ở agency design 8 người, 20tr/tháng
BEHAVIORS:
  • Dùng Asana (basic plan) + trùng lặp tasks giữa projects
  • Client gọi hỏi tiến độ → phải check từng người
  • Copy-paste status từ Asana sang email cho client
GOALS: "Khi client hỏi status, tôi muốn link 1 dashboard live, để khỏi soạn email update"
PAIN: Report thủ công → client update → response delay
WTP: $19/tháng
QUOTE: "Client hỏi tiến độ mà tao phải check 3 chỗ rồi soạn email. Ai làm auto thì tao mua."
```

---

## TẦNG 5: NEEDS (RICE)

| Need | Reach | Impact | Conf | Effort | RICE |
|------|-------|--------|------|--------|------|
| Auto status from activity | 2000 | 3 | 70% | 6 | 700 |
| Client-facing dashboard | 1500 | 2 | 80% | 4 | 600 |
| Smart deadline warnings | 3000 | 1 | 60% | 3 | 600 |
| AI task assignment | 1000 | 2 | 40% | 8 | 100 |

---

## TẦNG 6: UNMET NEEDS

| Need | Current sol? | Better? | Status |
|------|-------------|---------|--------|
| Auto status | ❌ No tool does this well | ✅ AI can parse Slack/Git | ⭐ UNMET |
| Client dashboard | 🟡 Asana has it (paid, ugly) | ✅ Cleaner, simpler | ⭐ UNMET |
| Smart deadlines | 🟡 Basic reminders exist | ⚠️ Incremental | 🟡 MAYBE |
| AI task assign | ❌ | ⚠️ Hard, needs lots of data | ❌ LOẠI |

```
✅ Unmet needs: Auto status + Client dashboard
→ @pmf-validator
```
