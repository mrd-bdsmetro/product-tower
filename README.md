# 🏗️ Product Tower — AI Product Management Framework

> 13 tầng build sản phẩm bài bản. Từ thị trường → user → PMF → features → ship.
> Dành cho founder, PM, và bất kỳ ai muốn build right, not fast.

---

## 🎯 Product Tower là gì?

Framework 13 tầng giúp build sản phẩm **user-centric**:

```
T12-13: Build + QA          ← @clean-code (existing)
T10-11: UX/UI Design        ← @ui-ux-pro-max (existing)
──────────────────────────────────────────────────
T8-9:   Feature Scoping     ← @feature-scoping ✅
T7:     PMF Gate ⚠️          ← @pmf-validator ✅
T4-6:   User Discovery      ← @user-discovery ✅
T1-3:   Market Segmentation ← @market-segmentation ✅
```

> **Rule: Build từ dưới lên. Skip = cascade failure.**

---

## ⚡ Quick Start

```
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

```
Build product_tower/
├── README.md                     ← This file
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
    ├── resources/ (4 files)
    └── examples/ (3 files)
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

## 📄 License

MIT — Free to use, modify, and distribute.

**Version:** 1.0
**Author:** Mr.D × Skill Creator Ultra
**Last Updated:** 2026-03-09
