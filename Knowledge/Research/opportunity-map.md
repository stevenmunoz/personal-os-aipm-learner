# Course Improvement Opportunity Map
## AI Product Playbook Course - TA Research Analysis

**Framework:** Teresa Torres' Continuous Discovery Habits
**Date:** October 24, 2025 (Updated)
**Analyst:** Steven Muñoz (TA)
**Evidence Sources:**
- Mike Vela student interview (Oct 20)
- Ricardo student interview (Oct 24)
- Course observation

---

## Desired Outcome

**Primary Outcome:** Increase student success rate (% who complete course with working project deployed)

**Supporting Metrics:**
- Time to first deployment (reduce from 2+ weeks to 1 week)
- Student engagement score (Slack activity, office hours attendance)
- Post-course confidence score (self-reported ability to build AI products)
- TA value perception (student feedback on TA helpfulness)

---

## Opportunity Tree

### 🎯 Outcome: Increase Student Success Rate

#### Opportunity 1: **Reduce Initial Barriers to Entry**
**Evidence Strength:** 🔴 High (Critical blocker - CONFIRMED across 2/2 students)
**Customer Quotes:**
- Mike: *"Getting started was the most difficult part... License setup and basic configuration created significant friction."*
- Ricardo: *"If there is technical stuff to set up before a section, just give me all the steps"*

**Impact:** Students drop out or lose momentum in Week 1 before learning begins

**Sub-Opportunities:**
1. **Pre-course technical setup is confusing and time-consuming**
   - Students arrive unprepared (Cursor, licenses, API keys, dependencies)
   - No troubleshooting guide for common issues
   - No pre-flight check to validate setup
   - **NEW (Ricardo):** Autonomous learners prefer written docs over live walkthroughs
   - **NEW (Ricardo):** Setup steps sent day-of are too late; need 2-3 days advance notice

2. **EU students face timezone barriers**
   - Course timing (7pm ET = midnight+ EU) causes mental exhaustion
   - EU office hours only available last 2 weeks (too late)
   - Async support not structured well enough

3. **Technical blockers have no clear resolution pathway** (NEW from Ricardo)
   - Students hit blockers and abandon projects (e.g., AI Trip Planner OpenAI issue)
   - No "known issues" documentation per project
   - No async debugging support
   - Students choose work priorities over course debugging

**Solution Experiments to Test:**

**Experiment 1A: Pre-Course Setup Week**
- **Hypothesis:** If students complete setup 1 week before course start, they'll arrive ready to learn
- **Test:** Send setup checklist + video walkthrough 1 week before next cohort
- **Measure:** % of students who join Week 1 with working environment
- **Effort:** Low (1 video + 1 checklist doc)
- **Expected Impact:** High (removes #1 blocker)

**Experiment 1B: Setup Office Hours**
- **Hypothesis:** Dedicated setup support session reduces Week 1 friction
- **Test:** Offer optional "Setup Support" session 2 days before Week 1
- **Measure:** Attendance rate + setup success rate
- **Effort:** Medium (1 hour TA time)
- **Expected Impact:** High

**Experiment 1C: EU-Friendly Async Track**
- **Hypothesis:** Better async support maintains EU student engagement
- **Test:** Create structured async learning path with async-first materials
- **Measure:** EU student completion rate vs. non-EU
- **Effort:** High (requires content restructuring)
- **Expected Impact:** Medium-High (affects 20-30% of cohort)

**Experiment 1D: Dual-Format Setup Materials (NEW from Ricardo)**
- **Hypothesis:** Offering both "Quick Start" and "Detailed Walkthrough" serves different learner types
- **Test:** Create two versions of setup docs (autonomous vs. guided learners)
- **Measure:** Student satisfaction with setup materials + preference data
- **Effort:** Medium (2x documentation work)
- **Expected Impact:** Medium-High (reduces friction for autonomous learners)

**Experiment 1E: Technical Blocker Triage System (NEW from Ricardo)**
- **Hypothesis:** Fast blocker support prevents project abandonment
- **Test:** #technical-help Slack channel + "Known Issues" docs + weekly blocker office hours
- **Measure:** Blocker resolution time + project completion rate
- **Effort:** Medium (requires ongoing TA time)
- **Expected Impact:** High (prevents dropoff like Ricardo's AI Trip Planner)

---

#### Opportunity 2: **Prevent "Going Too Deep Too Soon" Pattern**
**Evidence Strength:** 🟡 Medium (Mike experienced this, Ricardo did NOT - may be learner-dependent)
**Customer Quote (Mike):** *"Realized went way too deep before mastering fundamentals. Should focus on small, simple projects first."*
**Counterpoint (Ricardo):** Did NOT mention scope creep issues; abandoned AI Trip Planner due to technical blocker, not complexity

**Impact:** Some students get overwhelmed, stuck, or build nothing deployable
**Note:** This may affect guided learners (Mike) more than autonomous learners (Ricardo)

**Sub-Opportunities:**
1. **Students don't understand project scoping**
   - Start custom projects from scratch without baseline
   - Add too many features (scope creep: 5 sources → 50 sources)
   - Choose complex tech before mastering basics (web scraping vs. RSS)

2. **Course doesn't explicitly teach "start small" framework**
   - No guidance on when to leave baseline repo
   - No project sizing template
   - No examples of "good first projects"

3. **Students lack context management skills**
   - Give agents too much context upfront
   - Don't know when to start new chat sessions
   - Sessions get "contaminated" with old context

**Solution Experiments to Test:**

**Experiment 2A: Mandatory Baseline Week**
- **Hypothesis:** Requiring Week 1-2 baseline repo work builds confidence before custom projects
- **Test:** Add explicit instruction: "Don't start custom projects until Week 3"
- **Measure:** % of students who deploy working project by Week 2
- **Effort:** Low (add 1 slide + Slack reminder)
- **Expected Impact:** High

**Experiment 2B: Project Sizing Guide**
- **Hypothesis:** Template helps students scope appropriately
- **Test:** Create "Graduation Project Template" with scoped examples
- **Measure:** Student-reported confidence in scoping + project success rate
- **Effort:** Medium (create template + 3-5 examples)
- **Expected Impact:** High

**Experiment 2C: "Build 3 Before 1" Rule**
- **Hypothesis:** Portfolio of small projects beats one complex project
- **Test:** Teach: "Modify 3-5 existing projects before starting from scratch"
- **Measure:** # of deployed projects per student
- **Effort:** Low (add to curriculum messaging)
- **Expected Impact:** Medium-High

**Experiment 2D: Context Management Workshop**
- **Hypothesis:** Explicit teaching on context management prevents "contamination"
- **Test:** Add 15-min segment in Session 2: "How to manage agent context"
- **Measure:** Student-reported context management issues (before/after)
- **Effort:** Low (15 min content)
- **Expected Impact:** Medium

---

#### Opportunity 3: **Increase Peer Learning & Accountability**
**Evidence Strength:** 🟡 Medium (Observed gap, confirmed by student)
**Customer Quote:** *"I kind of wish I had conversations like this with you and with others in the course more."*

**Impact:** Students feel isolated, lack sounding board, struggle alone

**Sub-Opportunities:**
1. **Online format lacks in-person connection**
   - Students turn cameras off, play recordings later
   - Slack participation is surface-level
   - No structured peer interaction

2. **No built-in accountability structure**
   - Students with "too many ideas" build nothing
   - No check-ins on progress
   - Course ends without ongoing support

3. **Failure is hidden, success is showcased**
   - Students posture ("need to look like I know what I'm doing")
   - Real struggles not visible to cohort
   - Learning from failure opportunities missed

**Solution Experiments to Test:**

**Experiment 3A: Peer Accountability Pairs**
- **Hypothesis:** Pairing students creates accountability and peer learning
- **Test:** Opt-in pairing system, bi-weekly 30-min check-ins
- **Measure:** Pair participation rate + reported value
- **Effort:** Low (create matching system)
- **Expected Impact:** Medium-High

**Experiment 3B: "Failure Fridays" in Slack**
- **Hypothesis:** Showcasing failures normalizes struggle and increases learning
- **Test:** Weekly thread: "What broke this week + what I learned"
- **Measure:** Thread engagement + student sentiment
- **Effort:** Low (facilitate weekly thread)
- **Expected Impact:** Medium

**Experiment 3C: Weekly Async Progress Check-ins**
- **Hypothesis:** Lightweight check-ins maintain momentum
- **Test:** Weekly Slack post: "What I shipped this week (even if small)"
- **Measure:** Participation rate + # of deployed projects
- **Effort:** Low (TA facilitation)
- **Expected Impact:** Medium

**Experiment 3D: Post-Course Accountability Cohorts**
- **Hypothesis:** Ongoing support maintains engagement post-course
- **Test:** Monthly alumni check-ins (TA-facilitated)
- **Measure:** Alumni participation + continued project development
- **Effort:** Medium (1 hour/month TA time)
- **Expected Impact:** Medium

---

#### Opportunity 4: **Improve Observability Learning Depth**
**Evidence Strength:** 🟡 Medium (Student wish, not critical blocker)
**Customer Quote:** *"I didn't really get deep into it [observability], and that's something that I wish I'd been able to do more of."*

**Impact:** Students miss key differentiating skill for AI PM roles

**Sub-Opportunities:**
1. **Observability feels abstract without hands-on practice**
   - Students don't implement tracking in their projects
   - Arize setup but not deep usage
   - Hard to see value without real production issues

2. **Course pacing doesn't allow deep exploration**
   - Too much content, not enough practice time
   - Observability covered but not reinforced

**Solution Experiments to Test:**

**Experiment 4A: Observability Office Hours**
- **Hypothesis:** Dedicated support helps students implement tracking
- **Test:** Bi-weekly "Observability Deep Dive" office hours
- **Measure:** % of students with tracking in deployed projects
- **Effort:** Medium (1 hour every 2 weeks)
- **Expected Impact:** Medium

**Experiment 4B: "Add Observability to Your Project" Challenge**
- **Hypothesis:** Structured challenge drives hands-on implementation
- **Test:** Week 3 challenge: Add Arize tracking to existing project
- **Measure:** Completion rate + quality of implementation
- **Effort:** Low (create challenge prompt)
- **Expected Impact:** Medium-High

---

## Prioritization Matrix (Updated with Ricardo Insights)

| Opportunity | Impact | Evidence | Effort | Priority | Quick Win? | Status |
|-------------|--------|----------|--------|----------|------------|--------|
| **Blocker Triage System** (NEW) | High | High | Medium | 🔴 P0 | ❌ No | Ricardo AI Trip Planner |
| **Pre-Course Setup Week** | High | High | Low | 🔴 P0 | ✅ Yes | Mike + Ricardo |
| **Dual-Format Setup Docs** (NEW) | High | High | Medium | 🔴 P0 | ✅ Yes | Ricardo learner type |
| **Setup Office Hours** | High | High | Medium | 🔴 P0 | ✅ Yes | Mike + Ricardo |
| **Session Agenda Clarity** (NEW) | Medium | Medium | Low | 🟠 P1 | ✅ Yes | Ricardo only |
| **Mandatory Baseline Week** | Medium | Medium | Low | 🟠 P1 | ✅ Yes | Mike only (downgraded) |
| **Project Sizing Guide** | High | Medium | Medium | 🟠 P1 | ✅ Yes | Mike only |
| **"Build 3 Before 1" Rule** | Medium | Medium | Low | 🟠 P1 | ✅ Yes | Mike only |
| **Context Management Workshop** | Medium | Medium | Low | 🟠 P1 | ✅ Yes | Mike only |
| **Peer Accountability Pairs** | Medium-High | Medium | Low | 🟠 P1 | ✅ Yes | Mike only |
| **EU-Friendly Async Track** | Medium-High | High | High | 🟡 P2 | ❌ No | Mike only |
| **"Failure Fridays"** | Medium | Medium | Low | 🟡 P2 | ✅ Yes | No validation yet |
| **Weekly Progress Check-ins** | Medium | Medium | Low | 🟡 P2 | ✅ Yes | No validation yet |
| **Observability Office Hours** | Medium | Low | Medium | 🟡 P2 | ❌ No | Mike wished for more |
| **Post-Course Cohorts** | Medium | Low | Medium | 🟢 P3 | ❌ No | No validation yet |

**UPDATED PRIORITIES (Based on 2 Interviews):**
- 🔴 P0 Quick Wins: Blocker Triage + Dual-Format Setup + Pre-Course Materials
- 🟠 P1 High Value: Session Clarity + Scoping Guides (for guided learners)
- Note: "Going too deep" pattern may be learner-dependent (needs validation with Evelyn/Divya)

---

## Recommended Next Steps for Steven (TA Role)

### This Week (Immediate Actions):
1. ✅ **Document Mike insights** - COMPLETE
2. ✅ **Document Ricardo insights** - COMPLETE
3. **Create "Known Issues: AI Trip Planner" doc**
   - Document Ricardo's OpenAI output blocker
   - Add to prevent future students hitting same issue
   - Test fix before next cohort

4. **Create Dual-Format Setup Guide Prototype**
   - "Quick Start" version for autonomous learners
   - "Detailed Walkthrough" for guided learners
   - Test with current cohort

5. **Proactive Slack message to current cohort**
   - Announce: "#technical-help channel for blockers"
   - Promise: "TA response within 24 hours"
   - Encourage: "Post errors early, don't struggle alone"

### After Evelyn/Divya Calls:
6. **Synthesize patterns across all interviews**
   - Confirm: Setup friction universal? (2/2 so far)
   - Validate: "Going too deep" learner-dependent? (Mike YES, Ricardo NO)
   - Check: Session agenda clarity issue broader? (Ricardo mentioned)

7. **Pitch to Aman: Top 3 Quick Wins (UPDATED)**
   - **P0:** Technical Blocker Triage System (prevents dropoff)
   - **P0:** Dual-Format Setup Materials (serves all learner types)
   - **P0:** Pre-Course Setup Week (universal pain point)

### Next Cohort (Long-term):
6. **Implement Quick Wins**
   - Run experiments with next cohort
   - Measure impact on student success rate
   - Iterate based on data

7. **Build TA Value Proposition**
   - TA = Student success coach + Course optimizer
   - Demonstrate value through improved metrics
   - Position for expanded TA role

---

## TA Role Opportunities Identified

Based on this research, Steven can position himself for:

### **Opportunity 1: Student Success Coach**
- **What:** Proactive support to prevent common blockers
- **Evidence:** Students need accountability, scoping help, context management guidance
- **How:** Weekly check-ins, office hours, Slack presence
- **Value to Aman:** Higher completion rates, better student outcomes

### **Opportunity 2: Course Improvement Researcher**
- **What:** Continuous discovery with students to identify improvements
- **Evidence:** This research call revealed 4+ major opportunities
- **How:** Regular student interviews, synthesis, actionable recommendations
- **Value to Aman:** Data-driven course evolution, competitive advantage

### **Opportunity 3: Content & Materials Developer**
- **What:** Create templates, guides, and troubleshooting docs
- **Evidence:** Students need project sizing guides, setup checklists, context management tips
- **How:** Build reusable materials based on research insights
- **Value to Aman:** Scalable support, reduced TA burden over time

### **Opportunity 4: Community Builder**
- **What:** Facilitate peer learning and accountability
- **Evidence:** Students want more connection, Mike sought bi-weekly accountability
- **How:** Pair matching, Slack facilitation, alumni cohorts
- **Value to Aman:** Stronger community = higher retention + referrals

---

## Key Insights for TA Strategy

### Learner Personas Identified (NEW from Ricardo)

**Type 1: Autonomous Learner (Ricardo)**
- **Profile:** Technical background (CS degree), prefers independence
- **Needs:** Written docs, async flexibility, advanced resources
- **Support Style:** "Just give me the steps" - minimal hand-holding
- **Pain Points:** Live walkthroughs feel slow, setup delays frustrating
- **Value:** Fast blocker triage, pre-emptive documentation, peer connections

**Type 2: Guided Learner (Mike)**
- **Profile:** Can learn technical skills but benefits from structure
- **Needs:** Guardrails, explicit frameworks, step-by-step guidance
- **Support Style:** "Show me how" - appreciates demonstrations
- **Pain Points:** Going too deep without guidance, scope creep
- **Value:** Project sizing guides, accountability, context management tips

**TA Implication:**
- ONE-SIZE-FITS-ALL SUPPORT DOESN'T WORK
- Need dual-format materials (quick start vs. detailed)
- Need persona-aware office hours
- Both types benefit from: blocker triage, pre-course setup, clear agendas

---

### What Makes a TA Valuable (Synthesized from Mike + Ricardo):
1. **Anticipates blockers before they happen** (proactive vs. reactive)
2. **Provides fast async support** (Ricardo: 24-hour blocker responses)
3. **Serves multiple learner types** (autonomous vs. guided)
4. **Creates pre-emptive documentation** (setup guides, known issues)
5. **Provides structure when students feel lost** (scoping, prioritization)
6. **Teaches "meta-skills"** (context management, project scoping, not just tech)
7. **Normalizes struggle** (shares failures, not just successes)

### What Doesn't Work:
1. Waiting for students to ask questions (Ricardo abandoned AI Trip Planner)
2. Only answering technical questions (deeper issues are strategic)
3. One-size-fits-all support (autonomous learners frustrated by hand-holding)
4. Live walkthroughs only (autonomous learners want written docs)
5. No blocker escalation path (students will deprioritize course over work)
6. Focusing only on current cohort (post-course support extends value)

---

## Evidence Quality Assessment (Updated with Ricardo)

| Insight | Evidence Type | Confidence | Validation Status |
|---------|---------------|------------|-------------------|
| Initial setup is biggest barrier | 2/2 students (Mike + Ricardo) | 🔴 High | ✅ CONFIRMED |
| Technical blockers need triage system | Ricardo abandoned project | 🔴 High | ⏳ EMERGING (needs validation) |
| Learner personas require different support | Mike vs. Ricardo contrast | 🟡 Medium | ⏳ EMERGING (needs validation) |
| Students go too deep too soon | Mike only | 🟡 Medium | ❌ NOT CONFIRMED (Ricardo didn't mention) |
| Session agenda clarity issues | Ricardo only | 🟢 Low | ❓ UNKNOWN (needs validation) |
| EU timezone challenges | Mike only | 🟡 Medium | ❓ UNKNOWN (check cohort data) |
| Need for peer accountability | Mike only | 🟡 Medium | ❓ UNKNOWN (survey broader cohort) |
| Observability depth lacking | Mike only | 🟡 Medium | ❓ UNKNOWN (check other students) |
| Context management confusion | Mike only | 🟡 Medium | ❓ UNKNOWN (Ricardo didn't mention) |

**Key Takeaways:**
- ✅ CONFIRMED (2/2): Setup friction is universal pain point
- ⏳ EMERGING: Technical blocker support gap (Ricardo case study)
- ⏳ EMERGING: Learner personas hypothesis (needs more data)
- ❌ NOT UNIVERSAL: "Going too deep" may be learner-dependent

---

## Next Research Questions

**For Evelyn Call:**
- Did you experience setup friction in Week 1? (validate pattern)
- Learning style: prefer written docs or live walkthroughs? (test persona hypothesis)
- Did you hit any technical blockers? How did you resolve them? (validate blocker triage need)
- Session agenda clarity: did you know what to expect from each session? (validate Ricardo's feedback)
- Did you start with baseline repo or custom project? (test "going too deep" pattern)
- Observability: did you implement it? What made it click or not?

**For Divya Call (Nov 7):**
- Same questions as Evelyn (validate patterns)
- Evals-specific deep dive:
  - How did evals teaching land?
  - What made evals hard/easy?
  - Where did you need more support?
- Technical blockers: any abandoned projects or features?

---

## Meta-Reflection: Opportunity Mapping Process

**What worked well in this research:**
- Open-ended questions revealed unexpected insights (context management)
- Student felt comfortable sharing failures (built trust)
- 45-min format allowed depth without overwhelming

**What to improve:**
- Could have probed more on observability ("What would have made it click?")
- Missed asking about specific Session 3-4 experiences (evals)
- Should have asked about materials quality (videos, slides, docs)

**Application to TA work:**
- Use this framework for all student interviews
- Build opportunity map across all 4 research calls
- Present evidence-based recommendations to Aman
- Track experiments to measure TA impact

---

**Last Updated:** October 24, 2025 (After Ricardo call)
**Next Update:** After Evelyn and Divya calls

**Research Progress:**
- ✅ Mike Vela (Oct 20) - COMPLETE
- ✅ Ricardo (Oct 24) - COMPLETE
- 📅 Evelyn Chou - TBD
- 📅 Divya (Nov 7) - Scheduled
