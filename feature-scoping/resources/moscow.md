# MoSCoW Prioritization — Feature Priority Framework

> Must / Should / Could / Won't — quyết định build gì TRƯỚC.

---

## Framework

| Priority | Ý nghĩa | % features | Ví dụ |
|----------|---------|-----------|-------|
| **M**ust Have | Không có = sản phẩm KHÔNG CHẠY ĐƯỢC | 60% | Login, Search, Core feature |
| **S**hould Have | Quan trọng nhưng có workaround | 20% | Filters, Export |
| **C**ould Have | Nice to have, nếu có thời gian | 15% | Dark mode, Animations |
| **W**on't Have | Cần nhưng KHÔNG build sprint này | 5% | AI predictions, Mobile app |

---

## Template

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📋 MoSCoW — [Product] — Sprint [#]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MUST HAVE (sản phẩm chết nếu thiếu):
  □ F1: _______________  [___ person-days]
  □ F2: _______________  [___ person-days]
  □ F3: _______________  [___ person-days]
  Subtotal: ___ person-days

SHOULD HAVE (quan trọng, workaround OK):
  □ F4: _______________  [___ person-days]
  □ F5: _______________  [___ person-days]
  Subtotal: ___ person-days

COULD HAVE (nice, nếu có thời gian):
  □ F6: _______________  [___ person-days]
  □ F7: _______________  [___ person-days]
  Subtotal: ___ person-days

WON'T HAVE (this sprint — move to next):
  ○ F8: _______________
  ○ F9: _______________

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
TOTAL MUST:    ___ days (target: ≤ 70% capacity)
BUFFER:        ___ days (30% cho bugs + unexpected)
SPRINT LENGTH: ___ weeks
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Decision Rules

```
"Feature này MUST hay SHOULD?"

Hỏi: "Nếu BỎ feature này, user còn dùng sản phẩm không?"
  YES → SHOULD (hoặc thấp hơn)
  NO  → MUST

"Feature này SHOULD hay COULD?"

Hỏi: "User có THAN PHIỀN nếu thiếu feature này không?"
  YES → SHOULD
  NO  → COULD
```

---

## Tips

1. **MUST ≤ 60% capacity** — chừa buffer cho bugs
2. **WON'T ≠ Never** — chỉ là "not now"
3. **Debate là tốt** — nếu team không đồng ý M vs S, discuss = tìm ra truth
4. **Re-prioritize mỗi sprint** — context thay đổi, priority thay đổi
