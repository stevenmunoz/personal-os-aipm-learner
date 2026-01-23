# AI PM Learning Tool

[![Status](https://img.shields.io/badge/Status-Product%20Development-blue)]()
[![Stage](https://img.shields.io/badge/Stage-Research%20%26%20Design-orange)]()

**AI-powered content aggregation and learning path generation for AI Product Managers**

Save content from LinkedIn, Medium, and YouTube. Get AI-generated summaries, topic clustering, and personalized learning paths based on your goals and timeline.

---

## Problem Statement

AI PM learners face overwhelming content across multiple platforms:
- 📌 **Content Graveyard**: 100+ saved LinkedIn posts never read
- 🌊 **Information Overload**: 10-15 hours of content per week, can't keep up
- 🔍 **Lost Context**: "I know I saved something about agents..."
- 📚 **No Learning Path**: Random consumption without progression
- ❌ **Can't Apply Knowledge**: Consuming content ≠ Understanding

**Evidence:** Validated through 3 in-depth user research interviews with AI PM course students (Mike, Ricardo, Evelyn) using Teresa Torres' Continuous Discovery framework.

---

## Solution

An intelligent learning companion that:

1. **Aggregates Content** - Save from LinkedIn, Medium, YouTube, Twitter in one place
2. **AI Summarization** - Extract key concepts without re-reading everything
3. **Topic Clustering** - Auto-organize by theme (agents, evals, RAG, etc.)
4. **Intent-Based Paths** - "I have interview in 2 weeks" → personalized curriculum
5. **Semantic Search** - Find saved content by concept, not keywords

---

## User Personas (Evidence-Based)

### 1. The Career Transitioner (Primary)
- **Profile:** Traditional PM preparing for AI-native roles
- **Goal:** Land AI PM job in 3 months
- **Pain:** Can't recall what they learned despite consuming hours of content
- **Need:** Time-boxed interview prep paths (2 weeks, 1 month)

### 2. The Continuous Builder
- **Profile:** Current AI PM, learning while shipping
- **Goal:** Stay current + ship quality AI products
- **Pain:** Can't find saved content when blocked on implementation
- **Need:** Context-aware search, just-in-time retrieval

### 3. The Aspiring Specialist
- **Profile:** Junior PM or recent grad, new to AI
- **Goal:** Become job-ready AI PM in 6 months
- **Pain:** Paralysis by choice, overwhelmed by content firehose
- **Need:** Guided learning roadmap, clear progression

📄 **Full personas:** [Knowledge/Research/product-user-personas.md](Knowledge/Research/product-user-personas.md)

---

## Tech Stack

```
Frontend:  React 18 + TypeScript + Tailwind CSS
Extension: Chrome Extension (Manifest V3)
Backend:   Firebase (Cloud Functions, Firestore, Auth)
AI/ML:     Claude 3.5 Sonnet (summarization, path generation)
Vector DB: Pinecone (semantic search)
```

**Cost:** ~$18-20/month for 100 users (80% profit margin at $10/user)

**Development Timeline:** 4 weeks with 2 developers → MVP

📄 **Full architecture:** [Knowledge/Research/tech-stack-architecture.md](Knowledge/Research/tech-stack-architecture.md)

---

## Project Structure

```
personal-os-aipm-learner/
├── .claude/
│   └── agents/
│       ├── meeting-notes-distiller.md    # Meeting summary agent
│       └── research-analyst.md           # Teresa Torres framework agent
│
├── Knowledge/
│   ├── Meetings/                         # Meeting summaries
│   │   └── 2026-01-23_steven-divya-collaboration-kickoff.md
│   │
│   ├── Research/                         # User research & evidence
│   │   ├── opportunity-map.md            # Teresa Torres opportunity map
│   │   ├── product-user-personas.md      # 3 detailed personas + journey maps
│   │   ├── tech-stack-architecture.md    # Tech stack + ASCII diagram
│   │   ├── ai-pm-learner-personas-synthesis.md  # Evidence from student research
│   │   ├── mike-vela-check-in-analysis.md       # Research call #1
│   │   ├── ricardo-executive-summary.md         # Research call #2
│   │   └── evelyn-feedback.md                   # Research call #3
│   │
│   ├── Transcripts/                      # Raw meeting transcripts (Granola)
│   ├── Specs/                            # Feature specs & PRDs
│   ├── Process/                          # Development workflows
│   └── References/                       # External resources
│
├── Tasks/                                # Project tasks (backlog, todo)
├── BACKLOG.md                           # Feature ideas, bugs, notes
├── GOALS.md                             # Product goals & milestones
├── AGENTS.md                            # AI agent instructions
└── README.md                            # This file
```

---

## Development Phases (MVP)

### ✅ Phase 0: Research & Design (Current)
- [x] User research (3 interviews)
- [x] Persona definition
- [x] Tech stack selection
- [x] Architecture design
- [ ] Competitive analysis (in progress)
- [ ] Feature prioritization

### Phase 1: Foundation (Week 1-2)
**Goal:** User can save content and see it organized

- [ ] Firebase project setup
- [ ] User authentication (email + Google)
- [ ] Firestore schema implementation
- [ ] Basic web app (dashboard, list view)
- [ ] Chrome extension (save from LinkedIn)

### Phase 2: Intelligence (Week 3-4)
**Goal:** AI summarizes and clusters content

- [ ] Claude API integration (summarization)
- [ ] Cloud Functions (onContentSaved)
- [ ] Topic clustering algorithm
- [ ] Embedding generation (OpenAI)
- [ ] Pinecone vector search

### Phase 3: Personalization (Week 5-6)
**Goal:** Users can generate learning paths

- [ ] Intent-based search
- [ ] Learning path generation (Claude)
- [ ] Time-boxed curriculum
- [ ] Progress tracking
- [ ] Path completion UI

### Phase 4: Polish (Week 7-8)
**Goal:** Production-ready MVP

- [ ] Multi-source support (Medium, YouTube)
- [ ] Advanced filtering
- [ ] Mobile-responsive UI
- [ ] Performance optimization
- [ ] Beta user testing (10 users)

---

## Key Features (MVP Scope)

### Must-Have (P0) - Launch Blockers
- ✅ Save content from LinkedIn (browser extension)
- ✅ AI summarization (Claude)
- ✅ Topic clustering
- ✅ Basic search & filter
- ✅ User authentication
- ✅ Dashboard view

### Should-Have (P1) - Launch in 2-4 Weeks
- ✅ Learning path generation
- ✅ Intent-based search ("interview prep in 2 weeks")
- ✅ Save from Medium, YouTube
- ✅ Progress tracking
- ✅ Mobile-responsive

### Nice-to-Have (P2) - Post-Launch
- Strategic sparring partner AI
- Peer matching
- Save from all websites
- Mobile app
- Team features

---

## Research Evidence

Our product direction is grounded in user research:

**Validated Problem (3/3 students confirmed):**
> "When we go to LinkedIn, I save the post, and sometimes I never read it, but I want it because it was important." - Mike Vela

**Key Findings:**
- 80% of AI PM course students don't complete courses (content overload)
- Students can only digest 20-30% of materials
- Saved content goes unused (87 LinkedIn posts, 50 Medium articles typical)
- No systematic way to organize or retrieve when needed

**Framework:** Teresa Torres' Continuous Discovery Habits
- Outcomes → Opportunities → Solutions → Experiments
- Evidence-based decision making
- Continuous validation with users

📄 **Full opportunity map:** [Knowledge/Research/opportunity-map.md](Knowledge/Research/opportunity-map.md)

---

## Team & Collaboration

**Product Team:**
- **Steven Muñoz** - Technical lead, AI PM automation expert
- **Divya Sabade** - Product strategy, AI PM education specialist

**Collaboration Model:**
- Weekly sync calls (documented in `Knowledge/Meetings/`)
- Evidence-based decision making (research in `Knowledge/Research/`)
- Iterative development (4-week sprints to MVP)
- User validation throughout (continuous discovery)

**Initial Meeting:**
- Date: January 23, 2026
- Summary: [Knowledge/Meetings/2026-01-23_steven-divya-collaboration-kickoff.md](Knowledge/Meetings/2026-01-23_steven-divya-collaboration-kickoff.md)
- Outcome: Agreed on product vision, tech stack, MVP scope

---

## How to Use This Repository

### For Development Work
```bash
# Read project context
cat AGENTS.md

# Process backlog items
"Process my backlog and create tasks"

# Check priorities
"What should I work on today?"

# Research analysis
"Use the research-analyst agent to analyze [interview transcript]"
```

### For Meeting Notes
```bash
# After meetings with Divya or users
"Use the meeting-notes-distiller agent to summarize these meeting notes"
# Output saved to Knowledge/Meetings/YYYY-MM-DD-topic.md
```

### For Research Synthesis
```bash
# After user interviews
"Use research-analyst to create opportunity map from [interview notes]"
# Output saved to Knowledge/Research/
```

---

## Key Documents

| Document | Purpose | Location |
|----------|---------|----------|
| **Product Vision** | Collaboration kickoff summary | [Knowledge/Meetings/2026-01-23_steven-divya-collaboration-kickoff.md](Knowledge/Meetings/2026-01-23_steven-divya-collaboration-kickoff.md) |
| **User Personas** | 3 personas + journey maps | [Knowledge/Research/product-user-personas.md](Knowledge/Research/product-user-personas.md) |
| **Tech Stack** | Architecture + ASCII diagram | [Knowledge/Research/tech-stack-architecture.md](Knowledge/Research/tech-stack-architecture.md) |
| **Opportunity Map** | Research synthesis (Teresa Torres) | [Knowledge/Research/opportunity-map.md](Knowledge/Research/opportunity-map.md) |
| **Evidence Base** | Student research synthesis | [Knowledge/Research/ai-pm-learner-personas-synthesis.md](Knowledge/Research/ai-pm-learner-personas-synthesis.md) |
| **Agent Instructions** | AI behavior guidelines | [AGENTS.md](AGENTS.md) |
| **Project Goals** | Product goals & milestones | [GOALS.md](GOALS.md) |

---

## Agents Available

### 1. Meeting Notes Distiller
**Use when:** Processing raw meeting transcripts into structured summaries
**Output:** Organized notes with decisions, action items, stakeholder feedback
**Location:** `.claude/agents/meeting-notes-distiller.md`

**Example:**
```
"Use meeting-notes-distiller to process these meeting notes: [paste transcript]"
```

### 2. Research Analyst
**Use when:** Analyzing user research, creating opportunity maps, designing experiments
**Framework:** Teresa Torres' Continuous Discovery Habits
**Output:** Evidence-based opportunity maps with prioritized solutions
**Location:** `.claude/agents/research-analyst.md`

**Example:**
```
"Use research-analyst to analyze this user interview and update the opportunity map"
```

---

## Next Steps

### Immediate (This Week)
1. ✅ Project foundation setup
2. ✅ User personas defined
3. ✅ Tech stack selected
4. [ ] Competitive analysis (mymind.org, Notion, Readwise)
5. [ ] Feature prioritization with Divya
6. [ ] Firebase project setup

### Week 1-2: Foundation Sprint
1. [ ] Set up GitHub repo structure (monorepo: /extension, /web, /functions)
2. [ ] Firebase project + authentication
3. [ ] Chrome extension MVP (save from LinkedIn)
4. [ ] Basic web app (dashboard + list view)
5. [ ] Firestore schema implementation

### Week 3-4: Intelligence Sprint
1. [ ] Claude API integration (summarization)
2. [ ] Cloud Functions (onContentSaved, searchContent)
3. [ ] Pinecone vector database setup
4. [ ] Topic clustering implementation
5. [ ] Semantic search functionality

---

## Assumptions to Validate

**Critical Assumptions (Test First):**

1. **Will users save content consistently?**
   - Hypothesis: Users save 5+ items per week
   - Test: Track save frequency in beta (n=10 users, 2 weeks)
   - Risk: Low adoption if saving isn't habit

2. **Can AI summarization capture nuance?**
   - Hypothesis: 80%+ of key concepts captured accurately
   - Test: Show summaries to 10 users, measure accuracy
   - Risk: Users don't trust summaries, go back to original

3. **Do personalized learning paths work better than generic?**
   - Hypothesis: 2x higher completion rate vs generic paths
   - Test: A/B test personalized vs generic (n=20 users)
   - Risk: Personalization complexity not worth effort

4. **Will users actually follow intent-based paths?**
   - Hypothesis: 60%+ complete suggested "interview in 2 weeks" path
   - Test: Track path completion in beta
   - Risk: Users start path but abandon

---

## Competitive Landscape

**Similar Tools:**
- **mymind.org** - Content bookmarking (lacks AI summarization, learning paths)
- **Notion** - Knowledge management (not content aggregation focused)
- **Readwise** - Highlight management (reading-focused, not learning paths)
- **Instapaper/Pocket** - Read-it-later (no AI, no learning paths)

**Our Differentiator:**
- ✅ AI PM vertical focus (not general knowledge management)
- ✅ Intent-based learning paths ("interview in 2 weeks")
- ✅ Multi-source aggregation (LinkedIn, Medium, YouTube, etc.)
- ✅ AI-powered topic clustering
- ✅ Proficiency-aware content curation

---

## Success Metrics

### MVP (First 100 Users)
- **Activation:** 60%+ save 5+ items in first week
- **Engagement:** 40%+ use product 2x per week
- **Value:** 30%+ generate at least 1 learning path
- **Retention:** 50%+ return after 30 days

### Product-Market Fit Indicators
- Users save 10+ items per week consistently
- 70%+ complete generated learning paths
- NPS score 40+ (users actively recommend)
- Willingness to pay $10-15/month

---

## License

This project is under development by Steven Muñoz and Divya Sabade.

Foundation based on PersonalOS framework by Aman Khan (CC BY-NC-SA 4.0).

---

## Contact & Collaboration

**Project Repository:** https://github.com/stevenmunoz/personal-os-aipm-learner

**Team:**
- Steven Muñoz - [LinkedIn](https://www.linkedin.com/in/stevenmunoz/) - Technical Lead
- Divya Sabade - Product Strategy

**Status:** Active Development - Research & Design Phase

---

*Last Updated: January 23, 2026*
