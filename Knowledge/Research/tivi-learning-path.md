# Steven's Learning Path — AI-First PM & Builder

**Goals:** Ship Upstream + Deep AI/LLM technical fluency
**Current level:** Intermediate (solid prompting/context, fuzzy on agents/MCP/tool-use)
**Time budget:** 1-2 hrs/week
**Strategy:** Learn by building. Every learning block feeds directly into Upstream.

---

## Phase 1: Agents & Tool Use (Weeks 1-4)
> *Why first: This is the fuzziest area AND the core of what Upstream teaches users*

### Week 1 — How Agents Actually Work (30 min read + 30 min hands-on)
- [ ] Read: [Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) — Anthropic's definitive guide
  - Key concepts: agent loop, prompt chaining, routing, parallelization
  - **Apply to Upstream:** Map these patterns to your Growth Tree nodes

### Week 2 — Tool Use & Function Calling (1 hr hands-on)
- [ ] Read: [Tool Use Overview](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview) — how Claude calls external tools
- [ ] Try: Build a simple tool-use example in Python (use your Firebase setup)
  - **Apply to Upstream:** Design a "tool use" learning module for your users

### Week 3 — Context Engineering (1 hr)
- [ ] Read: [Context Engineering for AI Agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) — compaction, retrieval, sub-agent isolation
- [ ] Analyze: How OpenClaw (your own setup!) implements these patterns — AGENTS.md, SOUL.md, memory files
  - **Apply to Upstream:** This becomes content for your "Context Engineering" path

### Week 4 — MCP (Model Context Protocol) (1 hr)
- [ ] Course: [MCP Getting Started](https://anthropic.skilljar.com/introduction-to-model-context-protocol) — Anthropic Academy (free)
- [ ] Skim: [MCP Build Rich-Context Apps](https://www.deeplearning.ai/short-courses/mcp-build-rich-context-ai-apps-with-anthropic/) — DeepLearning.AI
  - **Apply to Upstream:** Decide if MCP integration is a feature worth building

---

## Phase 2: LLM Internals (Weeks 5-8)
> *Why: You're building an AI learning platform — you need to understand what you're teaching*

### Week 5 — How LLMs Work (1 hr)
- [ ] Watch: [3Blue1Brown — Transformers](https://www.youtube.com/watch?v=wjZofJX0v4M) (visual, no math prereqs)
- [ ] Read: [Anthropic Models Overview](https://docs.anthropic.com/en/docs/about-claude/models/overview) — Opus vs Sonnet vs Haiku tradeoffs
  - **Apply to Upstream:** Write your "How AI Works" explainer content (Level 1 users need this)

### Week 6 — Prompt Engineering Deep Dive (1 hr)
- [ ] Do: [Prompt Engineering Interactive Tutorial](https://github.com/anthropics/prompt-eng-interactive-tutorial) — Chapters 1-5 (Jupyter)
  - **Apply to Upstream:** Extract exercise patterns for your platform's practice modules

### Week 7 — Evals & Quality (1 hr)
- [ ] Read: [Anthropic Courses — Evaluations](https://github.com/anthropics/courses) — how to measure AI output quality
- [ ] Think: How would Upstream measure user "AI fluency" progression?
  - **Apply to Upstream:** Refine your Readiness Score methodology

### Week 8 — RAG & Retrieval (1 hr)
- [ ] Read: [Anthropic Cookbook — RAG patterns](https://github.com/anthropics/anthropic-cookbook)
- [ ] Explore: Embeddings, vector search, chunking strategies
  - **Apply to Upstream:** Could your content library use RAG for personalized recommendations?

---

## Phase 3: Ship & Differentiate (Weeks 9-12)
> *Why: Turn learning into product features*

### Week 9 — Agent SDK (1 hr)
- [ ] Read: [Agent SDK Docs](https://docs.anthropic.com/en/docs/claude-code/sdk) — production agent patterns
  - **Apply to Upstream:** Evaluate if an AI tutor agent (powered by SDK) is your killer feature

### Week 10 — Claude Code & Skills (1 hr)
- [ ] Course: [Claude Code in Action](https://anthropic.skilljar.com/claude-code-in-action) — Anthropic Academy
  - **Apply to Upstream:** Your users are PMs who code with AI — this is their workflow

### Week 11 — Competitive Analysis (1 hr)
- [ ] Map the landscape: Learn-Claude, Anthropic Academy, DeepLearning.AI, Coursera series
- [ ] Identify: What does Upstream do that NONE of them do?
  - **Apply to Upstream:** Sharpen positioning and landing page messaging

### Week 12 — Synthesize & Plan (1 hr)
- [ ] Review all notes and Upstream backlog
- [ ] Create Q2 roadmap based on everything learned
- [ ] Update Growth Tree content with real knowledge gained

---

## Principles

1. **Learn by building** — Every topic feeds directly into Upstream features or content
2. **Depth over breadth** — 1 topic per week, properly absorbed > skimming 5 things
3. **Document as you go** — Notes go to `personal-os-aipm-learner/Knowledge/`
4. **Teach to learn** — If you can explain it to Upstream users, you understand it
5. **Use your own setup as lab** — OpenClaw IS an agent system; study it while you use it

---

## Quick Reference: Resource Priority

| Resource | Type | Time | Priority |
|----------|------|------|----------|
| Building Effective Agents (Anthropic) | Article | 30 min | 🔴 Week 1 |
| Context Engineering (Anthropic) | Article | 30 min | 🔴 Week 3 |
| Tool Use Overview (Docs) | Docs | 30 min | 🔴 Week 2 |
| MCP Getting Started (Academy) | Course | 1 hr | 🟡 Week 4 |
| 3Blue1Brown Transformers | Video | 30 min | 🟡 Week 5 |
| Prompt Eng Tutorial (GitHub) | Hands-on | 2 hr | 🟡 Week 6 |
| Agent SDK Docs | Docs | 1 hr | 🟢 Week 9 |
| Claude Code in Action (Academy) | Course | 1 hr | 🟢 Week 10 |

---

**Started:** 2026-02-18
**Target completion:** ~12 weeks (May 2026)
**Review cadence:** Lobster checks in weekly
