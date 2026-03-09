# Example: LocalBite — PMF Validation (Complex)

## Context
- Product: Hidden gem F&B discovery app
- Stage: MVP, 15 users (< 30!)
- Method: Metrics Dashboard (chưa đủ user cho survey)

## Metrics Dashboard

```
ENGAGEMENT                   Target    Actual   Status
DAU/MAU ratio               > 20%     12%      ❌
Avg sessions/week           > 3       1.8      ❌

RETENTION                    Target    Actual   Status
Day 7 retention             > 25%     35%      ✅
Day 30 retention            > 10%     18%      ✅

GROWTH                       Target    Actual   Status
Organic/WOM growth %        > 30%     60%      ✅
Referral rate               > 10%     25%      ✅

SCORE: 4/6 → 🟡 Mixed signals
```

## Analysis
- **Retention + Referral = STRONG** → people who try it LOVE it and refer
- **Engagement = WEAK** → they don't come back OFTEN enough
- **Insight**: App solves a "cuối tuần" job → dùng 1-2x/tuần, không daily

## Decision
```
PMF Signal: 🟡 PARTIAL
→ App có value (retention + referral strong)
→ Nhưng engagement model sai (daily metric cho weekly product)

ACTION:
1. Adjust metrics: DAU/WAU thay vì DAU/MAU (weekly product)
2. Grow đến 30+ users → chạy Sean Ellis Test
3. Nếu DAU/WAU > 40% → pivot metric thành công

⚠️ KHÔNG SCALE YET — chờ Sean Ellis confirm
```

## Bài học
- Marketplace cần đủ critical mass trước khi survey
- Weekly products = dùng weekly metrics, không daily
- Strong referral = proxy tốt cho PMF (users tự recommend)
