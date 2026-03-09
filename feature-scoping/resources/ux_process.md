# UX Process — Wireframe Flow, IA, Prototyping

> Product Tower Tầng 10: Luồng trải nghiệm, kiến trúc thông tin, wireframe.
> Output: Low-fidelity wireframe → CHO UI designer pixel-perfect.

---

## 3 Bước UX Design

```
BƯỚC 1: INFORMATION ARCHITECTURE (IA)
  → Tổ chức nội dung + navigation
  
BƯỚC 2: WIREFRAME (Low-Fidelity)
  → Sketch layout + flow, KHÔNG có màu/font
  
BƯỚC 3: PROTOTYPE (Interactive)
  → Click-through để test với user thật
```

---

## BƯỚC 1: Information Architecture (IA)

### Site Map Template

```
HOME
├── Feature 1 (Core)
│   ├── Sub-page A
│   └── Sub-page B
├── Feature 2
│   ├── Sub-page C
│   └── Sub-page D
├── About / Pricing
├── Auth
│   ├── Login
│   ├── Register
│   └── Forgot Password
└── Dashboard (logged in)
    ├── Overview
    ├── Settings
    └── Profile
```

### Navigation Rules

| Rule | Giải thích |
|------|-----------|
| **3-Click Rule** | User đến được MỌI trang trong ≤ 3 clicks |
| **7±2 Rule** | Menu chính ≤ 7 items (cognitive load) |
| **F-Pattern** | Đặt CTA ở top-left → top-right (scan pattern) |
| **Progressive Disclosure** | Chỉ hiện info cần thiết, ẩn phần còn lại |

### Card Sorting (nếu nhiều content)
```
1. Liệt kê TẤT CẢ pages/features trên post-it
2. Cho 5 users tự nhóm theo logic CỦA HỌ
3. Pattern → đó là IA tự nhiên cho user
```

---

## BƯỚC 2: Wireframe (Low-Fidelity)

### Wireframe Checklist

```
□ Layout grid (12-column hoặc 4-column mobile)
□ Header + Navigation
□ Hero / Main content area
□ CTA placement (above the fold)
□ Content hierarchy (H1 → H2 → body)
□ Form fields + labels
□ Error states
□ Empty states ("No data yet")
□ Loading states
□ Footer
```

### Wireframe Tools (miễn phí)

| Tool | Best for | Cost |
|------|---------|------|
| **Excalidraw** | Quick sketch, hand-drawn feel | Free |
| **Figma** | Professional, collaboration | Free tier |
| **Balsamiq** | Rapid wireframing | $9/mo |
| **Paper + Pen** | Fastest possible | Free |

### Key Pages cho MVP (ưu tiên wireframe)

```
1. Landing page / Homepage
2. Core feature page (main value)
3. Auth flow (login/register)
4. Dashboard (logged-in state)
5. Pricing page (if SaaS)
```

> ⚠️ **KHÔNG wireframe tất cả.** Chỉ wireframe 5 key pages cho MVP.

---

## BƯỚC 3: Prototype

### Prototype Levels

| Level | Tool | Khi nào |
|-------|------|---------|
| **Paper** | Paper + scissors | Idea validation (5 phút) |
| **Clickable** | Figma prototype | User testing (1-2 ngày) |
| **Coded** | HTML/React | Dev handoff (3-5 ngày) |

### User Testing với Prototype (5 users)

```
SCRIPT (10 phút/user):

1. "Mở trang này, tìm [core feature]"
   → Quan sát: họ click đâu? Bị kẹt ở đâu?

2. "Hoàn thành task [key action]"
   → Đo: bao nhiêu bước? Bao lâu?

3. "Cái gì confusing nhất?"
   → Ghi nhận: UX issue

4. "Bạn mong đợi thấy gì ở đây?"
   → Phát hiện: missing features / wrong placement
```

> **5 users tìm được 85% UX issues** (Nielsen Norman Group).

---

## UX ≠ UI

| UX (Tầng 10) | UI (Tầng 11) |
|--------------|-------------|
| Luồng (flow) | Màu sắc |
| Cấu trúc (IA) | Typography |
| Wireframe | Pixel-perfect mockup |
| "Dùng thế nào?" | "Nhìn thế nào?" |
| Research-driven | Aesthetic-driven |

> **UX trước, UI sau.** Đừng chọn màu khi chưa biết layout.
