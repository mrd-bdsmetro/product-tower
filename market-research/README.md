# Market Research — Product Tower Tầng 0

> Data Foundation layer. Thu thập và tổ chức data thị trường để feed vào T1-T9.

## 2 Modes

| Mode | Thời gian | Dùng khi | Output quality |
|------|-----------|----------|----------------|
| 🐣 **EXPRESS** | ~2 giờ | Ý tưởng mới, test nhanh | AI-generated (60%) |
| 🦅 **PRO** | 30-60 phút + research | Project thật, cần cited sources | Real data (80-90%) |

## Output

9 files `.md` cho T1-T9:

```
data/
├── t1_target_market.md
├── t2_segments.md
├── t3_filter.md
├── t4_personas.md
├── t5_user_needs.md
├── t6_unmet_needs.md
├── t7_pmf.md
├── t8_features.md
└── t9_user_stories.md
```

## Quick Start

```text
"Research market cho [industry] tại [market]"
"Chạy T0 express cho BĐS HCMC"
"T0 pro mode — tao có reports rồi"
```

## Integration với 3-Loop Protocol

- **Loop 1**: Chạy Express mode → baseline data cho T0-T6
- **Loop 2**: Chạy Pro mode (add counter-research sources) → update data
- **Loop 3**: Add interview/field data → finalize

## Dependencies

- PRO mode cần `notebooklm-py` v0.3.3+ (optional)
- EXPRESS mode không cần cài gì thêm

## See Also

- [SKILL.md](./SKILL.md) — Full protocol
- [Parent: Product Tower](../README.md) — Orchestrator
