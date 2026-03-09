# Story Map — User Journey × Feature Priority

> Tổ chức stories theo LUỒNG USER, không theo feature list.

---

## Story Map Structure

```
←────────────── USER JOURNEY (horizontal) ──────────────→

         DISCOVER    EVALUATE     DECIDE      USE
            │           │           │          │
BACKBONE:  Search      Compare    Price Info  Dashboard
(phải có)  Browse      Details    Contact     Settings
            │           │           │          │
WALKING    Filter      Save       Alerts      Export
SKELETON:  Sort        Share      History     Feedback
(MVP)       │           │           │          │
NICE TO    Suggest     AI rank    Predict     Portfolio
HAVE:      Maps view   Reviews    Report      API access
(later)
```

---

## How to Build a Story Map

### Bước 1: User Activities (horizontal)
```
Liệt kê các bước lớn user đi qua:
   Discover → Evaluate → Decide → Use → Retain
```

### Bước 2: User Tasks (backbone)
```
Mỗi activity, liệt kê tasks CHÍNH:
   Discover: [Search, Browse, Filter]
   Evaluate: [Compare, View Details, Read Reviews]
```

### Bước 3: Story Details (vertical)
```
Mỗi task, liệt kê user stories từ QUAN TRỌNG → ÍT:
   Search:
     Row 1 (MUST): Basic keyword search
     Row 2 (SHOULD): Advanced filters
     Row 3 (COULD): AI auto-suggest
```

### Bước 4: Draw the MVP Line
```
═══════════════ MVP LINE ═══════════════
Everything ABOVE = build now
Everything BELOW = build later
```

---

## Template

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🗺️ STORY MAP — [Product]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

ACTIVITIES:  [A1]    →    [A2]    →    [A3]    →    [A4]
              │            │            │            │
BACKBONE:   [task]       [task]       [task]       [task]
            [task]       [task]       [task]       [task]
              │            │            │            │
═══════════════════ MVP LINE ═══════════════════════════
              │            │            │            │
LATER:      [story]      [story]      [story]      [story]
            [story]      [story]      [story]      [story]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
MVP STORIES:  ___ stories above the line
LATER:        ___ stories below the line
SPRINT PLAN:  Sprint 1 = [stories], Sprint 2 = [stories]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Tips

1. **Horizontal = breadth** (cover full journey) > **Vertical = depth** (all features 1 area)
2. **MVP = thin horizontal slice** — mỗi activity 1-2 stories thôi
3. **Read left-to-right** = user journey. **Read top-to-bottom** = priority
4. **Invitee stakeholders** — story map là communication tool
