# Example: LocalBite — Feature Scoping (Complex)

## Input
- PMF: 🟡 Partial (metrics only, chưa survey)
- 2-sided: Demand (Foodie) + Supply (Quán nhỏ)
- ⚠️ Risk: expertise thấp, chưa confirm PMF

---

## 2-Sided Feature Set

### Supply Side (build TRƯỚC — giải chicken-egg)

| Priority | Feature | Why |
|----------|---------|-----|
| **MUST** | Simple listing form | Quán add bằng 3 bước |
| **MUST** | Photo upload | Ảnh thật = trust |
| **COULD** | Basic analytics | "Bao nhiêu người xem" |

### Demand Side

| Priority | Feature | Why |
|----------|---------|-----|
| **MUST** | Map view (hidden gems) | Core value |
| **MUST** | Review + rating | UGC content |
| **SHOULD** | "Near me" filter | Location-based |
| **COULD** | Save favorites | Return visits |
| **WON'T** | Ordering/delivery | Grab territory |

---

## MVP Strategy (2-sided)

```
PHASE 1 (2 weeks): Seed supply manually
  → Tự add 50 quán → không cần listing form
  → Build demand features only (map + review)
  
PHASE 2 (2 weeks): Open supply
  → Add listing form cho quán tự đăng ký
  → Test với 10 quán real
```

> **Key insight**: Marketplace MVP = SEED one side manually,
> build product for the OTHER side.

---

## User Stories (MVP Phase 1)

```
1. Là FOODIE EXPLORER,
   tôi muốn XEM BẢN ĐỒ QUÁN ẨN GẦN ĐÂY,
   để TÌM QUÁN MỚI CUỐI TUẦN.

2. Là FOODIE,
   tôi muốn ĐỌC REVIEW TỪ FOODIE KHÁC,
   để BIẾT QUÁN CÓ NGON KHÔNG TRƯỚC KHI ĐI.

3. Là FOODIE,
   tôi muốn VIẾT REVIEW + POST ẢNH,
   để SHARE TRẢI NGHIỆM VỚI COMMUNITY.
```

```
✅ Phase 1 MVP: 3 demand stories | 10 days
   Supply: seed 50 quán thủ công
   Total: 2 weeks to testable MVP
```
