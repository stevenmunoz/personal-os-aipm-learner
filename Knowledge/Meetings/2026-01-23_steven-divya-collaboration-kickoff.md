# Meeting Summary: Steven Munoz & Divya Sabade - AI PM Education Product Collaboration

**Date:** 2026-01-23
**Participants:** Steven Munoz, Divya Sabade
**Duration:** ~65 minutes

---

## SUMMARY

**Meeting Objective:** Initial connection call between Steven and Divya to discuss backgrounds, current work situations, and explore potential collaboration on an AI PM education product.

### Key Decisions

**Collaboration Confirmed**: Both parties committed to building an AI PM learning tool together, targeting a narrow use case for AI product management learners.

**Tech Stack Direction**: Firebase selected as primary backend infrastructure based on Steven's successful experience (serverless, Google-backed, extremely cost-effective at ~$1/month).

**Development Approach**: Two-week sprint model to build initial narrow-scope product, with focus on speed and iteration.

**Scheduling Pending**: Specific working sessions to be scheduled once Steven returns to Colombia (Sunday departure). Divya available Mon-Thu 1:30-4:30pm PT; Steven best on Monday evenings (7pm ET / 4pm PT) or weekends.

### Core Product Vision (Conditional Approval)

The team agreed to build a learning content aggregation and personalization tool specifically for AI PM learners that:
- Aggregates saved content from LinkedIn, Medium, YouTube, newsletters
- Uses LLM backend to auto-summarize and cluster content by topics
- Creates personalized learning paths based on user intent (e.g., "interview in 1 month," "learn agents in 3 days")
- Starts with extremely narrow scope solving one critical problem before expanding

### Requests/Requirements

**Pre-Work Before First Session:**
- Steven: Document personas from current AI PM courses, define 2-3 user archetypes with use cases
- Divya: Competitive analysis (starting with mymind.org), document bigger vision and core problem slice
- Both: Identify preferred tech stack components

**First Working Session Goals:**
- Duration: 1.5 hours minimum
- Agenda: Review persona research, finalize narrow problem definition, align on initial prototype scope
- Timing: TBD based on Steven's course schedule (next cohort starts following week)

---

## DETAILED NOTES

### Background & Current Situations

**Steven's Context:**
- Working with Ammon and Eric on compressed 2-week AI PM courses (intensive "think like Designer/Engineer/PM" format)
- Day job: PM at Writer (via Double Nines contractor) - traditional, well-established company with no AI conversations in roadmap planning
- Location: Based in Colombia, currently in New Jersey for holidays, returns Sunday. Travels quarterly to US (1-1.5 months)
- Tension: Day job delivers value but offers limited learning/growth opportunities; side work with AI courses provides the learning he seeks
- **Strategic Intent**: Looking to transition from traditional PM role toward building AI products full-time, potentially within 2026

**Divya's Context:**
- Just completed work with Product School (transitioning them from PM training to AI PM training for enterprises)
- Location: Bay Area (South Bay - Los Gatos/Mountain View/Sunnyvale area), PST timezone
- Currently evaluating: Full-time product role vs. continuing consulting with learning opportunities
- Completed Gemini's AI course (October cohort focused on evals, not as much cursor/code)
- **Learning Journey**: Intensive learning March-November 2025, took December break due to burnout, now restarting with strategic focus
- Personal constraints: Two young kids, weekdays 1:30-4:30pm PT most flexible, weekends require advance planning with spouse
- **Career Philosophy**: Seeking roles where she both provides value AND continuously learns; refuses "deliver-only" situations like previous 5-year stint at Deloitte

**Shared Observation on AI PM Education:**
Both noted massive drop-off rates in AI PM courses despite high enrollment. Steven observed that only 20-30% of cohort participants meaningfully engage with course content due to overwhelming day-to-day demands. This validated the core problem they want to solve.

### Product Concept Evolution

**Initial Brainstorming - Divya's Past Ideas:**
1. **Abandoned Idea (March 2025)**: Platform aggregating free AI resources (Deep Learning AI, Microsoft courses, etc.) with auto-created structured paths. Dropped due to market saturation on LinkedIn.
2. **Current Concept**: Content aggregation with intelligent extraction
   - Save LinkedIn posts, Medium articles, YouTube videos, newsletters
   - LLM backend auto-summarizes and creates topic clusters
   - Intent-based learning path generation (e.g., "interview in 1 month" → customized 30-day plan)
   - Pinterest-like browser extension for frictionless saving
   - Inspired by observing that valuable saved content never gets consumed

**Steven's Contribution - Tool Discovery:**
Introduced **mymind.org** as competitive reference:
- Browser extension for saving content from any platform
- Desktop app for centralized repository with visualization
- **Gap Identified**: mymind.org is just a "better notes app" - it centralizes but doesn't extract insights or create learning paths
- **Opportunity**: They have user data and content but aren't leveraging AI to transform saved content into actionable learning

**Synthesis - Agreed Direction:**
- Start with mymind.org-like aggregation but AI-native
- Focus exclusively on **AI PM learner persona** (not general productivity)
- Core innovation: Topic-based segmentation + intent-based extraction
- Example flow: User saves 50 LinkedIn posts about AI agents → system clusters by subtopics → user says "I have 3 days to learn agent basics" → system generates personalized 3-day curriculum from saved content
- **Critical Design Principle**: "So simple it's a no-brainer - if you're learning AI PM, you need this tool"

### Technical Infrastructure Discussion

**Steven's Tech Stack Recommendation: Firebase**
- Rationale: Google-backed, mature (years in market), extremely cost-effective
- Current costs: ~$1/month for full production app (PetHealth AI)
- Serverless architecture: No backend needed, cloud functions handle all logic
- Built-in features: GA4 analytics, experimentation framework, feature flags, offline support, tracing
- **AI Integration**: Native Google AI workflows, supports semantic search, embeddings
- Compared alternatives: Tried Superbase (newer competitor) but Firebase superior for speed and cost

**Other Tools Discussed:**
- **Evals Platforms**:
  - Weigh & Biases (race.ai): Good but difficult UX for datasets, labeling, navigation
  - **BrainTrust**: Simpler UX, better developer experience, more established
  - **Confident AI**: Newer startup, Eric uses it for Blue application, Steven recommends alongside BrainTrust
- **Design/Presentation**:
  - **Excalidraw** (formerly thought to be CorelDRAW): Web-based diagram/workflow tool similar to Figma but simpler
  - Used by Ammon/Eric extensively
  - Templates available, supports screenshots, links, simple visual storytelling
  - **Warning from Steven**: Easy to get lost in visual polish and forget the story - draft content first, polish later

**Development Philosophy:**
- Speed is critical, but must establish good workflow to avoid breaking things during iteration
- Steven plans to abstract successful patterns from PetHealth AI project
- Openness to consulting Eric for technical architecture advice when needed

### Persona & Market Positioning

**Target Persona Refinement Needed:**
Both agreed "AI PM learner" is still too broad. Steven identified diversity within cohorts:
- **Highly technical PMs**: Grasp concepts fast, comfortable with terminals and technical depth
- **Domain experts**: Strong PM skills but limited technical background
- **Complete beginners**: Never touched a terminal, need foundational technical concepts

**Next Steps on Personas:**
Steven committed to documenting 2-3 specific personas from current course participants with use cases. This will inform:
- Feature prioritization (which technical depth to target)
- Content complexity levels
- Onboarding flows

**Go-to-Market Strategy (Preliminary):**
- **Beta Testing**: Leverage AI community (Ammon's course chat, existing networks)
- **Course Creator Partnerships**: Offer free tool to platforms like Product School to embed with students
- **Validation Metrics**: Focus on usage patterns - which features get traction, what topics are most saved/extracted
- **Geographic Opportunity**: Divya mentioned Google Garage events and Bay Area startup ecosystem for potential demo opportunities, free credits
- **Content Marketing**: Both have writing platforms (Divya on Medium, considering Substack migration) to document build journey
- **Timing**: Don't expose product publicly until it's stable with 5+ users successfully using it

### Collaboration Dynamics & Working Agreement

**Skill Complementarity:**
- **Steven's Strengths**: Technical execution, rapid prototyping, infrastructure setup, Firebase/AI tooling expertise
- **Divya's Strengths**: Strategic vision, market analysis, long-term thinking, product positioning, user research
- **Mutual Learning Commitment**:
  - Steven wants to learn strategic/market thinking from Divya
  - Divya insists on learning technical depth - "if it breaks tomorrow, I want to fix it myself"
  - Both emphasized "give and take" philosophy

**Work Style Alignment:**
- **Divya's Requirement**: "I need someone really interested - not one day on, one day off. Get it out, get it done."
- **Steven's Commitment**: "I'm super committed. This is my life project direction - moving from traditional company to building products I own."
- **Shared Philosophy**: Both prioritizing learning + impact over pure financial optimization at this career stage

**Logistics:**
- **Steven's Availability**:
  - Weekdays: Monday evenings best (7pm ET / 4pm PT)
  - Weekends: Saturday/Sunday mornings wide open, uses weekends for side projects
  - Constraints: Day job + night sessions with Ammon/Eric reduce weekday flexibility
- **Divya's Availability**:
  - Weekdays: Mon-Thu 1:30-4:30pm PT highly available
  - Weekends: Requires advance coordination due to childcare (two young kids), but can reserve time with notice
  - Note: Often works 3am-7am PT for deep focus work when needed

**Proposed Workflow:**
1. Offline async work on personas, competitive analysis, tech stack research
2. First synchronous session: 1.5+ hour workshop to align on problem definition and initial prototype
3. Weekend workshop (once Steven returns and settles): Longer session (morning) to build initial version together
4. Ongoing: Mix of async work with periodic sync checkpoints (weekly or bi-weekly)
5. Potential: In-person collaboration when Steven visits Bay Area (estimated 2-3 months out, post-next cohort)

### Strategic Context & Motivations

**Steven's Career Trajectory:**
- Recognizes current role is "incremental changes" with no AI exploration (blocked by security/process)
- Side work with Ammon/Eric provides the innovation exposure his day job lacks
- 2026 goal: Position for transition away from contractor model toward product ownership
- Not rushing the change, but actively building runway through skill development and side projects
- Views this collaboration as potential path to full-time product work

**Divya's Career Trajectory:**
- Transformative 2025: Extensive learning led to multiple opportunities
- Deliberately taking time to choose next move rather than rushing into another role
- Got to final rounds with Meta (November, currently on hold post-December freeze)
- Prioritizing: "It's not about money now, it's about doing and getting things done"
- Wants either: (1) hardcore AI agent work at big/small company, or (2) joyful work that provides continuous learning
- Open to consulting as sustainable model if it includes learning component

**Shared Vision:**
Both see AI PM education space as massive opportunity with clear unmet needs. Ammon reportedly told Steven "the AI PM education space is huge" - validating their focus area. They're positioning this as a "learning by building" initiative that could evolve into a sustainable product/business.

---

## FINAL ALIGNMENT CHECK

### Confirmed Requirements

**Product Scope (Non-Negotiable):**
- Must support topic-based content segregation from multiple sources
- Must enable intent-based extraction ("I have X days to learn Y")
- Must start with extremely narrow use case (one critical problem) before expanding
- Must be AI PM learner-specific (not general productivity tool)

**Technical Requirements:**
- Backend must scale efficiently and cost-effectively
- Firebase confirmed as starting point unless research reveals blocking issues
- Must support fast iteration cycles (two-week sprint to initial prototype)
- Architecture should be modular enough to avoid "breaking everything" during iterations

**Collaboration Requirements:**
- Both parties commit to teaching/learning across strategic and technical domains
- Work sessions must be scheduled with mutual availability (not ad-hoc)
- Pre-work completed before synchronous sessions to maximize live collaboration value
- No public exposure until product is stable with initial user validation

### Pending Decisions

**Scheduling:**
- Specific dates for first 1.5-hour alignment session (waiting on Steven's course schedule confirmation)
- Weekend workshop timing (post-Steven's return to Colombia)
- 4-6 week working cadence to be documented in shared tracker

**Product Definition:**
- Final persona selection (awaiting Steven's research from current cohorts)
- Exact scope of MVP (which single problem to solve first)
- Success metrics for initial validation phase

**Technical Architecture:**
- Specific Firebase services to leverage (authentication, storage, cloud functions, etc.)
- LLM provider selection (Google AI native vs. other options)
- Data pipeline design for content ingestion from multiple sources

### Follow-Up Actions

**Immediate (Before First Session):**
1. **Steven**:
   - Confirm availability and schedule first session
   - Document 2-3 user personas from AI PM course participants with use cases
   - Research and propose tech stack components in shared doc
2. **Divya**:
   - Complete competitive analysis (starting with mymind.org deep dive)
   - Document full product vision in shared doc
   - Identify the "one critical problem" to solve in MVP
3. **Both**:
   - Review and comment on each other's pre-work
   - Come to first session with specific questions/discussion points

**First Session Agenda:**
- Review persona research and select target user
- Align on narrow problem definition and MVP scope
- Discuss tech stack and validate Firebase approach
- Define success criteria for initial prototype
- Distribute work for first two-week sprint

**Medium-Term (2-3 Months):**
- Potential in-person collaboration session in Bay Area when Steven travels
- Explore Bay Area startup events (Google Garage, etc.) for exposure opportunities
- Build initial user base within AI course communities for feedback

**Long-Term (Conditional):**
- If product gains traction, both open to transitioning to full-time focus
- Explore course creator partnerships (Product School, etc.) for distribution
- Consider content marketing strategy via Medium/Substack to build audience

---

## Key Insights & Context for Future Reference

**Market Timing:**
The massive growth in AI PM education (Divya noted 5-6 courses last year, now 15+ courses) combined with low completion rates creates urgency. The "explosion" of content is simultaneously the problem (overwhelming learners) and the opportunity (abundant content to aggregate/organize).

**Competitive Landscape:**
Tools like mymind.org prove the content aggregation model works, but they're solving general productivity rather than vertical-specific learning. The gap between "saving content" and "learning from content" is the white space this product targets.

**Risk Factors:**
- Both have competing time commitments (Steven's day job + course TA work; Divya's job search + family)
- Weekend-only development could slow momentum
- Scope creep risk given both parties' big-picture thinking - must maintain discipline on narrow MVP

**Success Factors:**
- Both bring deep domain expertise in AI PM education space
- Complementary skill sets reduce single-point-of-failure risk
- Shared learning philosophy ensures both parties stay motivated
- Access to built-in user base (AI course communities) for rapid validation
- Low infrastructure costs (Firebase ~$1/month) enable sustainable experimentation

**Cultural Fit Signals:**
- Both emphasized "give and take" unprompted
- Both rejected purely transactional work arrangements
- Both comfortable with ambiguity and iteration
- Both demonstrated strategic patience (not rushing to market)
- Both willing to teach/learn across domains

This collaboration has strong fundamentals: clear problem, complementary skills, aligned values, and built-in market access. The main execution risk is time management given competing commitments, which the structured workflow aims to mitigate.
