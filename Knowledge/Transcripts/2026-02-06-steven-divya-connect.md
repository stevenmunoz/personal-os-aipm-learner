# Steven/Divya Connect

Fri, 06 Feb 26 · divya.sabade@gmail.com

### Product Vision & Positioning

- Building AI-powered learning assistant for knowledge workers
- Core positioning: "Learn for the future, not the hype"
  - Help users stay grounded vs. chasing AI trends
  - Focus on foundational mental models over trending content
  - Sustainable learning at user's own rhythm
- Target feeling: Users go from anxious/lost to confident and in control

### User Personas & Use Cases

- Primary persona: Career transition/interview prep
  - Real user example: Failed interview despite consuming lots of content
  - Pain point: Information overload without actionable synthesis
- Secondary personas:
  1. Continuous learner (AI PM staying current)
  2. Aspiring specialist (deep expertise seeker)
- Success metrics: Higher confidence, better learning outcomes, reduced anxiety

### Competitive Landscape Analysis

- Three competitor categories:
  1. Knowledge capture apps (MyMind, Obsidian)
  2. Structured leatforms (courses, bootcamps)
  3. Generic AI chat tools
- MyMind inspiration but current limitations:
  - Good for saving/organizing content
  - Poor retrieval and contextual application
  - Steven considering canceling subscription due to search friction

### Core Product Features (MVP)

- Chrome extension for content capture
  - Save/summarize/cluster functionality
  - Auto-tagging without manual effort
- Three key differentiators:
  1. Concept graph visualization (like Arize agent traces)
  2. Learning intent modeling for personalized paths
  3. High-quality contextual retrieval vs. generic responses
- Visual concept mapping showing knowledge connections
  - Users can click deeper into topics
  - Automatic hierarchy based on learning goals

### Technical Architecture Decisions

- Model-agnostic approach across vendors (OpenAI, Anthropic, etc.)
  - Switch models based on task complexity vs. cost
  - Firebase remote configuration for live production changes
- YouTube + newsletters as initial content sources
  - Gemini models for better YouTube transcription
  - Easier content extraction than LinkedIn posts
- Chrome extension as starting point, expand to web app

### Pricing & Cost Management Strategy

- AI-heavy product requires careful unit economics
- Dynamic model selection:
  - Powerful models (Claude Opus) for complex aggregation
  - Cheaper models for simple extraction tasks
- Firebase remote config enables real-time cost control
  - Live switching between vendors during usage spikes
  - Prevent service interruption while managing costs

### Development Workflow & Collaboration

- Shared GitHub repo with AI assistant integration
- Cursor IDE with paid subscription for better models
- Two-repo structure:
  1. Research/planning repo (current setup)
  2. Product development repo (to be created)
- Divya can prototype independently using AI agents
- Weekly Friday sync meetings, flexible backup slots

### Next Steps

- Steven: Inject meeting insights into research repo, create implementation plan
- Steven: Build landing page prototypes for positioning validation
- Divya: Upgrade to paid Cursor subscription
- Divya: Review Aman's course (initial sessions + Eric's workflows)
- Both: Experiment with Chrome extension for YouTube/newsletter capture
- Target: Working prototype within 2 weeks

---

Chat with meeting transcript: https://notes.granola.ai/t/23a88263-7ce6-4c80-8683-dd1c46dee51c-00best9l
