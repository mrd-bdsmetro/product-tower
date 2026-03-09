# 🏗️ Product Tower — AI Product Management Framework

> 13 tầng build sản phẩm bài bản. Từ thị trường → user → PMF → features → ship.
> Dành cho founder, PM, và bất kỳ ai muốn build right, not fast.

---

## 🎯 Product Tower là gì?

Framework 13 tầng giúp build sản phẩm **user-centric**:

```text
T13:    QA / Testing        ← @testing-patterns + @tdd-workflow
T12:    Development         ← @clean-code
T10-11: UX/UI Design        ← @ui-ux-pro-max
──────────────────────────────────────────────
T8-9:   Feature Scoping     ← @feature-scoping ✅
T7:     PMF Gate ⚠️          ← @pmf-validator ✅
T4-6:   User Discovery      ← @user-discovery ✅
T1-3:   Market Segmentation ← @market-segmentation ✅
```

> **Rule: Build từ dưới lên. Skip = cascade failure.**

---

## ⚡ Quick Start

```text
"Đánh giá product tower cho [project]"
"Tao muốn build sản phẩm cho [market]"
"Project tao đang ở tầng nào?"
```

---

## 📦 What's Included (4 sub-skills)

| Skill | Tầng | Files | Lines | Frameworks |
|-------|------|-------|-------|-----------|
| `market-segmentation` | 1-3 | 11 | 1,264 | STP, TAM-SAM-SOM, JTBD |
| `user-discovery` | 4-6 | 11 | 1,166 | BAG Persona, Mom Test, RICE, Kano |
| `pmf-validator` | 7 | 8 | 717 | Sean Ellis 40%, Superhuman Engine |
| `feature-scoping` | 8-9 | 10 | 893 | MoSCoW, INVEST, Story Mapping |
| **TOTAL** | | **40** | **4,040** | |

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
product_tower/
├── SKILL.md                      ← Orchestrator (routes to sub-skills)
├── README.md                     ← This file
├── LICENSE                       ← MIT License
├── CONTRIBUTING.md               ← Contribution guidelines
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
      → Bước tiếp: hoàn thành @feature-scoping
```

### Example 3: PMF validation
```
You:  "Survey 80 users xong, 47% rất thất vọng"
AI:   📊 PMF Validator — Tầng 7
      ✅ PMF CONFIRMED (47% > 40%)
      → HXC Profile: CTO startup 5-10 người
      → Next: @feature-scoping cho paid plan
```

### Example 4: Feature scoping
```
You:  "Build gì trước cho TaskFlow?"
AI:   📋 Feature Scoping — Tầng 8-9
      → MoSCoW: 3 MUST + 1 SHOULD = MVP
      → 4 user stories with INVEST + acceptance criteria
      → Ship in 2 weeks
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
A: Có. Skip = cascade failure. Tuy nhiên, nếu đã có data sẵn (ví dụ đã biết market), bạn có thể chạy nhanh qua tầng đó thay vì skip.

**Q: AI platform nào support?**
A: Thiết kế cho **Antigravity (Gemini)** nhưng hoạt động trên bất kỳ AI nào hiểu markdown instructions (Claude, GPT, Cursor, etc.)

**Q: Khác gì so với Product Management frameworks khác?**
A: Product Tower là **AI-native** — mỗi tầng là 1 skill với instructions, templates, examples. AI thực hiện framework, không chỉ giải thích framework.

**Q: Dùng 1 skill riêng lẻ được không?**
A: Được. Mỗi sub-skill hoạt động độc lập. Nhưng kết quả tốt nhất khi dùng full pipeline (T1 → T9).

---

## 📄 License

MIT — Free to use, modify, and distribute.

**Version:** 1.0
**Author:** Mr.D × Skill Creator Ultra
**Last Updated:** 2026-03-09
