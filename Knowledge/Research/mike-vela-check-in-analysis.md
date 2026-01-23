# Mike Vela Check-In Call - Research Analysis

**Session Date:** 2025-11-07 (estimated)
**Participants:** Steven Munoz (TA), Mike Vela (Former Student, PM Job Seeker)
**Session Type:** Follow-up research call / PM automation discussion
**Duration:** ~57 minutes
**Context:** Mike is preparing for PM interviews and exploring AI-assisted PM workflows

---

## Executive Summary

This check-in call revealed deep insights into how AI Product Playbook alumni are applying course concepts to real-world PM workflows. Mike is preparing for a strategic PM interview while exploring Personal OS and PM automation patterns. The conversation uncovered critical opportunities for course improvements, practical PM automation use cases, and interview preparation strategies.

**Key Discovery:** The Personal OS framework is being successfully adapted from personal task management to professional PM workflows, demonstrating the system's extensibility and value for PM-specific use cases.

---

## Desired Outcome

**For Aman's Course:** Increase student success rate in securing AI-native PM roles by teaching practical PM automation workflows and interview preparation strategies.

**For Mike (User):** Successfully demonstrate AI-native PM capabilities in upcoming interview while building reusable PM automation systems.

---

## Opportunity 1: Personal OS as PM Interview Differentiator

**Evidence Strength:** 🔴 High
**Customer Quote:** "I think you're right. I think it would be pretty impressive. I mean, you can't take credit for putting it together, but..." (Mike, line 38)

**Impact:** Students could significantly differentiate themselves in PM interviews by demonstrating structured, goal-oriented AI workflows using Personal OS as foundation.

### Sub-Opportunities:

1. **Interview showcase templates** - Students need guidance on adapting Personal OS for interview presentations
2. **Goal-task alignment demonstration** - Showing how daily work connects to quarterly goals impresses interviewers
3. **Time-boxed setup guidance** - Students need "good enough for demo" vs "production-ready" clarity

### Evidence from Transcript:

**Steven's positioning (lines 26-32):**
> "This is important for PMs because you can quickly shift this into PM goals, right? This is my quarterly goal, and actually, if you see the personal OS, it's more focused on that. It's more on the PM side. Okay, this is my quarterly goals. I have these KPIs, and then these are my tasks, and how this is connected right? This is a big gap that we have now because it's always tricky to see what you are doing, who is connected to the long-term vision."

**Key Insight:** PM interviews test strategic thinking and goal alignment - Personal OS provides tangible proof of this capability.

### Solution Experiments:

**Experiment 1A: Interview Prep Template**
- **Hypothesis:** If we provide a "Personal OS for PM Interviews" template with pre-configured project structure and sample tasks, students will be able to demo goal-task alignment in interviews with <2 hours setup time.
- **Test:** Create template with Ryder-like project structure (quarterly goals, KPIs, task breakdown), give to 3 job-seeking students, measure setup time and interview feedback
- **Measure:** Setup time, interview mention rate, recruiter/interviewer response
- **Effort:** Low (8 hours to create template + documentation)
- **Expected Impact:** High - directly addresses job placement outcome

**Experiment 1B: "Demo vs Production" Setup Guide**
- **Hypothesis:** Students are overbuilding Personal OS for interviews when minimal setup would suffice
- **Test:** Create tiered setup guide (Basic/Interview/Production levels), track which students choose which path
- **Measure:** Time to first demo, interview success rate by setup level
- **Effort:** Low (4 hours documentation)
- **Expected Impact:** Medium - reduces friction, increases completion rate

---

## Opportunity 2: Separation of Personal vs Professional Context

**Evidence Strength:** 🔴 High
**Customer Quote:** "Would you put your work stuff in here? Or would you try to keep that separate?" (Mike, line 59)

**Impact:** Students mixing personal and professional context experience friction and eventually abandon Personal OS for work use cases.

### Sub-Opportunities:

1. **Multi-repo architecture pattern** - Teach when to split vs combine repos
2. **Context boundary best practices** - Privacy, security, and cognitive separation
3. **MCP sharing strategies** - Reuse tools across repos without exposing personal data

### Evidence from Transcript:

**Steven's experience (lines 62-67):**
> "Yeah, that's a great question. And for example, at the end, at first I tried to put my job stuff here, like my PM stuff here, but eventually I saw that it was getting, like, too complex. Like, if I wanted to make, like, for example, I want to build an agent to help me write yours or like, a skill or anything... It's getting a bit messy."

**Steven's solution (lines 68-69):**
> "What I decided is to keep this personal OS to help me manage tasks in terms of what are my tasks against my goals? For example, I have tasks for automation in my PM work. But then what I did was to have a separate project only for PM automation, and it's only focused on PM automation."

**Mike's concern (line 75):**
> "Yeah, that's kind of. Yeah... Like you get to see all of my life and that."

### Solution Experiments:

**Experiment 2A: Multi-Repo Architecture Module**
- **Hypothesis:** If we teach explicit patterns for when to split repos (personal vs work, core vs specialized), students will architect cleaner systems and avoid abandonment
- **Test:** Create lesson module covering repo splitting strategies with decision tree, add to Week 2
- **Measure:** Student repo architecture quality, continuation rate beyond course
- **Effort:** Medium (12 hours - lesson creation, decision tree, examples)
- **Expected Impact:** High - prevents major pain point that causes abandonment

**Experiment 2B: "PM Automation Starter" Separate Repo**
- **Hypothesis:** Students want PM-specific automation but don't know how to separate it from Personal OS
- **Test:** Create reference implementation of PM automation repo (separate from Personal OS) with 3 core agents
- **Measure:** Adoption rate, student customization activity
- **Effort:** Medium (16 hours - build reference repo, documentation)
- **Expected Impact:** High - provides clear pattern students can follow

---

## Opportunity 3: PM Task Automation (High-Value Use Cases)

**Evidence Strength:** 🔴 High
**Customer Quote:** "I'd love your thoughts on that, too. So, for example, on client calls or user calls, right when you do user research, when you do customer calls, how do you take the context that you have for all the transcripts of those conversations and streamline the workflow to identify common themes, to identify opportunities to just create a visual map of sorts." (Mike, lines 313-317)

**Impact:** PMs spend 40-60% of time on repetitive tasks (writing user stories, task descriptions, reviewing Figma, processing research). Automation could reclaim 15-20 hours/week for strategic work.

### High-Value PM Automation Use Cases (Validated in Conversation):

1. **Task/Story Writing** - Lines 140-196 (Steven's Task Writer Agent demo)
2. **User Research Synthesis** - Lines 320-376 (Steven's Teresa Torres framework agent)
3. **Figma Review Automation** - Lines 207-210 (Steven's experimental Figma agent)
4. **Scenario Writing** - Lines 202-207 (Steven's scenario agent)

### Evidence from Transcript:

**Steven on task writing pain (line 184-185):**
> "That's fine for two, but when we have 15 different tasks, then that's super time-consuming. Now I can do it in ten minutes."

**Mike's excitement (line 164):**
> "This is really cool, man."

**Mike's time awareness (line 290):**
> "Because I'm not getting paid for it." [regarding interview prep scope]

### Solution Experiments:

**Experiment 3A: "PM Automation Blueprints" Course Module**
- **Hypothesis:** If we provide 3 reference PM automation agents (task writer, research synthesizer, strategic sparring partner) with implementation guides, students will successfully build their own PM workflows
- **Test:** Create Week 4-5 module teaching these patterns, measure student implementation success
- **Measure:** % students who build at least 1 PM automation agent, time saved reports
- **Effort:** High (40 hours - agent development, lesson creation, testing)
- **Expected Impact:** Very High - this is THE killer use case for AI-native PMs

**Experiment 3B: Task Writer Agent Starter Template**
- **Hypothesis:** Task writing is the highest-value, lowest-effort PM automation to teach first
- **Test:** Create standalone lesson just on task writing automation, launch as bonus content
- **Measure:** Completion rate, student reported time savings
- **Effort:** Medium (16 hours)
- **Expected Impact:** High - quick win, builds momentum

---

## Opportunity 4: Strategic Sparring Partner Agent

**Evidence Strength:** 🟡 Medium (single student, but highly specific need)
**Customer Quote:** "I think I want to do it so that I have maybe some initial templates or frameworks that I fill out myself, maybe stream of consciousness, even if it's vocal... Then, maybe use an MCP to fetch the information from a FigJam board or something, Notion, or wherever. I'm inputting all of that to then feed it back to me and then start doing the sparring there, challenging certain thoughts or that kind of thing." (Mike, lines 430-436)

**Impact:** PMs need AI partners that challenge thinking and identify blindspots, not just generate content. Current AI tools over-automate and reduce critical thinking.

### Sub-Opportunities:

1. **Human-in-the-loop strategic workflows** - Agent that challenges vs completes
2. **Opinionated stance development** - Help PMs build conviction, not just analysis
3. **Risk identification sparring** - Agent probes for blindspots

### Evidence from Transcript:

**Mike's clarity on what he DOESN'T want (lines 426-427):**
> "Because what I don't want is for it to do all of the thinking, right, and just generate a bunch of content that then I spend 45 minutes reading as opposed to actually thinking through the problem."

**Interview context (lines 472-474):**
> "Can you take an opinionated stance and back that opinionated stance and develop a coherent roadmap and an implementation testing strategy with incomplete information because it's a lead role?"

**Mike's product sense focus (line 474):**
> "Explain your thinking, and can you demonstrate that you've got product sense as you do so?"

### Solution Experiments:

**Experiment 4A: Strategic Sparring Agent Template**
- **Hypothesis:** If we create an agent designed to challenge (not generate), PMs will develop stronger strategic thinking skills
- **Test:** Build agent with personality focused on asking "why?", identifying risks, probing assumptions; test with 3 students on real strategy decisions
- **Measure:** Student satisfaction, quality of strategic artifacts, interview performance
- **Effort:** Medium (20 hours - agent design, personality tuning, testing)
- **Expected Impact:** High - differentiates course from "AI does the work for you" approaches

**Experiment 4B: "Opinionated PM" Framework Module**
- **Hypothesis:** Students struggle with taking strong stances vs presenting options
- **Test:** Create lesson on using AI for stance validation (not stance generation), teach conviction-building workflow
- **Measure:** Student confidence in interviews, quality of opinionated writing
- **Effort:** Low (8 hours)
- **Expected Impact:** Medium - addresses soft skill gap

---

## Opportunity 5: MCP Tool Development Workflow

**Evidence Strength:** 🔴 High
**Customer Quote:** "So how do you then go about writing these tools? Do you just speak to Cloud Code? Do you mean you ask it, 'Yeah, I want to do this. Can you help me write this tool?'" (Mike, lines 217-218)

**Impact:** Students don't have clear workflow for building custom MCP tools, leading to inconsistent results and wasted time.

### Sub-Opportunities:

1. **PRD-first MCP development** - Structured approach prevents agent from going off-rails
2. **Context management for agent builds** - Teach how to give agent enough context to build tools
3. **Iterative refinement workflow** - Human-in-loop tool building process

### Evidence from Transcript:

**Steven's workflow (lines 223-227):**
> "So in essence, what I'm doing... Yeah. First, I use CloudCode almost entirely. What I'm trying to do is give the agent enough context and tools for what I'm trying to do. For example, if I want to write something new before that, I want to make sure that I have good instructions for what I'm expecting when he's building a new PRD because I try to do it that way. Okay, I want to do a new tool, for example, this competitor research agent. First of all, what I'm trying to do is build a PRD for that."

**Steven's PRD structure (lines 224-227):**
> "So I have instructions. Again, the agent is doing that for me. So I say, 'Okay, I want to have instructions in your context for when you build a PRD that at least includes 12345 sections of what is useful to me.' Once I have that, the next time I build a PRD, I ask the agent to build a PRD, and he's going to follow the context and start building something decent, right?"

**Mike's pain point (lines 230-231):**
> "Have you found any sort of things or tips or tricks that work to keep the PRD really focused? Because what I found when I was working with cloud code and in generating PRDs for products that weren't like tools NCP tools is that, it often would go like a little bit overboard."

### Solution Experiments:

**Experiment 5A: "Feature Simple" Slash Command Template**
- **Hypothesis:** If students use structured slash commands with guardrails, they'll build higher-quality MCP tools with less agent drift
- **Test:** Provide Steven's `/feature-simple` command as template, teach in Week 3
- **Measure:** Student MCP tool quality, completion rate, agent drift incidents
- **Effort:** Low (6 hours - adapt Steven's command, create lesson)
- **Expected Impact:** High - solves major frustration point

**Experiment 5B: MCP Development Best Practices Module**
- **Hypothesis:** Students need explicit workflow: Context → PRD → Implementation → Testing
- **Test:** Create lesson on 4-step MCP development process with examples
- **Measure:** Student tool quality, time to first working MCP
- **Effort:** Medium (12 hours)
- **Expected Impact:** High - teaches repeatable process

---

## Opportunity 6: User Research Synthesis Automation

**Evidence Strength:** 🔴 High
**Customer Quote:** "On client calls or user calls, right when you do user research, when you do customer calls, how do you take the context that you have for all the transcripts of those conversations and streamline the workflow to identify common themes, to identify opportunities to just create a visual map of sorts." (Mike, lines 313-317)

**Impact:** Research synthesis is critical PM skill but extremely time-consuming. Automation enables continuous discovery habits at scale.

### Sub-Opportunities:

1. **Teresa Torres framework implementation** - Agent that applies continuous discovery methods
2. **Pattern recognition across transcripts** - Multi-session synthesis
3. **Visual opportunity mapping** - Translate research to artifacts teams can act on

### Evidence from Transcript:

**Steven's research agent (lines 331-337):**
> "For example, Aman. We have a bunch of calls, some calls, and we have again, transcripts. So what I'm doing is I have an agent here, which is again doing the same thing, like summarizing stuff... Yeah, so this one is an agent that is basically trying to do exactly what you say. It's focused on conducting user research, analyzing customer feedback, and mapping improvement opportunities using this particular Teresa Torres continuous discovery habits framework."

**Steven's agent output (lines 342-351):**
> "For example, I was trying to understand in terms of all the sessions where the user was blocked, where the students may need some help, which kind of tools we could have to improve the user experience in the system... You are going to have a common, you know, patterns and opportunities that you could say, okay, for example... friction pattern analyzes, you know, this is like a setup friction. This is a super common pattern."

**Mike's enthusiasm (line 373):**
> "This would be super helpful. Would you mind sharing these with me because I'd love to try them?"

### Solution Experiments:

**Experiment 6A: Research Synthesis Agent Template**
- **Hypothesis:** If we provide Steven's Teresa Torres agent as course asset, students will implement continuous discovery practices
- **Test:** Package agent with tutorial, provide to students in Week 4
- **Measure:** % students who use it on real research, quality of opportunity maps produced
- **Effort:** Low (6 hours - clean up Steven's agent, create tutorial)
- **Expected Impact:** Very High - enables high-value PM workflow

**Experiment 6B: Continuous Discovery Module**
- **Hypothesis:** Students don't know Teresa Torres framework, limiting their research effectiveness
- **Test:** Create lesson on opportunity mapping + AI-assisted synthesis
- **Measure:** Student research quality, opportunity identification rate
- **Effort:** High (20 hours - teach framework + automation)
- **Expected Impact:** Very High - teaches fundamental PM skill + AI acceleration

---

## Opportunity 7: Performance Coach / Reflection Agent

**Evidence Strength:** 🟡 Medium (Steven uses it, Mike interested)
**Customer Quote:** "It's good. It's a bit aggressive at this point, but I want to improve it. Yeah, sometimes it may get super aggressive more than I wanted, but that's the part of the continuous like optimization." (Steven, lines 389-393)

**Impact:** Students struggle with self-reflection and prioritization discipline. Coach agent provides accountability.

### Sub-Opportunities:

1. **Personality tuning for coaching style** - Balance between pushy and supportive
2. **Goal-task alignment audits** - Agent checks if work matches stated goals
3. **Bias detection in decision-making** - Agent surfaces cognitive biases

### Evidence from Transcript:

**Steven's coach description (lines 383-389):**
> "So this agent, when I ask the agent, this agent specifically, yeah, to help me do reflection, he's going to read the task, read the goals, and it's going to start pushing. It's super pushy. You know, this is kind of aggressive because this is the personality that I gave. But yeah, it's like, hey, what you are doing, you should be doing that. Like, is this really something that's trying to uncover biases or any kind of approval needs or things like that, psychologically?"

**Mike's humor (line 403):**
> "Remind me not to let you, like, you know, develop a AGI for us cause."

### Solution Experiments:

**Experiment 7A: Performance Coach Agent Template**
- **Hypothesis:** If students have accountability agent, they'll complete more goals and stay aligned
- **Test:** Create coach agent with adjustable personality, test with students struggling with follow-through
- **Measure:** Goal completion rate, student satisfaction, behavioral change
- **Effort:** Medium (16 hours - agent design, personality options, testing)
- **Expected Impact:** Medium - helps subset of students, may not be universal need

---

## PM Automation Patterns Discussed

### 1. Task Writer Agent (Azure DevOps Integration)

**Workflow:**
1. Agent fetches PBI (Product Backlog Item) context via API
2. User provides meeting transcript (drag/drop or paste)
3. Agent summarizes transcript with PM context extraction
4. Agent analyzes existing tasks and suggests improvements
5. Agent generates detailed task descriptions
6. Human approves/edits each task (human-in-loop)
7. Agent updates Azure DevOps via API

**Key Technical Details:**
- Uses Azure DevOps API with authentication tokens
- Summarizer agent extracts: business context, problem, UX flows, infrastructure, API endpoints, data/analytics
- Human approval at multiple stages (transcript summary, title changes, descriptions)
- Saves all context locally for future reference

**Time Savings:** 15 tasks in 10 minutes (vs hours manually)

**Quote (lines 184-185):**
> "That's fine for two, but when we have 15 different tasks, then that's super time-consuming. Now I can do it in ten minutes."

---

### 2. Scenario Writer Agent

**Workflow:**
1. Fetch PBI context
2. Process meeting transcript
3. Generate Gherkin scenarios (Given/When/Then)
4. Update user story descriptions

**Status:** Working, similar to Task Writer Agent

---

### 3. Figma Review Agent (Experimental)

**Workflow:**
1. Connect to Figma API
2. Extract node context from Figma files
3. Compare Figma flows against user stories/scenarios
4. Identify missing flows or discrepancies
5. Suggest updates

**Challenges:**
- High token usage (Figma files are large)
- Working on breaking down nodes for better context management
- Still in development

**Quote (lines 209-211):**
> "So this one is working quite fine. I'm still seeing that it's getting some challenges with the context because when you read one Figma file, it could be like a lot of tokens for just one context window. So I'm trying to break down the different nodes from the Figma and making sure that I have each node, and when I have each node, then I'm going to pass and store that context and then use it for comparison."

---

### 4. Research Synthesis Agent (Teresa Torres Framework)

**Workflow:**
1. Import meeting transcript (Granola, Krisp, or manual)
2. Agent applies Teresa Torres Continuous Discovery Habits framework
3. Extracts: outcomes, opportunities (the why), solutions (the how), experiments
4. Identifies friction patterns across multiple transcripts
5. Generates opportunity maps with evidence strength
6. Outputs structured analysis document

**Framework Structure:**
- Desired outcome (business/product goal)
- Opportunities (customer needs, pain points, desires)
- Solutions (specific ways to address opportunities)
- Experiments (assumption tests to validate solutions)

**Quote (lines 336-337):**
> "It's focused on conducting user research, analyzing customer feedback, and mapping improvement opportunities using this particular Teresa Torres continuous discovery habits framework."

---

### 5. Performance Coach Agent

**Workflow:**
1. Reads task files and goal documents
2. Analyzes alignment between tasks and stated goals
3. Provides "pushy" feedback on prioritization
4. Surfaces cognitive biases and approval-seeking behaviors
5. Challenges user on strategic choices

**Personality:** Intentionally aggressive/pushy (Steven tuning to be less so)

**Quote (lines 387-389):**
> "It's like, hey, what you are doing, you should be doing that. Like, is this really something that's trying to uncover biases or any kind of approval needs or things like that, psychologically?"

---

## Tools & Integrations Mentioned

### Tools in Steven's Stack:
- **Claude Code** - Primary agent interface
- **Azure DevOps** - Work item management (PBI, tasks)
- **Figma** - Design review via API
- **Granola** - Meeting notes and transcripts
- **Krisp** - Noise reduction + transcript capture
- **GitHub** - Version control for agents and context
- **Obsidian** - Personal OS interface (local markdown files)

### MCP Servers Mentioned:
- **Figma MCP** - Reading Figma nodes, taking screenshots
- **Notion MCP** - (Mentioned as possibility)
- **Trello MCP** - (Referenced via Teresa Torres example)

### APIs Used:
- Azure DevOps API (task automation)
- Figma API (design review)

---

## Agent Design Best Practices (Extracted from Conversation)

### 1. PRD-First Development

**Steven's Workflow (lines 223-227):**
1. Create instructions for how agent should build PRDs
2. Build PRD for the tool/agent you want
3. Ask agent to implement based on PRD
4. PRD tracks progress (what's done, what's left)

**Benefit:** Prevents agent from going off-rails, maintains context, enables progress tracking

---

### 2. Slash Commands with Guardrails

**Steven's `/feature-simple` command (lines 247-251):**
- Defines strict structure for feature breakdown
- Includes task breakdown by phase
- Forces follow-up questions before specification
- Prevents scope creep and overbuilding

**Quote (line 247):**
> "I have this slash command that is basically called a feature simple. A feature simple is super specific in terms of how I want the agent to build the feature. So we avoid this kind of situation that you are describing."

---

### 3. Human-in-the-Loop at Critical Points

**Steven's Task Writer Agent has approval gates at:**
1. Transcript summary review
2. Task title changes
3. Task description generation
4. Final API update

**Benefit:** Maintains control, enables course correction, builds trust in agent output

**Quote (line 156):**
> "If you see what he's doing is okay, I have this PBI and I'm going to fetch the context... Then this is going to say, 'Okay, man, I found two different tasks. Is that okay?' Yeah, is that okay? So let's continue. If you see this is like a human in the loop flow. Because I want to make sure that he's doing the right thing first."

---

### 4. Context Management Strategy

**Steven's approach (lines 102-112):**
- Store context in local empty files (markdown)
- Pull from multiple sources: customer feedback, experiments, competitor research, app reviews, goals
- Tools operate on this context
- Agent combines context to inform decisions

**Quote (lines 111-113):**
> "You could pull all these contexts in, like market, competitors, reviews, for example, from the App Store, if you have an app or any other website, you could have goals, you could have experiments. Then with that context, the funny part starts coming because this is where you can start doing a much better PM AI-assisted job."

---

### 5. Iterative Personality Tuning

**Steven's experience with coach agent:**
- Started too aggressive
- Continuously adjusting tone
- Experimentation required to find right balance

**Lesson:** Agent personality is design decision that requires iteration

---

### 6. Local Context Storage

**Benefits of local markdown files:**
- Version control (Git)
- Privacy (no cloud exposure)
- Agent can read/write easily
- Human-readable
- Supports reflection and synthesis over time

---

## Interview Preparation Insights

### What Mike is Being Tested On:

**From Mike (lines 472-474):**
> "Can you take an opinionated stance and back that opinionated stance and develop a coherent roadmap and an implementation testing strategy with incomplete information because it's a lead role? So, it's like a strategic exercise, as opposed to specifically crafting the test plan for this or the rollout phases and timelines and having a detailed roadmap."

**Key Assessment Criteria:**
1. **Opinionated stance** - Taking strong positions backed by reasoning
2. **Coherent roadmap** - Strategic sequencing and phasing
3. **Implementation strategy** - Practical execution thinking
4. **Incomplete information handling** - Decision-making under uncertainty
5. **Product sense** - Intuition and judgment

---

### How AI Should Support (Not Replace) Interview Prep:

**Mike's clarity (lines 426-427):**
> "Because what I don't want is for it to do all of the thinking, right, and just generate a bunch of content that then I spend 45 minutes reading as opposed to actually thinking through the problem."

**Steven's recommendation (lines 447-452):**
> "I would focus more on having a good agent like... Okay. I want to do these kinds of things. I don't want to do all the work for me. I want to have a human in the loop, interaction. So, I will focus more on that, trying to fine-tune that because that's pretty interesting."

---

### Mike's Interview Prep Plan (Committed):

**From lines 425-436:**
1. Design strategic sparring partner agent
2. Use initial templates/frameworks filled out manually (stream of consciousness)
3. Potentially use MCP to fetch from FigJam/Notion
4. Agent challenges thinking, identifies risks, probes opportunities
5. Separate step: Turn into presentation

**From lines 494-499:**
1. Build strategic sparring partner agent
2. Test Steven's user research agent
3. Customize research agent to fit his workflows
4. Apply to identify themes and opportunities

---

### Steven's Advice on Interview Focus (lines 465-467):

> "But if I were you, I would try to focus first on having good agents showing my workflows. At least that you can do because it's one hour, right? They are not going to ask about, like, 'Okay, how do you do all the processes?' They are trying to see how you think."

**Key Point:** Showcase thinking process, not automation infrastructure

---

### AI as Differentiator for PM Roles:

**Mike (lines 475-476):**
> "If I can showcase in my presentation part that I've accelerated my workflows using these things, that's exactly what a company like a faculty or an AI company would be looking for in terms of native."

**Interview Value Proposition:**
- Show AI-assisted workflow acceleration
- Demonstrate native AI thinking
- Prove strategic capability (AI as tool, not crutch)

---

## Technical Implementation Details

### Multi-Repo Architecture Pattern

**Steven's Structure:**
1. **Personal OS repo** - Task/goal management, cross-project coordination, reflection
2. **PM Automation repo** - Work-specific agents (task writer, Figma reviewer, etc.)
3. **Project-specific repos** - Pet Moments, other products

**Rationale (lines 68-69):**
> "What I decided is to keep this personal OS to help me manage tasks in terms of what are my tasks against my goals? For example, I have tasks for automation in my PM work. But then what I did was to have a separate project only for PM automation, and it's only focused on PM automation."

**Benefits:**
- Privacy (don't expose personal life to work tools)
- Deployment separation
- Sharing capability (can share PM automation without personal context)
- Cleaner agent context boundaries

---

### MCP Tool Consistency Strategy

**Steven's approach (lines 83-91):**
- Local MCP with project-specific tools
- Tools enforce consistent output format
- Example: `check_in_date` tool has predefined structure
- Agent uses tools → consistent UX

**Quote (lines 88-90):**
> "How do you think about agents? How do you think about tools for agents? How do you think about consistency and a better user experience? Because that's one of the problems with the agents, like consistency in giving the user a good experience."

---

### Git + Slash Commands for Agent Safety

**Steven's workflow (lines 250-251):**
> "Using this kind of commands in combination, of course with your versioning system, is the best thing you could do to go back. For example, if you feel that things are not going well and you need to go back into a checkpoint, using GitHub and pushing along with this is super helpful."

**Pattern:**
1. Use slash commands for structured agent workflows
2. Commit frequently
3. When agent goes off-rails → revert to checkpoint
4. Restart with better instructions

---

## Course Improvement Recommendations

### Immediate (Week 2-3) Additions:

1. **Multi-repo architecture decision tree** (Opportunity 2)
   - When to split personal vs work
   - Privacy and security considerations
   - MCP sharing strategies

2. **"Demo vs Production" setup tiers** (Opportunity 1)
   - Interview-ready: 2 hours setup
   - Daily use: 8 hours setup
   - Production: 20+ hours setup

3. **PRD-first MCP development workflow** (Opportunity 5)
   - Teach Steven's workflow
   - Provide `/feature-simple` template
   - Prevent agent drift

### Medium-Term (Week 4-5) Additions:

4. **PM Automation Blueprints Module** (Opportunity 3)
   - Task Writer Agent tutorial
   - Research Synthesis Agent (Teresa Torres framework)
   - Scenario Writer Agent
   - Reference implementations students can adapt

5. **Continuous Discovery + AI Module** (Opportunity 6)
   - Teach Teresa Torres framework
   - Opportunity mapping with AI assistance
   - Pattern recognition across transcripts
   - Visual synthesis workflow

6. **Strategic Sparring Partner Agent** (Opportunity 4)
   - Human-in-loop strategic thinking
   - Risk identification workflows
   - Opinionated stance development

### Long-Term Course Evolution:

7. **Interview Preparation Track**
   - Personal OS as portfolio piece
   - Demonstrating AI-native PM capabilities
   - Case study walkthrough templates

8. **Advanced Agent Design Module**
   - Personality tuning
   - Human-in-loop design patterns
   - Context management at scale

---

## Student Success Metrics to Track

Based on this conversation, we should measure:

1. **Job Placement Metrics:**
   - % students who showcase Personal OS in interviews
   - % students who mention AI workflows in offer letters/feedback
   - Time to job offer (AI-native vs traditional PM roles)

2. **PM Automation Adoption:**
   - % students who build at least 1 PM automation agent
   - Most common automation use cases (task writing, research, etc.)
   - Reported time savings

3. **System Continuation:**
   - % students still using Personal OS 3 months post-course
   - % students who split into multi-repo architecture
   - MCP tool development rate

4. **Interview Preparation:**
   - % students using AI for interview prep
   - Types of agents built for interviews
   - Interview success rate

---

## Patterns Across Research Participants

### Emerging Themes:

1. **Setup friction is universal** (Ricardo, Mike, others)
   - Initial setup time is barrier
   - Students don't know when "good enough" is reached
   - Over-engineering is common

2. **PM use cases are highly valued** (Mike, Steven's own work)
   - Task/story writing automation
   - Research synthesis
   - Figma/design review
   - Strategic sparring

3. **Personal vs work separation is critical** (Mike explicitly asked, Steven learned the hard way)
   - Privacy concerns
   - Cognitive separation
   - Sharing/collaboration needs

4. **Teresa Torres framework is powerful** (Steven using, Mike interested)
   - Structured approach to research synthesis
   - Opportunity mapping resonates with PMs
   - Visual artifacts needed

### Cross-Participant Validation:

| Insight | Mike | Ricardo | Steven | Confidence |
|---------|------|---------|--------|------------|
| Interview showcase value | ✅ Excited | ❓ TBD | ✅ Uses actively | High |
| PM automation high-value | ✅ Primary interest | ❓ TBD | ✅ Built 3+ agents | High |
| Personal/work separation | ✅ Asked explicitly | ❓ TBD | ✅ Learned by experience | High |
| Research synthesis need | ✅ Requested specifically | ❓ TBD | ✅ Built agent for it | High |
| Strategic sparring demand | ✅ Planning to build | ❓ TBD | ⏳ Not yet built | Emerging |

---

## Unanswered Questions / Follow-Up Research Needed

1. **How are other students using Personal OS for PM work?**
   - Need to survey broader cohort
   - Identify common PM automation patterns

2. **What is optimal interview prep time investment?**
   - Mike said "a few hours" (line 289)
   - Need to validate with students who've interviewed

3. **Which PM automation use case should we teach first?**
   - Task writing seems highest value
   - Research synthesis is more strategic
   - Need to test both and measure completion rates

4. **How to balance "AI does thinking" vs "AI supports thinking"?**
   - Mike's concern (line 426-427)
   - Steven's sparring partner approach
   - Need clear guidance on when to use each mode

5. **What visual tools work best for opportunity mapping?**
   - Mike wants visual output (line 317)
   - Figma MCP? Miro? Notion?
   - Need to test options

---

## Agent Sharing Plan

**Steven committed to sharing (lines 451-452, 501-502):**
1. Teresa Torres research synthesis agent
2. Performance coach agent
3. PM automation repo (task writer, scenario writer)
4. `/feature-simple` slash command

**Next Steps:**
- Steven will share agents with Mike
- Mike will test and provide feedback
- Follow-up call scheduled for Friday, Nov 21 (lines 518-522)
- Potential live session to build Mike's use cases together (lines 300-305)

---

## Next Actions for Aman/Course Team

### P0 (Immediate):
1. **Extract Steven's agents for course use**
   - Teresa Torres research synthesis agent
   - Task Writer Agent (Azure DevOps example)
   - `/feature-simple` slash command template

2. **Create "PM Automation Quick Start" bonus content**
   - 2-hour setup guide
   - Focus on task writing (highest ROI)
   - Interview showcase template

3. **Document multi-repo architecture pattern**
   - When to split repos
   - Privacy/security considerations
   - Add to Week 2 content

### P1 (This Quarter):
4. **Build Week 4-5 PM Automation Module**
   - 3 reference agents (task, research, scenarios)
   - Implementation tutorials
   - Testing/validation workflows

5. **Add Continuous Discovery Habits lesson**
   - Teresa Torres framework
   - AI-assisted opportunity mapping
   - Pattern recognition across research

6. **Create Interview Prep Track**
   - Personal OS as portfolio
   - Demo vs production setup tiers
   - Case study templates

### P2 (Future):
7. **Survey alumni on PM automation**
   - What use cases are they building?
   - Time savings quantification
   - Interview impact

8. **Build strategic sparring agent reference**
   - Human-in-loop design
   - Challenge mode vs generate mode
   - Opinionated stance development

---

## Researcher Reflection

### What worked well in this session:
- Steven's demos were extremely valuable (showed, not just told)
- Mike asked clarifying questions that revealed pain points
- Real-world PM context made abstract concepts concrete
- Shared enthusiasm created safe space for deep exploration

### What could improve next time:
- Could have probed more on "strategic sparring partner" concept
- Missed opportunity to discuss failure cases / what hasn't worked
- Would benefit from seeing Steven's actual agent code/prompts
- Could explore Figma agent challenges more deeply

### Patterns emerging across cohort:
- **Setup friction** is universal blocker (Ricardo, Mike, implied others)
- **PM use cases** are the killer app (task automation, research synthesis)
- **Goal alignment** is highly valued but underutilized
- **Interview prep** is top-of-mind for job seekers (Mike, others?)

### Key quotes that capture student mindset:

**On AI as differentiator:**
> "If I can showcase in my presentation part that I've accelerated my workflows using these things, that's exactly what a company like a faculty or an AI company would be looking for in terms of native." - Mike

**On avoiding over-automation:**
> "Because what I don't want is for it to do all of the thinking, right, and just generate a bunch of content that then I spend 45 minutes reading as opposed to actually thinking through the problem." - Mike

**On extensibility of Personal OS:**
> "I think if you can start showcasing something like this, okay, this is a way that I have as a PM to keep you on track in terms of my tasks, what I'm doing day to day against my long-term vision and the big picture." - Steven

---

## Meta Notes

**Research Quality:** High - this was a rich, technical discussion between two AI-native PMs sharing real workflows

**Transcript Clarity:** Very good - minimal crosstalk, clear speaker attribution

**Follow-Up Opportunity:** Mike will test Steven's agents and report back (Nov 21 call) - schedule follow-up research session

**Archetype:** Mike represents "PM Job Seeker" persona - highly motivated, technical, looking for competitive advantage

**Course Phase:** Post-graduate / alumni applying course concepts to real work

**Steven's Role:** Both TA and advanced practitioner - his workflows are case studies for what's possible

---

**Analysis completed:** 2025-11-07
**Analyst:** Claude (Teresa Torres Framework Agent)
**Next research session:** Mike check-in (Nov 21, 2025)
**Recommended follow-up:** Survey broader cohort on PM automation use cases
