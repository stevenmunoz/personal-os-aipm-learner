# Strategic Planning Document: AI PM Learning OS
**Date:** February 13, 2026
**Authors:** Steven Muñoz & Divya Sabade
**Source:** Steven_Divya Collab.pdf

---

## Brainstorming/Notes

### Onboarding:
- What's the **AHHA moment** + Emotional connection + Feeling (App)
- **Option 1:** Import (history? Extension?) + Goal/Intent? || **Option 2:** What to do if we can't → Pre curated content?

### Design System:
- Save image (go full screen)
- Prompt for design system
- Component/design library
- **Analogy:** Graph Nodes → Tree? Water Jug?
- LinkedIn login? Google/Apple login?
- **Chrome Extension Full Page:** https://chromewebstore.google.com/detail/gofullpage-full-page-scre/fdpohaocaechififmbbbbbknoalclacl?hl=en

### Prototypes:
- https://finance-tracker-27760.web.app/dashboard/concepts
- https://screen.studio/share/XHkGVKwg

---

## MyMind - Competitive Analysis

**URL:** https://mymind.com/

### Core JTBD
Save things, Automatically organize, Beautifully browse later, Feel calm about your digital life

### Key User Flows

**A. Capture Flow [Removes organization burden]**
- **Trigger:** User sees something interesting
- **Action:** Save via browser extension
- **Backend:** Auto-tagging → Image + text recognition → AI categorization → No folders required

**B. Browse / Rediscover Flow [Retrieval is aesthetic, Discovery feels exploratory → No performance pressure]**
- Users: Scroll visually (Pinterest-style grid) → Filter by auto-generated tags → Search semantically

**C. Emotional Experience**

The UX is:
- Soft gradients
- Creams + muted dark tones
- Rounded cards
- Large spacing
- No sharp productivity dashboard vibes
- No metrics
- No streaks
- No "optimize your life" pressure

---

## What MyMind Does NOT Do (This Is Where We Win)

MyMind does NOT:
- ✗ Turn saved content into structured learning
- ✗ Build time-boxed curricula
- ✗ Optimize for performance
- ✗ Prepare you for interviews
- ✗ Detect knowledge gaps
- ✗ Track explanation ability
- ✗ Force recall
- ✗ Create skill transformation loops

### Where It Overlaps With Us

Overlap layer:
- Content ingestion
- Auto clustering
- Semantic search
- LLM-based categorization
- Zero manual tagging

**If we position as:**
> "Better MyMind for AI PMs"

**We lose.**

Because they:
- Are broader
- Are more aesthetic
- Already polished
- Funded
- Have brand moat

**So we must avoid the "content organization tool" trap.**

---

## How It Relates to Our Idea

Your product (from the PDF) is not about saving.

**It's about:** Turning saved knowledge into interview-ready and build-ready capability.

That is a different game.

Let's contrast clearly:

| Dimension | MyMind | Our AI PM Learning OS |
|-----------|--------|----------------------|
| Core Outcome | Calm digital memory | Interview + build performance |
| Emotional State | Peace | Urgency under time pressure |
| Structure | Organic clustering | Intent-driven curriculum |
| Return Trigger | Rediscovery | Tomorrow's learning task |
| Measurement | None | Recall, explanation, gaps |
| Persona | Creators / thinkers | AI PM under pressure |

**This is critical:**
- MyMind is **ambient memory**.
- We must be **goal-driven transformation**.

---

## UX Lessons We Should Steal

✔ **Zero Manual Tagging**
Users hate organization labor.

✔ **Beautiful Simplicity**
No cluttered dashboards.

✔ **AI-first organization**
Clustering invisible.

✔ **Emotional clarity**
The product feels calm.

---

## UX Direction We Should NOT Copy

We should NOT:
- Be Pinterest-style browsing
- Be "inspiration discovery"
- Be generic content moodboard
- Emphasize aesthetic over progress

**We are not:** A memory.

**We are:** A training system.

That means our UI likely needs:
- Today's focus card
- Time remaining countdown
- Active learning mode
- "Explain this concept"
- Progress toward interview readiness

Much more structured.

---

## Strategic Insight

MyMind optimizes for: **"I'll want this someday."**

**Your ICP optimizes for: "I need this in 21 days."**

Time pressure changes everything.

Under time pressure:
- Browsing dies
- Curriculum matters
- Relevance matters
- Gaps matter
- Practice matters

**That is our wedge.**

---

## Our Strategy

### 1. Performance infrastructure, not just storage
   a. Force recall
   b. Explanation score
   c. Gap detection
   d. Concept dependency graph
   e. Application prompts
   f. Interview simulation (MVP??)
   g. Skill readiness score [Attempt → Fail → Diagnose → Improve → Reattempt]

### 2. We own a narrow but painful moment
Ex: Pass AI PM interview in 30 days (**vertical** not horizontal)
Integrations (Later?)

### 3. We focus on learning graphs not just clusters [Cognitive Infra]
   a. Extract canonical concepts
   b. Identify pre-req
   c. Track mastery per node
   d. Detect missing foundations
   e. Adjust plan dynamically

### 4. We measure capability, not consumption (Personal AI readiness score)
   a. Explainability quality
   b. Response latency
   c. Concept retention decay
   d. Cross concept linking ability

---

## We become defensible when:

1. We narrow to <AI PM under time pressure>?
2. We build recall + evaluation loops.
3. We own the <interview readiness> metric.
4. It becomes painful to remove once set up.
5. We transform saved content into measurable skill.

---

## MVP Scope (Strict)

### We build:
- Narrow ingestion (LinkedIn posts + web articles)
- Auto concept extraction
- 14-day interview plan
- Daily recall + explanation loop
- Readiness signal

### We don't build:
- YouTube ingestion (too complex)
- Multi-goal modes
- Community
- Broad personas
- Aesthetic browsing
- Full concept graph

---

## MVP Flow [Persona - AI PM skillup?]

**Step 1:** Signup
↓

**Step 2:** Define Goal + Timeline
↓

**Step 3:** Save 10–20 articles via extension
(Friction: LinkedIn? Chrome history? Curated content?)
↓

**Step 4:** System builds 14-day plan
↓

**Step 5:** Daily:
- Review concept summary (2 min)
- Explain concept
- Get feedback
- Answer follow-up
↓

**Step 6:** Readiness score updates
↓

**Step 7:** Plan adapts

---

## MVP Back End

- Content ingestion → cleaned text
- LLM summarization → canonical structured output
- Topic extraction (fixed AI PM taxonomy)
- Vector store (Pinecone / Supabase pgvector)
- Prompt-based evaluation engine
- Simple scoring heuristic
- Lightweight concept tracking table

---

## Key Prototype Screenshot: AI PM Learner Extension

The extension shows:
- **Auto-tagging example:** #LLM, #Foundation-Models, #Transformers, #Fine-Tuning
- **Learning path dropdown:**
  - ✓ Interview Prep - AI Systems
  - RAG & Vector Databases
  - AI Product Strategy
  - Agent Architecture Deep Dive
- **Action button:** "Save & Summarize"
- **Navigation:** Library (1) | My Progress | Ask AI

This demonstrates the core value prop: intelligent auto-categorization + learning path assignment in a single save action.
