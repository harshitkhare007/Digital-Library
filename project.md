📚 Digital Library — Complete Project 
🎯 What Is It?
Digital Library is an AI-powered public information assistant website built as a single HTML file that runs entirely in the browser — no server, no backend, no API keys required. It helps citizens, students, and youth find government services, public resources, learning materials, career opportunities, and trending tech skills through a conversational chat interface.

🧠 Core Idea
The original idea was to build an AI-powered solution that improves access to information, resources, and opportunities in public systems. The website evolved from a basic civic information tool into a full-featured digital resource hub dedicated to students and the general public.

🏗️ Project Evolution — What Was Built Step by Step
Step	What Was Added
1	Basic CivicAI chat with 7 public service categories
2	Wikipedia button added to the header
3	Explore Subjects category — search any topic across 6 web platforms
4	Name changed from CivicAI to Digital Library, title centred
5	Opportunities category — 12 cards for youth, students, internships
6	All 7 categories given unique bright colours
7	⚡ Tech Skills popup — auto-opens on page load, top-right corner
8	Background changed to animated multicolour light aurora gradient
9	UI/UX enhanced — glassmorphism, neon accents, animations
10	Background made lighter and softer with pastel tones
📁 Files Created
File	Purpose
harshit.html	The main Digital Library website
workflow.html	Visual workflow diagram of how the site works
🎨 Visual Design
Background

Animated pastel aurora — sky blue, lavender, mint green, peach, periwinkle
Two layered CSS radial gradient blobs that slowly shift hue using keyframe animations
Runs at 14 seconds and 18 seconds in opposite directions for a living, breathing feel
Header

Frosted glass white background with a soft purple border
Title "Digital Library" in a cyan → purple → pink gradient text
📚 book emoji as the logo above the title
Subtitle in soft indigo below
⚡ Tech Skills glowing amber button pinned to the left
📖 Wikipedia link button pinned to the right
Layout

Two-column layout — sidebar on the left, main chat area on the right
Maximum width 1200 pixels, centred on the screen
Fully responsive — stacks vertically on mobile screens
🗂️ Categories and Their Colours
Category	Colour	What It Shows
🏥 Healthcare	Rose Red	Medicaid, CHIP, Community Clinics, Healthcare.gov
🎓 Education	Warm Amber	FAFSA, Pell Grant, GED Programs, Digital Literacy
🏠 Housing	Sky Blue	HUD, Section 8, Emergency Shelter, Eviction Help
💼 Employment	Emerald Green	CareerOneStop, Unemployment, Job Corps, Workforce
⚖️ Legal Aid	Purple	Legal Services Corp, LawHelp, ACLU, Court Help
🍎 Food Assistance	Orange	SNAP, WIC, Food Banks, School Meals
🚌 Transportation	Electric Blue	Public Transit, Medicaid Rides, Senior Transport
🔭 Explore Subjects	Indigo	Wikipedia, Google, Khan Academy, Scholar, YouTube
🚀 Opportunities	Teal Green	Internships, Scholarships, Competitions, Programs
⚡ Tech Skills	Amber Orange	12 trending skills for 2025 job market
💬 Chat System — How It Works
When a user types a message or clicks a category card:

The message appears in the chat as a user bubble on the right
A typing indicator (three bouncing dots) appears for 900 milliseconds
The system scans the message for keywords using regex pattern matching
The correct response is chosen and rendered as a bot bubble on the left
Resource cards appear inside the bot bubble with real links
Keyword routing logic:

Keywords Detected	Response Given
health, medic, doctor, clinic	Healthcare resources
school, college, fafsa, scholarship	Education resources
hous, rent, shelter, evict, homeless	Housing resources
job, work, employ, career, resume	Employment resources
legal, lawyer, court, rights, law	Legal aid resources
food, hungry, snap, wic, grocery	Food assistance resources
bus, transit, transport, ride, train	Transportation resources
opportunit, internship, hackathon	Opens Opportunities panel
tell me about / what is / explain X	Shows 6 web source cards for topic X
hi, hello, hey	Friendly greeting
emergency, crisis, urgent	911 · 211 · 988 numbers
veteran, military	VA.gov
disability, disabled	SSA.gov, ADA.gov
immigrant, immigration	USCIS, ImmigrationAdvocates
thank, thanks	Acknowledgement + call 211 tip
🔭 Explore Subjects Feature
A dedicated search panel that opens inside the main area. The user types any topic — science, history, geography, technology, anything — and gets six direct links:

Source	What It Provides
📖 Wikipedia	Full encyclopedia article
🔍 Google Search	Web search + latest news
🎓 Khan Academy	Free educational videos and lessons
📰 Google Scholar	Peer-reviewed academic papers
🎬 YouTube	Educational videos and documentaries
📚 Internet Archive	Free books and historical documents
10 quick-topic tags are provided: AI, Climate Change, Human Anatomy, WW2, Quantum Physics, Space, Democracy, Blockchain, Psychology, Renewable Energy

🚀 Opportunities Feature
A green-themed panel showing 12 curated opportunity cards for youth and students, filterable by category:

Filter	Examples
💻 Tech	Google Summer of Code, GitHub Student Pack, Meta Internship
🎓 Scholarships	Gates Scholarship, Chevening Scholarship
💼 Internships	NASA Internship, CERN Summer Programme
🏆 Competitions	MIT Hacking Medicine, Hyperloop Competition
🌍 Programs	UN Youth Volunteer, Google Career Certificates, Microsoft AI Skills
Each card shows a status badge (🔥 Hot / ✨ New / 🆓 Free / 🟣 Open), a description, and two links — one to apply and one to read the latest news.

⚡ Tech Skills Feature
A floating popup that automatically opens 1 second after the page loads in the top-right corner. It shows 12 trending tech skills for 2025, filterable by:

Filter	Skills
🤖 AI	Generative AI & Prompt Engineering, Machine Learning & Deep Learning
🌐 Web	React & Next.js, Rust & WebAssembly
📊 Data	Data Engineering & dbt, Vector Databases & RAG
☁️ Cloud	AWS / Azure / GCP, Kubernetes & DevOps
🔐 Cyber	Cybersecurity & Ethical Hacking, Zero Trust & Cloud Security
📱 Mobile	Flutter & Cross-Platform Dev, Swift & iOS Development
Each skill card has a coloured category badge, a description of market demand, a free learning link, and a job trends link.

🗃️ Data Structure
All data is stored locally in JavaScript — no database, no API needed:

Data Object	Contents
KB{}	7 service categories × 4 resources each = 28 resource entries
OPPS[]	12 opportunity cards with tags, badges, descriptions, and links
SKILLS[]	12 tech skill cards with category tags, descriptions, and links
⚙️ JavaScript Functions
Function	What It Does
sendMessage()	Main handler — reads input, routes to correct response
detectCategory(text)	Regex keyword scanner — returns category name or null
buildResponse(cat)	Builds HTML resource cards from KB data
buildSubjectResponse(topic)	Builds 6 web source cards for any topic
fallbackResponse(text)	Handles special queries — greetings, emergencies, veterans
appendMessage(role, html)	Adds a message bubble to the chat window
showTyping()	Shows three-dot bouncing animation
removeTyping()	Removes typing indicator before showing response
toggleSubjectPanel()	Opens or closes the Subject Explorer panel
searchSubject()	Processes subject search and sends to chat
toggleOppsPanel()	Opens or closes the Opportunities panel
renderOpps(filter)	Renders filtered opportunity cards
filterOpps(tag, btn)	Switches the active opportunities filter tab
toggleSkillsPopup()	Opens or closes the Tech Skills popup
renderSkills(filter)	Renders filtered skill cards
filterSkills(tag, btn)	Switches the active skills filter tab
sendChip(text)	Sets input value and sends — used by chips
askCategory(cat)	Shortcut to send a category query via sendChip
🎞️ Animations and Effects
Effect	Where Used
Aurora gradient animation	Full page background — 14s and 18s loops
Gradient text	Header title using background-clip: text
Fade-in + slide-up	Every new chat message
Bouncing dots	Typing indicator while bot responds
Glow pulse	⚡ Tech Skills header button — 2.5s loop
Slide-down + scale	Tech Skills popup opening animation
Hover slide + scale	All sidebar category cards
Border glow on focus	Chat input bar when clicked
Hover glow shadow	Send button, resource cards, skill cards
Frosted glass	Chat window, input bar, panels, popup
📱 Responsive Behaviour
Screen Size	Layout
Above 768px	Sidebar left + main area right, side by side
Below 768px	Sidebar stacks above main area, cards wrap horizontally
Mobile	Header buttons shrink, popup takes full width
🔗 All External Resources Linked
Government sites: medicaid.gov · insurekidsnow.gov · healthcare.gov · studentaid.gov · hud.gov · careeronestop.org · dol.gov · lsc.gov · fns.usda.gov · transit.dot.gov · va.gov · ssa.gov · ada.gov

Learning platforms: khanacademy.org · deeplearning.ai · nextjs.org · flutter.dev · tryhackme.com · kubernetes.io · learn.microsoft.com · grow.google

Opportunity sites: summerofcode.withgoogle.com · thegatesscholarship.org · intern.nasa.gov · education.github.com · hackingmedicine.mit.edu · careers.cern · chevening.org · unv.org

📊 Project Numbers at a Glance
Metric	Count
Total HTML files	2
Lines of code (approx.)	1,100+
Service categories	7
Resource entries	28
Opportunity cards	12
Tech skill cards	12
Subject quick-tags	10
Web sources per subject search	6
Fallback response handlers	7
JavaScript functions	18
CSS animations	8+
External trusted links	40+
✅ Final Result
A fully functional, beautifully designed, single-file AI-powered public information assistant that:

Requires zero setup — just open in any browser
Helps anyone find government services, resources, and opportunities
Educates students with subject exploration across the web
Inspires youth with curated internships, scholarships, and competitions
Upskills learners with trending 2025 tech skills and free course links
Looks premium with glassmorphism, gradient animations, and smooth transitions
Works on all devices with fully responsive layout
