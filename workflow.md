 Digital Library — Website Workflow
1. Page Load
Browser opens harshit.html
        │
        ▼
Fonts load (Inter via Google Fonts)
        │
        ▼
Animated multicolour light background renders
(aurora gradient: sky blue → lavender → mint → peach)
        │
        ▼
⚡ Tech Skills popup AUTO-OPENS after 1 second
(top-right corner, amber glow button)
2. Header Bar
┌─────────────────────────────────────────────────────┐
│  ⚡ Tech SkillsBtn │   📚 Digital Library   │ 📖 Wikipedia │
│   (left, amber)    │  (centre, gradient)    │ (right, link) │
└─────────────────────────────────────────────────────┘
Tech Skills button → opens/closes the skills popup
Wikipedia link → opens wikipedia.org in new tab
3. Main Layout
┌──────────────┬─────────────────────────────────────┐
│   SIDEBAR    │           MAIN AREA                  │
│  (left col)  │                                      │
│              │  [Quick Chips / shortcuts]           │
│  Categories  │                                      │
│              │  [Active Panel - if open]            │
│  Stats Box   │                                      │
│              │  [Chat Window]                       │
│              │                                      │
│              │  [Input Bar + Send Button]           │
└──────────────┴─────────────────────────────────────┘
4. Sidebar Category Flow
User clicks a Category Card
        │
        ├── 🏥 Healthcare    ──► Chat response with Medicaid, CHIP, Clinics links
        ├── 🎓 Education     ──► Chat response with FAFSA, Pell Grant, GED links
        ├── 🏠 Housing       ──► Chat response with HUD, Section 8, Shelter links
        ├── 💼 Employment    ──► Chat response with CareerOneStop, Job Corps links
        ├── ⚖️ Legal Aid     ──► Chat response with LSC, LawHelp, ACLU links
        ├── 🍎 Food Assist.  ──► Chat response with SNAP, WIC, Food Bank links
        ├── 🚌 Transport     ──► Chat response with Transit, Medicaid Rides links
        │
        ├── 🔭 Explore Subj. ──► Opens Subject Search Panel (indigo)
        ├── 🚀 Opportunities ──► Opens Opportunities Panel (green)
        └── ⚡ Tech Skills   ──► Opens Tech Skills Popup (amber)
5. Chat Workflow
User types message → presses Enter or clicks Send
        │
        ▼
   detectCategory(text)
        │
        ├── keyword match? (health/medic/doctor...)
        │        └──► buildResponse(category)
        │               └──► Renders resource cards with .gov links
        │
        ├── subject pattern? (tell me about / what is / explain...)
        │        └──► buildSubjectResponse(topic)
        │               └──► Returns 6 source cards:
        │                    Wikipedia, Google, Khan Academy,
        │                    Scholar, YouTube, Archive.org
        │
        ├── opportunities / internship / scholarship?
        │        └──► toggleOppsPanel() — opens green panel
        │
        └── none matched?
                 └──► fallbackResponse()
                        ├── hi/hello → greeting
                        ├── thank → acknowledgement
                        ├── 211 → helpline info
                        ├── emergency → 911/988 info
                        ├── veteran → VA.gov
                        ├── disability → SSA/ADA
                        └── default → guide message
6. Subject Explorer Panel Flow
Click "🔭 Explore Subjects" (sidebar or chip)
        │
        ▼
Subject Search Panel opens (slide-in animation)
        │
        ├── User types topic OR clicks a quick tag
        │   (AI, Climate Change, WW2, Quantum Physics...)
        │
        ▼
searchSubject(topic) called
        │
        ▼
Panel closes → message sent to chat
        │
        ▼
buildSubjectResponse(topic) renders 6 cards:
  📖 Wikipedia ──────► en.wikipedia.org/wiki/{topic}
  🔍 Google ─────────► google.com/search?q={topic}
  🎓 Khan Academy ───► khanacademy.org/search?q={topic}
  📰 Google Scholar ─► scholar.google.com/scholar?q={topic}
  🎬 YouTube ────────► youtube.com/results?q={topic}
  📚 Internet Archive► archive.org/search?q={topic}
7. Opportunities Panel Flow
Click "🚀 Opportunities" (sidebar or chip)
        │
        ▼
Green panel opens with filter tabs
        │
        ├── All / Tech / Scholarships / Internships
        │   / Competitions / Programs
        │
        ▼
filterOpps(tag) → renders filtered cards
        │
Each card shows:
  - Badge (🔥Hot / ✨New / 🆓Free / 🟣Open)
  - Title + Description
  - Apply link + News/Search link
8. Tech Skills Popup Flow
Auto-opens 1s after page load (or click ⚡ button)
        │
        ▼
Popup slides in from top-right
Dark overlay appears behind it
        │
        ├── Filter tabs: All / AI / Web / Data / Cloud / Cyber / Mobile
        │
        ▼
filterSkills(tag) → renders skill cards
        │
Each card shows:
  - Category badge (coloured pill)
  - Skill name + description
  - Free course link + Job trends link
        │
        ▼
Close: click ✕ button or dark overlay
9. Data Flow Summary
All data is LOCAL (no server/API needed)
        │
        ├── KB{}       — 7 public service categories
        ├── OPPS[]     — 12 opportunity cards
        ├── SKILLS[]   — 12 tech skill cards
        └── All links  — real .gov & trusted external URLs
10. Responsive Behavior

Screen width > 768px  →  Sidebar left + Main right (side by side)
Screen width ≤ 768px  →  Sidebar stacks on top, cards wrap into rows
