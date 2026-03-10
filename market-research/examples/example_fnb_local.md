# Example: FoodHub — F&B Local Marketplace (T0)

## Input
```
Lĩnh vực: F&B Marketplace (2-sided)
Thị trường: Quận 1-3, HCMC
Vốn: 100 triệu VND
Ý tưởng: Marketplace kết nối quán ăn nhỏ với VP gần
Mode: Express → Pro
```

## Loop 1 Output (Express — 🤖 60%)

### t1_target_market.md (excerpt)
```markdown
# Target Market: Local F&B Delivery — HCMC Q1-3

- 🤖 Thị trường delivery HCMC: ~$1.5B (2025)
- 🤖 Office lunch segment (Q1-3): ~$50M
- 🤖 Existing players: GrabFood, ShopeeFood, Baemin (đã exit)
- 🤖 Gap: quán nhỏ không lên app lớn (commission 25-30%)
```

## Loop 2 Delta (Counter-research)

```markdown
KILLED:
  - "Gap: quán nhỏ không lên app" → Thực tế 80% quán đã trên GrabFood
  - "Commission 25-30% = pain" → Quán đã quen, coi như marketing cost
  
CONFIRMED:
  - Office lunch = real demand segment
  - Q1-3 density cao, delivery radius ngắn

NEW:
  - 📊 Baemin exit VN (2023) → market consolidation, khó cho newbie
  - Real gap: không phải delivery, mà PRE-ORDER (đặt trước 11h, nhận 12h)
  - Competitor analysis: 3 startup VN đã thử, 2 đã chết

PMF IMPACT:
  - Before: raw 8, adjusted 6 (overly optimistic)
  - After: raw 5, adjusted 4.5 → FAIL ❌
  - Pivot signal: change from "marketplace" to "pre-order for office"
```

## Loop 3 Delta (Field + Interviews)

```markdown
KILLED:
  - "Pre-order model" → 2/5 VP HR nói "nhân viên tự lo cơm, công ty không quản"
  
CONFIRMED:
  - Office workers Q1 muốn đa dạng hơn canteen
  - Quán nhỏ muốn thêm kênh bán nhưng không muốn thêm app

NEW:
  - 👤 "Tụi tao hay đặt theo nhóm 5-10 người, ai gom order thì mệt" — NV VP
  - 👤 Actual pain = GROUP ORDER coordination, không phải delivery
  - 👤 WTP: $0 (không ai trả phí), revenue model phải từ quán
  - Field: 15/20 quán quanh VP dùng Zalo nhận order → opportunity

PMF IMPACT:
  - Before: raw 5, adjusted 4.5 (marketplace model)
  - After: raw 6, adjusted 6 (group order pivot) → STILL FAIL ❌
  - Decision: pivot thêm hoặc kill project
  
→ ⚠️ PMF 6/10 = FAIL. Cần thêm Loop 3b hoặc pivot hoàn toàn.
```

## Key Lesson

> F&B marketplace là **graveyard of startups**. 3-Loop Protocol cứu founder khỏi đổ 100 triệu vào ý tưởng raw 8 nhưng adjusted chỉ 4.5.
> Loop 2 bắn hạ 2 giả định sai. Loop 3 phát hiện real pain khác hoàn toàn.
