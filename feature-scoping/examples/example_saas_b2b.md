# Example: TaskFlow — Feature Scoping (Simple)

## Input từ @pmf-validator
- **PMF Score**: 47.5% ✅
- **HXC**: CTO/Tech Leads ở startup 5-10 người
- **Core value**: Auto status updates from Git commits
- **Top gap**: GitLab support (10/25 "hơi thất vọng")
- **Personas**: CTO Minh (solo founder, 8-dev team), Tech Lead Hoa (report to VP)

---

## TẦNG 8: FEATURE SET

### Unmet Needs → Features

```
UNMET NEED                    → PRODUCT          → FEATURES
                                                   
"Mất 30 min/ngày hỏi status" → Auto Tracker     → Git sync, Dashboard
"Không biết ai bị block"      → Smart Alerts     → Blocker detection, Slack
"Report cho sếp mất thời gian"→ Auto Reports     → Weekly summary, PDF
```

### MoSCoW Prioritization

| Priority | Feature | Map to Need | Effort | Notes |
|----------|---------|------------|--------|-------|
| **MUST** | Git commit → auto status | Core pain | 5 days | GitHub first |
| **MUST** | Team dashboard | Visibility | 3 days | Real-time view |
| **MUST** | Slack daily summary | Communication | 2 days | 9am auto-send |
| **SHOULD** | GitLab integration | Top gap | 3 days | Unlock 40% "hơi thất vọng" |
| **SHOULD** | Client-facing view | Report to CEO | 3 days | Read-only board |
| **COULD** | Sprint progress view | Planning | 3 days | v1.1 |
| **COULD** | Smart deadline warnings | Proactive | 3 days | AI-based |
| **WON'T** | AI task assignment | Over-engineering | 15 days | v2.0, nếu có |
| **WON'T** | Mobile app | Scope creep | 20 days | Web responsive đủ |

### MVP Scope (Solo Founder Rule)

```
MVP = 3 MUST + 1 SHOULD (GitLab — giải top gap)
Timeline: 13 days → 2 tuần (buffer 1 day)
Features: 4 total
Risk: GitLab API complexity — nếu delay → ship 3 MUST trước
```

> ⚠️ Tại sao chọn SHOULD GitLab cho MVP? Vì 40% "hơi thất vọng" 
> cite GitLab = potential +10% PMF nếu solve. ROI rất cao.

---

## TẦNG 9: USER STORIES (MVP)

### Story 1 — Core (MUST)
```
Là CTO STARTUP (5-10 devs),
tôi muốn STATUS TỰ CẬP NHẬT TỪ GIT COMMITS,
để KHÔNG CẦN HỎI TEAM MỖI SÁNG.

AC: GIVEN team member push code lên GitHub,
    WHEN commit message = "feat: add user login",
    THEN dashboard hiện: "Minh — working on user login — 2h ago"
INVEST: 6/6 ✅  |  Size: L (5 days)
```

### Story 2 — Dashboard (MUST)
```
Là TECH LEAD,
tôi muốn XEM DASHBOARD TOÀN TEAM,
để BIẾT AI ĐANG LÀM GÌ REAL-TIME.

AC: GIVEN tôi login vào TaskFlow,
    WHEN mở Team Dashboard,
    THEN thấy: tên, task hiện tại, last activity, status (on track/blocked)
INVEST: 6/6 ✅  |  Size: M (3 days)
```

### Story 3 — Slack (MUST)
```
Là CTO,
tôi muốn NHẬN SUMMARY TRÊN SLACK MỖI SÁNG,
để KHÔNG CẦN MỞ THÊM APP.

AC: GIVEN cài Slack integration,
    WHEN đến 9:00 AM mỗi ngày,
    THEN bot gửi: "[Team] Yesterday: 12 commits, 3 PRs merged, 1 blocker"
INVEST: 6/6 ✅  |  Size: S (2 days)
```

### Story 4 — GitLab (SHOULD)
```
Là CTO DÙNG GITLAB,
tôi muốn CONNECT GITLAB REPO THAY VÌ GITHUB,
để DÙNG TASKFLOW VỚI STACK HIỆN TẠI.

AC: GIVEN tôi chọn "Connect GitLab" trong settings,
    WHEN paste GitLab access token,
    THEN commits từ GitLab hiện trên dashboard (y như GitHub)
INVEST: 6/6 ✅  |  Size: M (3 days)
```

---

## Story Map

```
USER JOURNEY: CTO STARTUP → Track team → Get updates → Report

SETUP        →    TRACK         →    COMMUNICATE    →    REPORT
    │                 │                  │                 │
  Connect Git      Dashboard         Slack bot         Client view
  Add team         Activity log      @mention          Weekly PDF
═══════════════════ MVP LINE ══════════════════════════════════
  GitLab sync     Sprint view       Email digest       Custom board
  SSO login       Blocker AI        MS Teams bot       Investor view
```

---

## Summary

```
✅ Feature Scoping: TaskFlow
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MVP: 4 stories (3 MUST + 1 SHOULD)
Timeline: 13 days (~2 weeks)
Total effort: 13 person-days
Ship to: Existing 80 beta users + marketing push

→ Next: @ui-ux-pro-max cho dashboard design
  hoặc @clean-code nếu skip design (dev tool = function > form)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## Bài học
- **SHOULD trong MVP chỉ khi data rõ ràng** — 40% cite GitLab = strong signal
- **Dev tools = function > form** — có thể skip @ui-ux-pro-max, jump to @clean-code
- **"WON'T HAVE" quan trọng nhất** — nó set boundary, tránh scope creep
- **Story Map visual** — giúp founder thấy rõ MVP line, không bị lôi kéo build hết
