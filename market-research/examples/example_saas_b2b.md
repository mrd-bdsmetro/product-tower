# Example: TaskFlow — SaaS B2B Project Management (T0)

## Input
```
Lĩnh vực: SaaS B2B (Project Management)
Thị trường: SEA startups (5-50 người)
Vốn: $15K
Ý tưởng: PM tool tích hợp AI auto-assign tasks
Mode: Express
```

## Loop 1 Output (Express — 🤖 60%)

### t1_target_market.md (excerpt)
```markdown
# Target Market: AI PM Tool — SEA

- 🤖 PM software market SEA: ~$800M (2025)
- 🤖 SMB segment (<50 employees): ~30% = $240M
- 🤖 AI-enhanced PM: emerging sub-segment (<$50M)
- 🤖 Competitors: Asana, Monday, Jira, ClickUp, Notion
```

### t3_filter.md (excerpt)
```markdown
# Segment Filter

| Criteria | Startups 5-50 | Freelancers | Enterprise |
|----------|---------------|-------------|------------|
| Budget fit ($15K) | ✅ | ✅ | ❌ |
| AI value-add | ✅ High | 🟡 Medium | ✅ High |
| Reachable | ✅ Online | ✅ Online | ❌ Gatekeeper |
| WTP | $10-30/seat/mo | $0-10/mo | $50+/seat |

→ KEEP: Startups 5-50
→ DISCARD: Enterprise (budget mismatch), Freelancers (low WTP)
```

## Loop 2 Delta (Counter-research)

```markdown
KILLED:
  - "PM market $800M in SEA" → more like $300M (overcount)
  - "AI auto-assign = differentiator" → Monday.com đã có, ClickUp beta

CONFIRMED:
  - SMB pain: tool overload (Slack + Asana + Notion = chaos)
  - SEA startups underserved vs US market

NEW:
  - Real gap: không phải AI assign, mà AI summarize + reduce meetings
  - 📊 Gartner: "70% PM tool features unused" → less is more
```

## Loop 3 Delta (Interviews — 5 startup CTOs)

```markdown
KILLED:
  - "Auto-assign tasks" → 3/5 nói "tao muốn tự assign, AI đừng đoán"

CONFIRMED:
  - Tool overload pain = real (5/5 dùng 3+ tools)
  - Budget $10-30/seat acceptable

NEW:
  - 👤 "Meeting summary + action items tự extract = game changer" — CTO #2
  - 👤 Vietnamese startups prefer Vietnamese UI (4/5)
  - 👤 Biggest WTP driver: thời gian tiết kiệm, không phải features

PMF: raw 7, adjusted 7, Loop 3, penalty 0 → PASS ✅
```
