---
name: feature-scoping
description: |
  Prioritize features (MoSCoW), scope MVP, và generate User Stories 
  với INVEST criteria. Product Tower tầng 8-9 (Product). Kích hoạt khi 
  user nói "feature", "scope", "MVP", "user story", "feature list",
  "build cái gì trước", hoặc cần quyết định BUILD GÌ TRƯỚC.
triggers:
  - "feature"
  - "feature list"
  - "feature scope"
  - "MVP"
  - "mvp scope"
  - "user story"
  - "user stories"
  - "build gì trước"
  - "MoSCoW"
---

# Goal

Quyết định build FEATURES GÌ và THEO THỨ TỰ NÀO. Đây là bước cuối 
Product Tower trước khi chuyển sang Design/Build. Map user needs → features 
→ MoSCoW priority → MVP scope → user stories with acceptance criteria.

> **Ai quyết**: Product Manager (mũ PM)
> **Input**: T5 (user needs) + T6 (unmet needs) + T7 (PMF validated)
> **Output**: Feature list (MoSCoW) + MVP scope + User stories

---

# Instructions

## GATE CHECK

```
🛑 PRE-SCOPING GATE CHECK

  □ T7 PMF(adjusted) ≥ 7?     → [PASS/FAIL]
  □ data/t5_user_needs.md      → [EXISTS/MISSING]
  □ data/t6_unmet_needs.md     → [EXISTS/MISSING]

IF PMF < 7 → BLOCKED. "PMF chưa pass. Quay lại @pmf-validator."
IF T5/T6 missing → BLOCKED. "Chưa có needs data. Chạy @user-discovery."
```

---

## TẦNG 8: FEATURE LIST (MoSCoW Prioritization)

### Bước 1: Map Needs → Features

Cho MỖI need trong T5 + T6:

```
Need: [tên need]
  → Feature giải quyết: [tên feature]
  → Unmet? [🔴 UNMET / 🟡 PARTIAL / ✅ MET]
  → Effort: [Low / Medium / High]
```

### Bước 2: MoSCoW Prioritization

| Priority | Rules | Khi nào dùng |
|----------|-------|-------------|
| **MUST** | Không có = product vô dụng. Trực tiếp solve unmet need #1-#2 | Core MVP |
| **SHOULD** | Quan trọng nhưng có workaround. Solve need #3-#4 | Phase 2 |
| **COULD** | Nice-to-have. Enhancement, polish | Phase 3+ |
| **WON'T** | Tốn effort, low impact, hoặc ngoài scope | Kill / defer |

### Scoring Matrix (Decision Aid)

```
              Impact CAO            Impact THẤP
             ┌──────────────────┬──────────────────┐
Effort       │  ⭐ MUST           │  🟡 SHOULD        │
THẤP         │  Build first!     │  Quick win        │
             ├──────────────────┼──────────────────┤
Effort       │  ⚠️ SHOULD/MUST   │  ❌ WON'T         │
CAO          │  Plan carefully   │  Don't build      │
             └──────────────────┴──────────────────┘
```

### Output Format — T8

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📋 FEATURE LIST — [Project]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

| Feature | Addresses Need | Unmet? | MoSCoW | Effort |
|---------|---------------|--------|--------|--------|
| F1: ___ | #___ | 🔴/🟡/✅ | MUST | L/M/H |
| F2: ___ | #___ | 🔴/🟡/✅ | MUST | L/M/H |
| ...

MUST count: ___  |  Total features: ___
MVP = MUST features only
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## TẦNG 9: MVP SCOPE + USER STORIES

### Bước 1: Define MVP

```
MVP = MUST features ONLY (2-4 features max)

Rules:
- Solo founder → MAX 3 MUST features
- Team 2-5 → MAX 5 MUST features
- Nếu MUST > 5 → re-prioritize, demote weakest MUST → SHOULD
```

### Bước 2: Write User Stories (INVEST Criteria)

Mỗi MUST feature → 1 user story theo format:

```
US-[N]: [Feature Name]

AS A [persona từ T4]
I WANT TO [action]
SO THAT [benefit/outcome]

Acceptance Criteria:
- [ ] [specific, testable criterion]
- [ ] [specific, testable criterion]
- [ ] [specific, testable criterion]
```

**INVEST Checklist** (mỗi story phải pass):

| Criteria | Check |
|----------|-------|
| **I**ndependent | Story không phụ thuộc story khác? |
| **N**egotiable | Có thể negotiate scope? |
| **V**aluable | Deliver value cho user? |
| **E**stimable | Ước lượng effort được? |
| **S**mall | Ship trong 1-2 sprint (1-2 tuần)? |
| **T**estable | Có acceptance criteria rõ ràng? |

### Bước 3: MVP Definition Card

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🎯 MVP DEFINITION — [Project] v1.0
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Tagline: "[1 câu mô tả giá trị]"
Target:  [persona chính]
Scope:   [N] MUST features

┌─────────────┬──────────────────────────┐
│ ✅ In-Scope  │ ❌ Out-of-Scope          │
├─────────────┼──────────────────────────┤
│ F1: ___     │ F4: ___ (Phase 2)       │
│ F2: ___     │ F5: ___ (Phase 2)       │
│ F3: ___     │ F6: ___ (WON'T)         │
└─────────────┴──────────────────────────┘

Success Metrics (3 tháng đầu):
| Metric           | Target          |
|------------------|-----------------|
| [metric 1]       | [number]        |
| [metric 2]       | [number]        |
| [metric 3]       | [number]        |

Tech Stack:
| Layer     | Choice       | Why           |
|-----------|-------------|---------------|
| Frontend  | ___         | ___           |
| Backend   | ___         | ___           |
| Data      | ___         | ___           |
| Hosting   | ___         | ___           |

Timeline:
| Week    | Milestone              |
|---------|------------------------|
| W1-2    | ___                    |
| W3-4    | ___                    |
| ...     | ...                    |
| W[N]    | 🚀 LAUNCH             |
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## ANTI-PATTERNS

### ❌ Feature Creep (Cái Gì Cũng Build)
```
"Thêm F4 luôn đi, có F5 nữa, rồi F6..."
→ Solo founder + 10 features = ship 0 features
→ BRAKE: "Anh đang có [N] MUST. Solo founder MAX 3. Cái nào demote?"
```

### ❌ Solution-First (Build Trước Khi Hiểu Need)
```
"Tao muốn build AI chatbot cho app"
→ "AI chatbot solve need nào trong T5? Nếu không solve unmet need → WON'T."
```

### ❌ Copy-Cat (Clone Đối Thủ)
```
"Làm giống PropertyGuru"
→ "Differentiation ở đâu? T6 unmet needs = cái đối thủ CHƯA solve."
```

---

## KHỞI ĐỘNG (INITIALIZATION)

```
📋 Feature Scoping — Product Tower Tầng 8-9

Anh đang scope features cho project nào? Cho tao biết:
1. Tên project
2. PMF score đã pass chưa? (adjusted ≥ 7?)
3. Có T5 (user needs) + T6 (unmet needs) chưa?

Tao sẽ map needs → features → MoSCoW → MVP scope → user stories.

⚠️ Solo founder rule: MAX 3 MUST features. Scope nhỏ = ship nhanh = learn nhanh.
```

---

# Examples

## Ví dụ 1: BĐS Metro — Solo founder, 2 unmet needs

**Input:** "Scope features cho BDSmetro. PMF 7.5/10 PASS. Unmet needs: giá thật + so sánh khu vực"

**Output:**
```
📋 FEATURE LIST — BDSmetro
━━━━━━━━━━━━━━━━━━━━━━━━━━

| Feature | Need | Unmet? | MoSCoW | Effort |
|---------|------|--------|--------|--------|
| F1: Real Price Index | #1 Giá thật | 🔴 UNMET | ⭐ MUST | Medium |
| F2: Metro Area Compare | #2 So sánh | 🔴 UNMET | ⭐ MUST | Medium |
| F3: Nearby Amenities Map | #3 Tiện ích | 🟡 PARTIAL | SHOULD | Low |
| F4: AI Price Prediction | #1 Giá thật | 🟡 PARTIAL | COULD | High |
| F5: Agent Marketplace | — | ✅ MET | ❌ WON'T | High |

MUST: 2 | Solo founder MAX 3 → ✅ OK

━━━━━━━━━━━━━━━━━━━━━━━━━━
🎯 MVP DEFINITION — BDSmetro v1.0
Tagline: "Giá BĐS thật khu metro HCM"
Target:  "So sánh kỹ Tùng" (first-time buyer)
Scope:   2 MUST features

US-1: Real Price Index
AS A first-time buyer
I WANT TO see verified real transaction prices by metro station
SO THAT I know the true market price, not inflated listings

Acceptance Criteria:
- [ ] Display price/m² cho 5+ khu metro Line 1
- [ ] Data source visible (land registry, verified transactions)
- [ ] Update frequency ≤ 1 tháng
```

## Ví dụ 2: Feature Creep — Solo founder muốn quá nhiều

**Input:** "Tao cần 6 features MUST cho ví điện tử"

**Output:**
```
🛑 FEATURE CREEP DETECTED

Solo founder + 6 MUST features = ship 0 features.
Rule: Solo founder MAX 3 MUST.

Current 6 MUST:
  F1: QR Payment        Impact: CAO  Effort: Medium  → KEEP MUST
  F2: Cash Dashboard     Impact: CAO  Effort: Low     → KEEP MUST
  F3: Lending Referral   Impact: CAO  Effort: High    → KEEP MUST
  F4: Bill Payment       Impact: THẤP Effort: Medium  → DEMOTE → SHOULD
  F5: Loyalty Program    Impact: THẤP Effort: High    → DEMOTE → WON'T
  F6: Multi-wallet       Impact: THẤP Effort: High    → DEMOTE → WON'T

→ MVP = F1 + F2 + F3 (3 MUST). F4-F6 = Phase 2/3.
  "Ship 3 features rồi iterate. Đừng build 6 cái rồi ship 0."
```

---

# Constraints

- 🚫 **KHÔNG** scope features khi PMF(adjusted) < 7
- 🚫 **KHÔNG** cho MUST > 3 features (solo founder) hoặc > 5 (team)
- 🚫 **KHÔNG** add feature mà không map được tới T5/T6 need
- ✅ **LUÔN** mỗi feature phải trỏ tới ≥1 need number
- ✅ **LUÔN** user story phải pass INVEST checklist
- ✅ **LUÔN** ghi rõ In-Scope vs Out-of-Scope
- ⚠️ Feature creep = dopamine trap cho ADHD founder → BRAKE

## 🔄 ERROR RECOVERY
- Nếu PMF < 7 → BLOCK hoàn toàn, redirect sang @pmf-validator
- Nếu thiếu T5/T6 → BLOCK, redirect sang @user-discovery
- Nếu MUST > 3 (solo) → force re-prioritize, demote weakest
- Nếu feature không map tới need → reject: "Need nào? Nếu không có → WON'T"
- Nếu user nói "add feature" mà scope locked → cảnh báo scope creep + INVEST check

---

## HANDOFF

Khi T8-T9 hoàn thành:
```
✅ Feature Scoping DONE — [Project]
   MUST features: [list]
   MVP scope: [N] features
   User stories: [N] stories with acceptance criteria

→ Bước tiếp: Chạy @ui-ux-pro-max để design UX/UI cho MVP features.
  Input: t8_features.md + t9_mvp_scope.md + t4_personas.md
```
