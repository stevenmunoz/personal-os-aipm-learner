# AI PM Learning Tool - Tech Stack & Architecture

**Product:** Content Aggregation & Learning Path Generation
**Date:** January 23, 2026
**Version:** MVP Architecture v1.0
**Recommendation By:** Steven Muñoz (based on Firebase experience)

---

## Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────────┐
│                         USER INTERACTIONS                            │
└─────────────────────────────────────────────────────────────────────┘
                                    │
        ┌───────────────────────────┼───────────────────────────┐
        │                           │                           │
        ▼                           ▼                           ▼
┌──────────────┐          ┌──────────────┐          ┌──────────────┐
│   Browser    │          │   Web App    │          │  Mobile App  │
│  Extension   │          │   (React)    │          │  (Future)    │
│   (Chrome)   │          │              │          │              │
└──────────────┘          └──────────────┘          └──────────────┘
        │                           │                           │
        │                           │                           │
        └───────────────────────────┼───────────────────────────┘
                                    │
                                    │ HTTPS/REST
                                    ▼
        ┌─────────────────────────────────────────────────────┐
        │              FIREBASE (Backend as a Service)         │
        ├─────────────────────────────────────────────────────┤
        │                                                       │
        │  ┌─────────────────────────────────────────────┐   │
        │  │         Firebase Authentication              │   │
        │  │  (Email, Google, GitHub OAuth)               │   │
        │  └─────────────────────────────────────────────┘   │
        │                       │                              │
        │                       ▼                              │
        │  ┌─────────────────────────────────────────────┐   │
        │  │         Cloud Firestore (NoSQL DB)           │   │
        │  │  • Users collection                          │   │
        │  │  • Content collection (saved items)          │   │
        │  │  • LearningPaths collection                  │   │
        │  │  • Topics collection (clusters)              │   │
        │  └─────────────────────────────────────────────┘   │
        │                       │                              │
        │                       ▼                              │
        │  ┌─────────────────────────────────────────────┐   │
        │  │         Cloud Functions (Serverless)         │   │
        │  │                                               │   │
        │  │  ┌────────────────────────────────────┐     │   │
        │  │  │  onContentSaved()                   │     │   │
        │  │  │  • Extract metadata                 │     │   │
        │  │  │  • Call LLM for summarization       │     │   │
        │  │  │  • Generate embeddings              │     │   │
        │  │  │  • Store in Firestore + Vector DB   │     │   │
        │  │  └────────────────────────────────────┘     │   │
        │  │                                               │   │
        │  │  ┌────────────────────────────────────┐     │   │
        │  │  │  generateLearningPath()             │     │   │
        │  │  │  • Analyze user intent              │     │   │
        │  │  │  • Cluster related content          │     │   │
        │  │  │  • Create time-boxed curriculum     │     │   │
        │  │  │  • Return personalized path         │     │   │
        │  │  └────────────────────────────────────┘     │   │
        │  │                                               │   │
        │  │  ┌────────────────────────────────────┐     │   │
        │  │  │  searchContent()                    │     │   │
        │  │  │  • Vector similarity search         │     │   │
        │  │  │  • Context-aware ranking            │     │   │
        │  │  │  • Return relevant items            │     │   │
        │  │  └────────────────────────────────────┘     │   │
        │  │                                               │   │
        │  └─────────────────────────────────────────────┘   │
        │                                                       │
        └─────────────────────────────────────────────────────┘
                                    │
                    ┌───────────────┼───────────────┐
                    │               │               │
                    ▼               ▼               ▼
        ┌──────────────────┐  ┌──────────────┐  ┌──────────────┐
        │  Anthropic API   │  │  Pinecone    │  │  Firebase    │
        │  (Claude)        │  │  (Vector DB) │  │  Storage     │
        │                  │  │              │  │              │
        │  • Summarization │  │  • Embeddings│  │  • Screenshots│
        │  • Clustering    │  │  • Semantic  │  │  • PDFs      │
        │  • Intent        │  │    search    │  │  • Images    │
        │    analysis      │  │              │  │              │
        └──────────────────┘  └──────────────┘  └──────────────┘
                    │               │               │
                    └───────────────┴───────────────┘
                                    │
                        ┌───────────┴───────────┐
                        ▼                       ▼
              ┌──────────────────┐    ┌──────────────────┐
              │  External APIs   │    │  Content Sources │
              │                  │    │                  │
              │  • LinkedIn      │    │  • User uploads  │
              │  • Medium        │    │  • Web scraping  │
              │  • YouTube       │    │  • RSS feeds     │
              │  • GitHub        │    │                  │
              └──────────────────┘    └──────────────────┘
```

---

## Tech Stack Breakdown

### **Frontend Layer**

#### 1. Browser Extension
**Technology:** Chrome Extension (Manifest V3)
**Framework:** React + TypeScript
**Purpose:** Content capture from LinkedIn, Medium, YouTube, etc.

**Key Components:**
- Content script (detects saveable content)
- Background service worker (manages state)
- Popup UI (quick save, tagging)
- Context menu integration

**Why this choice:**
- Native browser integration
- Access to page DOM
- Persistent background process
- Chrome Web Store distribution

**Estimated Effort:** 40 hours (MVP)

---

#### 2. Web Application
**Technology:** React 18 + TypeScript
**Styling:** Tailwind CSS
**State Management:** Zustand or React Query
**Routing:** React Router v6

**Purpose:** Main user interface for organizing, searching, and learning

**Key Pages:**
- Dashboard (saved content overview)
- Search & Filter (find saved items)
- Learning Paths (personalized curricula)
- Profile & Settings

**Why this choice:**
- Fast development
- Rich component ecosystem
- Great developer experience
- Easy deployment (Vercel, Netlify, or Firebase Hosting)

**Estimated Effort:** 80 hours (MVP)

---

### **Backend Layer**

#### 3. Firebase (Backend as a Service)
**Services Used:**
- **Firebase Authentication:** User management
- **Cloud Firestore:** NoSQL database
- **Cloud Functions:** Serverless compute
- **Firebase Storage:** File storage
- **Firebase Hosting:** Static site hosting

**Why Firebase (from Steven's experience):**
✅ **Extremely cheap** - $1/month for MVP, scales with usage
✅ **Serverless** - No backend code needed, just functions
✅ **Real-time** - Live updates to UI
✅ **Built-in auth** - Google, Email, GitHub OAuth
✅ **Global CDN** - Fast worldwide
✅ **Offline support** - Works without connection
✅ **Google backing** - Reliable, maintained

**Monthly Cost Estimate (MVP with 100 users):**
- Firestore: ~$0.50 (reads/writes)
- Cloud Functions: ~$0.25 (invocations)
- Storage: ~$0.10 (stored content)
- Hosting: Free tier
- **Total: ~$1-2/month**

**Estimated Effort:** 60 hours (setup + functions)

---

#### 4. Cloud Functions (Serverless Logic)
**Technology:** Node.js 18 + TypeScript
**Triggers:** HTTP, Firestore, Scheduled

**Key Functions:**

**onContentSaved (Firestore Trigger)**
```javascript
// Triggered when user saves content
exports.onContentSaved = functions.firestore
  .document('content/{contentId}')
  .onCreate(async (snap, context) => {
    const content = snap.data();

    // 1. Extract metadata (title, author, date)
    const metadata = await extractMetadata(content.url);

    // 2. Call Claude for summarization
    const summary = await anthropic.messages.create({
      model: "claude-3-5-sonnet-20241022",
      messages: [{
        role: "user",
        content: `Summarize key concepts from: ${content.text}`
      }]
    });

    // 3. Generate embedding for semantic search
    const embedding = await generateEmbedding(summary.content);

    // 4. Store in Pinecone
    await pinecone.upsert([{
      id: contentId,
      values: embedding,
      metadata: { userId, topic, summary }
    }]);

    // 5. Update Firestore
    await snap.ref.update({
      summary: summary.content,
      metadata,
      processed: true
    });
  });
```

**generateLearningPath (HTTP Callable)**
```javascript
// Triggered when user requests learning path
exports.generateLearningPath = functions.https.onCall(async (data, context) => {
  const { userId, intent, timeframe, proficiency } = data;

  // 1. Fetch user's saved content
  const savedContent = await getSavedContent(userId);

  // 2. Cluster by topic using embeddings
  const clusters = await clusterContentByTopic(savedContent);

  // 3. Generate curriculum using Claude
  const path = await anthropic.messages.create({
    model: "claude-3-5-sonnet-20241022",
    messages: [{
      role: "user",
      content: `Create a ${timeframe} learning path for ${intent}
                at ${proficiency} level using these topics: ${clusters}`
    }]
  });

  // 4. Store and return
  await storeLearningPath(userId, path);
  return path;
});
```

**searchContent (HTTP Callable)**
```javascript
// Semantic search using vector similarity
exports.searchContent = functions.https.onCall(async (data, context) => {
  const { userId, query } = data;

  // 1. Generate query embedding
  const queryEmbedding = await generateEmbedding(query);

  // 2. Vector search in Pinecone
  const results = await pinecone.query({
    vector: queryEmbedding,
    topK: 20,
    filter: { userId }
  });

  // 3. Fetch full content from Firestore
  const content = await Promise.all(
    results.matches.map(m => getContentById(m.id))
  );

  return content;
});
```

**Estimated Effort:** 60 hours (core functions)

---

### **Data Layer**

#### 5. Cloud Firestore (NoSQL Database)
**Data Model:**

```javascript
// Users Collection
users/{userId}
  ├─ email: string
  ├─ displayName: string
  ├─ proficiencyLevel: "beginner" | "intermediate" | "advanced"
  ├─ goals: string[]
  ├─ createdAt: timestamp
  └─ preferences: object

// Content Collection (saved items)
content/{contentId}
  ├─ userId: string (indexed)
  ├─ sourceUrl: string
  ├─ sourceType: "linkedin" | "medium" | "youtube" | "manual"
  ├─ title: string
  ├─ author: string
  ├─ rawText: string (full content)
  ├─ summary: string (AI-generated)
  ├─ keyTakeaways: string[]
  ├─ topics: string[] (e.g., ["agents", "evals"])
  ├─ proficiencyLevel: string (AI-determined)
  ├─ savedAt: timestamp
  ├─ lastAccessedAt: timestamp
  └─ metadata: object

// Learning Paths Collection
learningPaths/{pathId}
  ├─ userId: string
  ├─ intent: string (e.g., "interview prep")
  ├─ timeframe: "2-weeks" | "1-month" | "3-months"
  ├─ proficiency: string
  ├─ curriculum: array [
  │     { week: 1, topics: ["agents"], contentIds: [...] },
  │     { week: 2, topics: ["evals"], contentIds: [...] }
  │   ]
  ├─ progress: object
  ├─ createdAt: timestamp
  └─ completedAt: timestamp?

// Topics Collection (clusters)
topics/{topicId}
  ├─ name: string (e.g., "AI Agents")
  ├─ description: string
  ├─ relatedTopics: string[]
  ├─ contentCount: number
  └─ popularityScore: number
```

**Why Firestore:**
- Real-time updates (user sees processing happen live)
- Flexible schema (easy to iterate on data model)
- Offline support (works on slow connections)
- Security rules (row-level permissions)

**Estimated Effort:** 20 hours (schema design + security rules)

---

#### 6. Pinecone (Vector Database)
**Purpose:** Semantic search via embeddings

**Setup:**
- 1 index for content embeddings
- Dimension: 1536 (OpenAI ada-002) or 768 (sentence-transformers)
- Metric: Cosine similarity
- Metadata filtering (userId, topic, proficiency)

**Use Cases:**
- "Find content similar to this article"
- "Show me everything about agents"
- "Search by intent: interview prep in 2 weeks"

**Cost:** Free tier (100K vectors, enough for MVP)

**Why Pinecone:**
- Purpose-built for vector search
- Fast queries (<100ms)
- Metadata filtering
- Managed service (no ops)

**Alternative (Cheaper for MVP):** Supabase pgvector extension

**Estimated Effort:** 16 hours (integration + testing)

---

### **AI/ML Layer**

#### 7. Anthropic Claude API
**Model:** Claude 3.5 Sonnet (or Haiku for cost optimization)

**Use Cases:**

**1. Content Summarization**
```
Input: Full article text
Output: 3-5 sentence summary + key takeaways
Cost: ~$0.003 per article (500 tokens)
```

**2. Topic Clustering**
```
Input: 10 article summaries
Output: Topic labels + groupings
Cost: ~$0.01 per clustering run
```

**3. Learning Path Generation**
```
Input: User intent + saved content summaries + proficiency
Output: Week-by-week curriculum
Cost: ~$0.05 per path generation
```

**4. Intent Analysis**
```
Input: User search query
Output: Inferred intent + recommended content
Cost: ~$0.001 per search
```

**Monthly Cost (100 users, 20 saves/user, 2 paths/user):**
- Summarization: 2,000 articles × $0.003 = $6
- Path generation: 200 paths × $0.05 = $10
- Search: 500 searches × $0.001 = $0.50
- **Total: ~$16.50/month**

**Why Claude:**
- Best-in-class summarization
- Fast (streaming responses)
- Steven already familiar with API
- Good cost/quality ratio

**Alternative (for cost):** Use Claude Haiku for summarization ($0.25 per 1M tokens)

**Estimated Effort:** 30 hours (prompt engineering + integration)

---

#### 8. Embeddings Generation
**Option 1:** OpenAI ada-002 ($0.0001 per 1K tokens)
**Option 2:** Sentence Transformers (free, self-hosted)

**Recommendation for MVP:** OpenAI ada-002
- Simple API
- High quality
- Low cost ($0.20 for 2,000 articles)

**Estimated Effort:** 8 hours (integration)

---

### **External Integrations**

#### 9. Content Source APIs

**LinkedIn (No official API for content scraping)**
- Browser extension scrapes from DOM
- Extract: title, author, content, images, date

**Medium**
- RSS feeds for public content
- Extract via HTML parsing

**YouTube**
- YouTube Data API v3
- Transcript API for captions

**GitHub**
- GitHub REST API
- Extract: repo READMEs, starred repos

**Estimated Effort:** 40 hours (all integrations)

---

## Complete Tech Stack Summary

| Layer | Technology | Purpose | Cost (100 users) | Effort |
|-------|-----------|---------|------------------|--------|
| **Frontend** | React + TypeScript | Web app | $0 (free hosting) | 80h |
| **Extension** | Chrome Extension | Content capture | $0 | 40h |
| **Backend** | Firebase Functions | Serverless compute | $1-2 | 60h |
| **Database** | Cloud Firestore | NoSQL storage | $0.50 | 20h |
| **Vector DB** | Pinecone | Semantic search | $0 (free tier) | 16h |
| **LLM** | Claude 3.5 Sonnet | Summarization, paths | $16 | 30h |
| **Embeddings** | OpenAI ada-002 | Vector generation | $0.20 | 8h |
| **Auth** | Firebase Auth | User management | $0 | 10h |
| **Storage** | Firebase Storage | Files (PDFs, images) | $0.10 | 8h |
| **Hosting** | Firebase Hosting | Static site | $0 | 4h |
| **APIs** | LinkedIn, Medium, etc. | Content sources | $0 | 40h |
| **TOTAL** | | | **~$18-20/month** | **~320 hours** |

---

## MVP Development Phases

### Phase 1: Foundation (Week 1-2, 80 hours)
**Goal:** User can save content and see it organized

**Deliverables:**
- Firebase project setup
- User authentication (email + Google)
- Firestore schema implemented
- Basic web app (dashboard, list view)
- Browser extension (save from LinkedIn)

**Success Metric:** User can save 10 items and view them

---

### Phase 2: Intelligence (Week 3-4, 80 hours)
**Goal:** AI summarizes and clusters content

**Deliverables:**
- Claude API integration (summarization)
- Cloud Functions (onContentSaved)
- Topic clustering algorithm
- Embedding generation
- Pinecone vector search

**Success Metric:** Saved content auto-summarized and grouped by topic

---

### Phase 3: Personalization (Week 5-6, 80 hours)
**Goal:** Users can generate learning paths

**Deliverables:**
- Intent-based search
- Learning path generation (Claude)
- Time-boxed curriculum
- Progress tracking
- Path completion UI

**Success Metric:** User generates "Interview prep in 2 weeks" path

---

### Phase 4: Polish (Week 7-8, 80 hours)
**Goal:** Production-ready MVP

**Deliverables:**
- Multi-source support (Medium, YouTube)
- Advanced filtering
- Mobile-responsive UI
- Performance optimization
- User testing & feedback

**Success Metric:** 10 beta users using daily for 1 week

---

## Alternative Architectures (Considered & Rejected)

### Option 1: Traditional Backend (Node.js + Express + PostgreSQL)
**Pros:** Full control, familiar patterns
**Cons:** Higher cost (~$50/month hosting), slower development, need to manage servers
**Verdict:** ❌ Rejected (Firebase faster + cheaper for MVP)

### Option 2: Supabase (Firebase alternative)
**Pros:** PostgreSQL (relational), open source, good for complex queries
**Cons:** Less mature than Firebase, fewer integrations, Steven less familiar
**Verdict:** ✅ Valid alternative (consider if outgrow Firebase)

### Option 3: Full Serverless AWS (Lambda + DynamoDB)
**Pros:** Most scalable, mature ecosystem
**Cons:** Steep learning curve, complex setup, slower development
**Verdict:** ❌ Rejected (overkill for MVP)

### Option 4: All-in-One (Retool, Bubble, etc.)
**Pros:** Fastest to build
**Cons:** Limited customization, vendor lock-in, not impressive technically
**Verdict:** ❌ Rejected (want to own tech)

---

## Recommended MVP Scope

### Must-Have (P0) - Launch Blockers
✅ Save content from LinkedIn (browser extension)
✅ AI summarization (Claude)
✅ Topic clustering
✅ Basic search & filter
✅ User authentication
✅ Dashboard view

### Should-Have (P1) - Launch in 2-4 weeks
✅ Learning path generation
✅ Intent-based search
✅ Save from Medium, YouTube
✅ Progress tracking
✅ Mobile-responsive

### Nice-to-Have (P2) - Post-Launch
- Strategic sparring partner AI
- Peer matching
- Chrome extension for all sites
- Mobile app
- Team features

---

## Cost Projections

### MVP (100 users)
- Fixed: $18-20/month
- Per user: ~$0.18/month
- Break-even: $5-10/user subscription

### Scale (1,000 users)
- Fixed: $50-80/month
- Per user: ~$0.05-0.08/month
- 80% profit margin at $10/user

### Scale (10,000 users)
- Fixed: $400-600/month
- Per user: ~$0.04-0.06/month
- Need to optimize LLM costs (caching, batching)

---

## Technical Risks & Mitigations

### Risk 1: LLM Costs Spiral
**Risk:** Users save 100+ items/week, costs explode
**Mitigation:**
- Cache summaries (don't re-summarize)
- Batch processing (summarize 10 at once)
- Use Claude Haiku for simple summaries
- Rate limit (max 50 saves/week in free tier)

### Risk 2: Browser Extension Blocked
**Risk:** LinkedIn blocks scraping
**Mitigation:**
- User-initiated saves only (not automatic)
- Respect robots.txt
- Manual paste option as fallback
- Diversify sources (Medium, YouTube)

### Risk 3: Vector DB Performance
**Risk:** Search becomes slow at scale
**Mitigation:**
- Pinecone designed for scale
- Metadata filtering reduces search space
- Cache frequent queries
- Consider Supabase pgvector if cost issue

### Risk 4: Firebase Limits
**Risk:** Outgrow free tier quickly
**Mitigation:**
- Monitor usage closely
- Optimize queries (use indexes)
- Migrate to Supabase if needed (similar API)

---

## Development Timeline

**Total Estimate:** 320 hours = **8 weeks @ 40 hours/week** (1 full-time developer)

**With 2 developers (Steven + Divya):**
- **4 weeks to MVP** (working together)
- **6 weeks to polished beta** (with user testing)

**Recommended Pace:**
- Week 1-2: Foundation (auth, save, display)
- Week 3-4: Intelligence (AI summarization, clustering)
- Week 5-6: Personalization (learning paths)
- Week 7-8: Polish + user testing

---

## Next Steps

1. **Validate tech stack** with Divya (confirm she's comfortable with React + Firebase)
2. **Set up Firebase project** (Steven can do in 2 hours)
3. **Create GitHub repo** (monorepo with /extension, /web, /functions)
4. **Build Chrome extension MVP** (save from LinkedIn, 1 week)
5. **Integrate Claude API** (summarization POC, 3 days)
6. **Design Firestore schema** (together, 1 day)
7. **Sprint 1 kickoff** (Week 1: User auth + basic save/display)

---

**Created:** January 23, 2026
**For:** AI PM Learning Tool MVP
**By:** Steven Muñoz
**Next:** Review with Divya, finalize stack, set up repos
