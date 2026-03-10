# 🏗️ Product Tower — AI Product Management Framework

> Build sản phẩm bài bản. Từ thị trường → user → PMF → features → ship.
> Dành cho founder, PM, và bất kỳ ai muốn build right, not fast.

---

## 🎯 Product Tower là gì?

Framework giúp build sản phẩm **user-centric** theo 5 blocks + **3-Loop data collection**:

```text
    ┌─────────────────┐
 5. │     BUILD       │  → @clean-code + @tdd-workflow       (T10-13)
    ├─────────────────┤
 4. │     SCOPE       │  → @feature-scoping                  (T8-9)
    ├─────────────────┤
 3. │  PMF GATE  ⚠️   │  → @pmf-validator                    (T7)
    ├─ ─ ─ ─ ─ ─ ─ ─ ┤
    │ 🔴 ANTI-BIAS    │  → AB1-AB4 (counter + red team + field + interview)
    ├─────────────────┤
 2. │     USER        │  → @user-discovery                   (T4-6)
    ├─────────────────┤
 1. │    MARKET       │  → @market-segmentation              (T1-3)
    ├─────────────────┤
 0. │    DATA  🔍     │  → @market-research                  (T0)
    └─────────────────┘

 Rule: Build từ dưới lên. Skip = cascade failure.
 Gate: T7 chưa pass PMF = KHÔNG lên T8+.
```

> **Product Tower = WHAT to build + WHY.** Design/Dev/QA (T10-13) = HOW → delegate sang skills khác.

---

## 🔄 3-Loop Protocol (v2.1 NEW)

Product Tower bắt buộc **3 vòng thu thập data** trước khi build:

```text
Loop 1 🤖  AI Desk Research     (~2 giờ)    → Confidence 60%  | PMF -2
Loop 2 📊  Counter + Red Team   (~1-2 ngày) → Confidence 80%  | PMF -0.5
Loop 3 👤  Real Human Data      (~1-2 tuần) → Confidence 90%+ | PMF 0
```

- **PMF chỉ chấm chính thức ở Loop 3** (sau khi có interview thật)
- Mỗi loop tạo `delta_report.md` so sánh thay đổi vs loop trước
- Data lưu theo `data/loop1/`, `data/loop2/`, `data/loop3/`

> Anti-Bias Layer = friction nhân tạo cho AI. Không framework nào khác bắt AI self-penalty PMF score.

---

## ⚡ Quick Start

```text
"Đánh giá product tower cho [project]"
"Tao muốn build sản phẩm cho [market]"
"Project tao đang ở tầng nào?"
"Đang ở loop mấy?"
```

---

## 📦 What's Included (6 sub-skills)

| Skill | Tầng | Frameworks |
|-------|------|------------|
| `market-research` | 0 | NotebookLM, AI desk research, Express/Pro mode |
| `market-segmentation` | 1-3 | STP, TAM-SAM-SOM, JTBD |
| `user-discovery` | 4-6 | BAG Persona, Mom Test, RICE, Kano |
| `pmf-validator` | 7 | Sean Ellis 40%, Superhuman Engine |
| `feature-scoping` | 8-9 | MoSCoW, INVEST, Story Mapping |
| Anti-Bias Layer | AB | Counter-search, Red Team, Field, Interview |

---

## 🔧 Installation

### Full Bundle (Recommended)

```bash
# macOS / Linux
cp -r market-segmentation ~/.gemini/antigravity/skills/
cp -r user-discovery ~/.gemini/antigravity/skills/
cp -r pmf-validator ~/.gemini/antigravity/skills/
cp -r feature-scoping ~/.gemini/antigravity/skills/

# Windows (PowerShell)
$skills = @("market-segmentation","user-discovery","pmf-validator","feature-scoping")
foreach ($s in $skills) {
    Copy-Item -Recurse $s "$env:USERPROFILE\.gemini\antigravity\skills\$s"
}
```

### Single Skill
```bash
cp -r [skill-name] ~/.gemini/antigravity/skills/[skill-name]
```

---

## 📁 Bundle Structure

```text
product-tower/
├── SKILL.md                      ← Orchestrator (routes to sub-skills)
├── README.md                     ← This file
├── LICENSE                       ← MIT License
├── CONTRIBUTING.md               ← Contribution guidelines
│
├── market-research/              ← T0 (Data Foundation)
│   ├── SKILL.md
│   ├── README.md
│   ├── resources/ (templates)
│   └── examples/ (3 case studies)
│
├── market-segmentation/          ← T1-3
│   ├── SKILL.md
│   ├── resources/ (5 files)
│   └── examples/ (3 files)
│
├── user-discovery/               ← T4-6
│   ├── SKILL.md
│   ├── resources/ (5 files)
│   └── examples/ (3 files)
│
├── pmf-validator/                ← T7
│   ├── SKILL.md
│   ├── resources/ (3 files)
│   └── examples/ (3 files)
│
└── feature-scoping/              ← T8-9
    ├── SKILL.md
    ├── resources/ (6 files)
    └── examples/ (3 files)
```

---

## 💬 Usage Examples

### Example 1: Starting from scratch
```
You:  "Tao muốn build sản phẩm cho thị trường BĐS"
AI:   📊 Market Segmentation — Product Tower Tầng 1-3
      → Chạy Decision Matrix, phân khúc, sizing TAM-SAM-SOM
      → Output: 3 segments filtered, positioning statements
```

### Example 2: Mid-project check
```
You:  "Project BDSmetro đang ở tầng nào?"
AI:   📊 Product Tower — Cascade Check
      T1-3 ✅ | T4-6 ✅ | T7 ✅ (PMF 43%) | T8-9 [/] in progress
      Loop: 3/3 ✅ | Anti-Bias: AB1-AB4 complete
      → Bước tiếp: hoàn thành @feature-scoping
```

### Example 3: 3-Loop tracking
```
You:  "Đang ở loop mấy?"
AI:   🔄 Loop Status
      Loop 1 ✅ (AI baseline) — 6 files
      Loop 2 ✅ (counter-research) — delta: killed 2 assumptions
      Loop 3 🟡 (3/5 interviews done)
      → Cần thêm 2 interviews trước khi chấm PMF
```

---

## 🎯 3 Case Studies (xuyên suốt)

Mỗi sub-skill đều có 3 ví dụ nhất quán:

| Example | Industry | Complexity | Key Lesson |
|---------|----------|-----------|------------|
| `example_bds_metro.md` | Real Estate VN | 🟡 Medium | Niche data play, VN context |
| `example_saas_b2b.md` | SaaS B2B | 🟢 Simple | Red ocean → AI gap |
| `example_fnb_local.md` | F&B Marketplace | 🔴 Complex | 2-sided, pivot, low expertise |

---

## ❓ FAQ

**Q: Product Tower chỉ dành cho startup?**
A: Không. Framework áp dụng cho bất kỳ sản phẩm mới nào — startup, side project, hoặc feature mới trong công ty lớn. Nhưng ví dụ focus solo founder vì đó là use case phổ biến nhất.

**Q: Có cần chạy hết 13 tầng không?**
A: Product Tower **own T0-T9** (Data → Market → User → PMF → Scope). T10-T13 (Design/Dev/QA) delegate sang skills khác. Skip tầng nào = cascade failure.

**Q: Tại sao bắt buộc 3 loops?**
A: AI desk research luôn biased (confirmation bias, survivorship bias). 3 loops bắt buộc thu thập data 3 lần với quality tăng dần. PMF chỉ chấm chính thức ở Loop 3 (sau interview thật).

**Q: AI platform nào support?**
A: Thiết kế cho **Antigravity (Gemini)** nhưng hoạt động trên bất kỳ AI nào hiểu markdown instructions (Claude, GPT, Cursor, etc.)

**Q: Dùng 1 skill riêng lẻ được không?**
A: Được. Mỗi sub-skill hoạt động độc lập. Nhưng kết quả tốt nhất khi dùng full pipeline (T1 → T9).

---

## 📄 License

MIT — Free to use, modify, and distribute.

**Version:** 2.1-pro
**Author:** Mr.D × Skill Creator Ultra
**Last Updated:** 2026-03-10
