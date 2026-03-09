# QA Process — Test Strategy, Regression, Bug Triage

> Product Tower Tầng 13: Kiểm thử liên tục VỚI user từ đầu.
> QA không phải giai đoạn cuối — QA chạy SONG SONG dev.

---

## Test Pyramid (Solo Founder Edition)

```
         ╱╲
        ╱ E2E ╲        ← Ít nhất, tốn nhất (browser tests)
       ╱────────╲
      ╱Integration╲    ← Trung bình (API, DB tests)
     ╱──────────────╲
    ╱   Unit Tests    ╲  ← Nhiều nhất, nhanh nhất
   ╱────────────────────╲

   === SOLO FOUNDER SHORTCUT ===
   Tối thiểu: Unit (core logic) + 3 E2E (happy paths)
```

---

## Test Strategy Template

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🧪 TEST STRATEGY — [Product]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

UNIT TESTS (tự động):
  □ Core business logic
  □ Utility functions
  □ Data transformations
  Tool: Jest / Vitest / pytest

INTEGRATION TESTS (tự động):
  □ API endpoints (CRUD)
  □ Database queries
  □ Auth flow
  Tool: Supertest / pytest

E2E TESTS (tự động — top 3 happy paths):
  □ User signup → login → core feature
  □ Core feature → complete task → result
  □ Payment flow (if applicable)
  Tool: Playwright / Cypress

MANUAL TESTING (mỗi sprint):
  □ Cross-browser: Chrome, Safari, Firefox
  □ Mobile responsive: 375px, 768px
  □ Edge cases: empty states, errors, slow network
  □ Accessibility: keyboard nav, screen reader

USER TESTING (mỗi 2 tuần):
  □ 5 users test prototype/MVP
  □ Observe + record issues
  □ Prioritize fixes

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Bug Triage — Priority Matrix

```
              FREQUENCY CAO         FREQUENCY THẤP
             ┌──────────────────┬──────────────────┐
SEVERITY     │  🔴 P0: FIX NOW  │  🟡 P1: THIS     │
CAO          │  (blocker)       │  SPRINT           │
(crash/      ├──────────────────┼──────────────────┤
data loss)   │  🟢 P2: NEXT     │  ⚪ P3: BACKLOG   │
SEVERITY     │  SPRINT          │  (when free)       │
THẤP         └──────────────────┴──────────────────┘
```

### Bug Report Template

```
BUG #___: [Tiêu đề ngắn]
Priority: [P0/P1/P2/P3]
Reporter: [Ai?]
Date: [DD/MM/YYYY]

STEPS TO REPRODUCE:
1. ___
2. ___
3. ___

EXPECTED: ___
ACTUAL: ___
SCREENSHOT: [link]

ENVIRONMENT:
  Browser: ___  |  OS: ___  |  Device: ___
```

---

## Regression Testing

### Khi nào chạy Regression?

| Trigger | Regression scope |
|---------|-----------------|
| Merge feature mới | Test core flows + feature mới |
| Fix bug P0/P1 | Test bug fix + related features |
| Deploy to production | Full regression (top 5 flows) |
| Dependency update | Smoke test all features |

### Regression Checklist (Top 5 Flows)

```
□ 1. Auth: Signup → Login → Logout → Reset password
□ 2. Core Feature: [main user flow từ đầu đến cuối]
□ 3. Data: Create → Read → Update → Delete
□ 4. Payment: (if applicable) Add card → Pay → Receipt
□ 5. Settings: Edit profile → Change password → Notifications
```

> **Solo founder rule:** Automate top 3, manual test 4-5.

---

## Continuous Testing Timeline

```
DAILY:     Unit tests run on save (auto)
PR/MERGE:  Integration tests (CI pipeline)
WEEKLY:    E2E regression (automated)
BI-WEEKLY: User testing (5 users)
MONTHLY:   Full audit (performance + security + accessibility)
```

---

## Solo Founder QA Shortcuts

| Full team | Solo shortcut |
|-----------|--------------|
| QA team tests everything | Automate happy paths, manual edge cases |
| Formal bug tracker | GitHub Issues + Priority label |
| Staging environment | Preview deployments (Vercel/Netlify) |
| Full regression suite | Top 3 E2E tests + smoke test |
| Weekly QA meetings | 30 phút Friday self-review |
