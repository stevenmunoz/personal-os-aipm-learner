# Evelyn Chou Research Call - Course Improvement Feedback

**Date:** Monday, October 21, 2025 (3:00pm)
**Duration:** ~38 minutes
**Participant:** Evelyn Chou (Previous cohort student)
**Current Role:** Building on-premise AI data agent
**Purpose:** Gather course feedback + personal OS guidance for work project
**Related:** Tasks/Aman/research-evelyn-call-prep.md

---

## Context: Evelyn's Current Work

**Product:** On-premise AI data agent
**Deployment Model:** Windows + Linux installers (not cloud-based)
**Target Customer:** Mid-sized companies with data scattered across multiple sources
**Key Challenges:**
- Complex deployment (on-premise vs. cloud)
- Data integration from multiple sources
- Data semantics understanding (joining, cleaning, deduplication)
- Identifying field meanings (e.g., 8-digit number = user ID or SSN?)

**Learning Goal:**
> "I feel it's much faster if I just redo my personal OS, redo the course content to learn about observability and tools. That's faster than trying to implement directly on work project."

**Key Insight:** Evelyn recognizes value of starting with personal OS as sandbox before tackling complex work implementation.

---

## Key Pain Points Identified

### 1. **Database & Data Sources (Not Covered in Course)**
**Severity:** High (for Evelyn's use case)
**Impact:** Gap between course content and work needs

**Evelyn's Feedback:**
> "For my work, the data agent I'm building interacts with various data sources quite often, and that's not something I felt we went very deep in Aman's course."

**What's Missing:**
- Database integration patterns (Supabase, Firebase, Redshift, etc.)
- Multi-source data retrieval strategies
- Schema understanding and context injection
- Data semantics for AI agents
- Tool design for database interactions

**What Evelyn Needs:**
- How to build tools that fetch from databases
- How to inject DB schema/context into prompts
- How to handle multi-source data workflows
- Data cleaning and semantic understanding patterns

**Recommendation for Aman:**
- Add "Database Integration" module (Week 3 or 4)
- Cover Supabase/Firebase basics
- Teach RAG patterns for database context
- Show tool design for data retrieval workflows
- Include example: Multi-source data agent

---

### 2. **Understanding Personal OS Structure**
**Severity:** Medium
**Impact:** Confusion about MD file organization

**Evelyn's Questions:**
- "Are those individual MD files system prompts or agents?"
- "What's the difference between skills, agents, and slash commands?"
- "How do you separate source-of-truth files (human-created) vs. AI-generated files?"

**What Caused Confusion:**
- Many MD files in screenshots without clear explanation
- Folder structure not immediately intuitive
- Overlap between agents, skills, slash commands unclear
- Source of truth vs. generated content distinction

**What Helped (from call):**
- **Knowledge/ folder** = Source of truth (context you feed in)
- **Tasks/ folder** = AI-generated task files from backlog processing
- **Agents** = Multi-step reasoning prompts (e.g., research analyst agent)
- **Slash commands** = Reusable formatting/response templates
- **Skills** = Specialized capabilities

**Recommendation for Aman:**
- Add "Personal OS Architecture" explainer early in course
- Diagram showing: Knowledge → Tools → Agent → Tasks workflow
- Clearly distinguish: Context files vs. Generated files
- Explain when to use agents vs. skills vs. slash commands
- Show folder structure with annotations

---

### 3. **Tools & Workflow Design Philosophy**
**Severity:** Medium
**Impact:** Students don't know how to choose tools or design workflows

**Evelyn's Question:**
> "For the sake of starting all over again, I don't even know what tools I need to call and I don't have Aman's repo. How do you even decide which tools to use?"

**Challenge:**
- Students see Aman's trip planner with pre-built tools
- Don't understand the *thinking process* behind tool selection
- Unclear how to design tools for new use cases
- Don't know when tools are needed vs. when they're overkill

**Steven's Answer (valuable teaching content):**
> "In terms of which tools you should use or not, it depends. It depends on the flow. You start designing these tools specifically for what you want to achieve. How can we use AI to provide a great user experience?"

**Key Teaching Points from Call:**
1. **Tools = Enabling great UX** (not technical for sake of technical)
2. **Start with workflow** (what does user need to accomplish?)
3. **Design tools backwards from UX** (what context does agent need?)
4. **Ask agent to help design tools** (don't build alone)
5. **Iterate incrementally** (start simple, add complexity)

**Recommendation for Aman:**
- Add "Tool Design Thinking" lesson/section
- Framework: User workflow → UX goal → Required context → Tool design
- Show examples: Bad tool design vs. Good tool design
- Teach: When to build custom tools vs. use existing
- Exercise: Students map their workflow and design 1-2 tools

---

## Positive Feedback & What Works

### 1. **Personal OS as Learning Sandbox**
**What Works:**
- Safe local environment for experimentation
- Real use case (managing own tasks/context)
- Immediate value (helps with daily work)
- Foundation for understanding MCPs and tools

**Evelyn's Reaction:**
> "I really like starting over with personal OS. It makes sense."

**Why It Works:**
- Students can experiment without breaking anything
- Personal context makes learning relevant
- Incrementally expandable (start simple, add complexity)
- Transfers to work projects later

**Recommendation for Aman:**
- Double down on Personal OS as primary sandbox
- Encourage students to start here before custom projects
- Use Personal OS to teach: MCPs, tools, context management, agents
- Position as "learning laboratory" not just task management

---

### 2. **Steven's Teaching Approach (Insights for Aman)**

**What Evelyn Valued:**
- **Explanations with examples** (showed actual files, walked through flows)
- **Contextual teaching** (connected concepts to her work needs)
- **Patient deep-dives** (took time to answer questions thoroughly)
- **Practical guidance** ("Start with Personal OS, then iterate")
- **Offer for working sessions** ("Let's troubleshoot together once you have something")

**Evelyn's Comment:**
> "This has been so helpful. Thank you so much, Steven."

**Why This Worked:**
- 1:1 attention allowed tailored explanations
- Real examples from Steven's own projects
- Connected dots between course concepts and real applications
- Offered ongoing support beyond single call

**Recommendation for Aman:**
- Consider adding "Student Project Office Hours" beyond Q&A
- Pair students with peers for troubleshooting sessions
- Create library of "common pattern explanations" (like Steven's DB/RAG explanation)
- Encourage TAs to offer 1:1 working sessions

---

## Learning Journey Insights

### Evelyn's Current State:
**Has Done:**
- ✅ Completed course (previous cohort)
- ✅ Started Supabase account (but not used yet)
- ✅ Began rebuilding climbing agent (switched from home care project)

**Hasn't Done Yet:**
- ❌ Implemented observability deeply
- ❌ Deployed agent to Render
- ❌ Connected Supabase to agent
- ❌ Built database integration tools

**Blockers:**
- Too complex initial project (home care agent)
- Insufficient domain knowledge to judge hallucinations
- Unclear how to implement database patterns from course

**What Changed (Smart Pivot):**
- Switched to climbing agent (domain she knows well)
- Better positioned to judge agent performance
- More passion for the domain
- Right level of complexity for learning

**Recommendation for Aman:**
- Encourage students to pick domains they know deeply
- Warning: "If you can't judge hallucinations, pick different domain"
- Guide project scoping based on student's expertise
- Celebrate smart pivots (not project abandonment)

---

## Evelyn's Project: Climbing Agent

**Why This Is Better:**
- ✅ Evelyn climbs weekly (domain expertise)
- ✅ She's working on projects (real use case)
- ✅ Right complexity level (not too simple, not overwhelming)
- ✅ She can judge performance (knows when agent hallucinates)

**Comparison to Previous Project (Home Care):**
- ❌ Too technical (insufficient knowledge)
- ❌ Can't judge accuracy (no domain expertise)
- ❌ No personal connection (less motivation)

**Next Steps for Evelyn:**
1. Deploy climbing agent to Render
2. Work with Steven on troubleshooting session
3. Add database integration (climbing projects, routes, progress)
4. Implement tracing in Arize
5. Build evaluation framework

**Value for Course:**
- Good example of smart project scoping
- Shows importance of domain knowledge
- Demonstrates learning by iteration

---

## Database Integration Deep Dive (Teaching Opportunity)

### Steven's Explanation (Captured from Call):

**Key Concepts Explained:**

**1. Backend Services (Supabase/Firebase) = Persistence Layer**
> "Supabase is solving all the server-side piece for you. You have tables, you can deploy it, see it anywhere in the world."

**2. RAG Pattern = Retrieval Augmented Generation**
> "It's a super fancy word, but in essence, it is: How can I provide the right context to the agent? It can be a database call passed as part of the prompt."

**3. Tool Design for DB Retrieval:**
> "Every time the user opens the chat, I need tools that allow the agent to fetch information from DB, retrieve context, then inject into prompt."

**4. Personalization Through Context:**
> "The agent went into DB, pulled information, injected into prompt, now it knows how to respond with the right context to user's questions."

**5. Schema Understanding:**
> "Give the agent an idea of how DB is structured, what the fields are, the length, the restrictions. Agent can now validate: 'This field should be 8-digit character, you're entering something different.'"

**Flow Diagram (Teaching Material):**
```
User Question
    ↓
Agent Triggered
    ↓
Tool: Fetch DB Context (pet records, schema, constraints)
    ↓
Inject Context into Prompt
    ↓
Agent Responds with Personalized Answer
```

**Recommendation for Aman:**
- Create dedicated lesson: "Building Database-Connected Agents"
- Use this exact flow as teaching framework
- Live demo: Supabase setup → Schema design → Tool creation → Context injection
- Exercise: Students build simple DB-backed agent
- Show both read and write operations
- Cover schema validation and data semantics

---

## Course Improvement Recommendations (Prioritized)

### 1. **Add "Database Integration" Module** (High Value)
**Problem:** Gap between course content and real-world agent needs
**Solution:**
- New lesson or extended section (90 minutes)
- Topics:
  - Supabase/Firebase basics (setup, tables, connections)
  - RAG pattern for database context
  - Tool design for data retrieval
  - Schema injection and validation
  - Multi-source data workflows
- Live demo + hands-on exercise
- Example project: Simple CRUD agent with DB backend

**Impact:** High — Bridges theory to practice, enables work applications

---

### 2. **"Tool Design Thinking" Framework** (High Value)
**Problem:** Students don't know how to choose/design tools
**Solution:**
- Teaching framework:
  1. Start with user workflow (what needs to happen?)
  2. Define UX goal (what makes experience delightful?)
  3. Identify required context (what does agent need to know?)
  4. Design tools backwards (how do we get that context?)
- Examples of good vs. bad tool design
- Decision tree: When to build custom vs. use existing
- Exercise: Map workflow → Design tools

**Impact:** High — Core skill for building production agents

---

### 3. **Personal OS Architecture Explainer** (Medium Value)
**Problem:** Students confused by folder structure and file types
**Solution:**
- Visual diagram of Personal OS architecture
- Clearly label: Knowledge (input) vs. Tasks (output)
- Explain: Agents vs. Skills vs. Slash Commands
- Show: Source of truth (human) vs. Generated (AI)
- Annotated folder structure walkthrough

**Impact:** Medium — Reduces confusion, accelerates onboarding

---

### 4. **Project Scoping Guidelines** (Medium Value)
**Problem:** Students pick projects outside their expertise
**Solution:**
- "Can you judge hallucinations?" test
- Domain expertise requirement
- Complexity assessment framework
- Smart pivot examples (like Evelyn's climb agent)
- Warning signs: Too technical, too broad, no expertise

**Impact:** Medium — Prevents project abandonment, increases success rate

---

## Quotes and Key Insights

### On Choosing Personal OS:
> "I feel it's much faster if I just redo my personal OS to learn about observability and tools. That's faster than trying to implement on work project."

### On Database Integration Gap:
> "For my work, the data agent interacts with various data sources quite often, and that's not something I felt we went very deep in Aman's course."

### On Steven's Teaching:
> "This has been so helpful. Thank you so much, Steven. I'm sure I'll have other questions."

### On Smart Project Pivot:
> "I started rebuilding my agent to be a climbing agent because the direction I picked (home care) was too technical. I don't have sufficient knowledge to judge if it's hallucinating. But I climb every week and work on projects, so I can judge performance."

---

## Comparison with Mike Vela Feedback

### Common Themes:
1. **Starting simple matters** (Both struggled with complexity)
2. **Personal OS is valuable** (Both found it useful for learning)
3. **Domain expertise critical** (Both realized importance of knowing domain)
4. **Need more structure** (Both would benefit from clearer guidelines)

### Different Pain Points:
| Mike | Evelyn |
|------|--------|
| Timezone challenges (EU) | Database integration gaps |
| Going too deep too soon | Tool design thinking |
| Initial setup friction | Personal OS architecture confusion |
| Needed EU office hours earlier | Needed DB/data source guidance |

### Different Projects:
| Mike | Evelyn |
|------|--------|
| Morning news brief (over-scoped) | Home care agent → Climbing agent |
| Learned to start smaller | Learned to pick known domain |
| Building portfolio approach | Using Personal OS as sandbox |

---

## Next Steps with Evelyn

**Agreed to working sessions:**
- Wait until climbing agent deployed to Render
- Troubleshooting session with Steven
- Connect Supabase and implement DB patterns
- Add tracing to Arize
- Share progress and learnings

**Evelyn's Immediate Focus:**
1. Clone Personal OS and start using locally
2. Continue building climbing agent
3. Deploy to Render when ready
4. Schedule working session with Steven

**Potential Value for Course:**
- Evelyn's climbing agent could be case study
- Her DB integration needs represent real PM work
- Smart pivot example for future students

---

## Action Items for Steven (TA Work)

### Immediate (This Week):
- [x] Capture Evelyn transcript and feedback
- [ ] Compare with Mike and Ricardo insights (Ricardo call Friday)
- [ ] Draft "Database Integration" lesson outline for Aman

### For Current Cohort (Week 2+):
- [ ] Share "Tool Design Thinking" framework in Slack
- [ ] Create Personal OS architecture diagram
- [ ] Proactively guide students on project scoping

### For Next Cohort:
- [ ] Work with Aman on DB integration module
- [ ] Create annotated Personal OS walkthrough
- [ ] Develop tool design exercise

---

## Meta-Notes (For Synthesis Across Calls)

**Patterns to Watch:**
1. ✅ Is database integration a common gap? (Evelyn: YES, critical for work)
2. ✅ Do students struggle with tool design? (Evelyn: YES, doesn't know where to start)
3. ✅ Is Personal OS architecture confusing? (Evelyn: YES, many questions)
4. ✅ Do students need project scoping help? (Evelyn: YES, pivoted from home care)

**Questions for Ricardo (Friday):**
- Did you integrate databases in your project?
- How did you decide which tools to build?
- Did you start with Personal OS or custom project?
- Any confusion about Personal OS structure?
- How did you scope your project complexity?

---

**Research Call Status:**
- ✅ Mike Vela (Oct 20) - COMPLETE (EU timezone, going too deep)
- ✅ Evelyn Chou (Oct 21) - COMPLETE (DB integration, tool design)
- 📅 Ricardo (Oct 24, Friday) - SCHEDULED
- 📅 Divya (Nov 7, 4:00pm) - SCHEDULED (Evals focus)

**Next Step:** Complete Ricardo call, then synthesize all insights into comprehensive course improvement recommendations.

---

## Steven's Teaching Insights (For Self-Improvement)

**What Worked in This Call:**
- ✅ Screen sharing Personal OS (visual + explanation)
- ✅ Walked through actual files and folders
- ✅ Connected concepts to Evelyn's work needs (data agent)
- ✅ Explained RAG/DB patterns clearly
- ✅ Offered working session for hands-on help
- ✅ Encouraged smart project scoping (climbing vs. home care)

**What Could Improve:**
- Could have asked more about *her* blockers first
- Could have dug deeper into observability gap
- Could have explored what she tried vs. what worked
- Could have asked about other course pain points

**For Next Calls (Ricardo, Divya):**
- Start with open-ended: "What were your biggest challenges?"
- Ask: "What did you try that didn't work?"
- Probe: "What topics do you wish we covered more deeply?"
- Explore: "What would you change about the course structure?"
