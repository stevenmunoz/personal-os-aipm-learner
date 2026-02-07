# AI PM Learning Tool - Implementation Plan

**Target**: Working Prototype by February 20, 2026 (14 days)
**Team**: Steven Muñoz (Tech Lead) + Divya Sabade (Product Strategy)
**Stage**: Research & Design → MVP Development
**Primary Persona**: Career Transitioner (Alex/Mike) preparing for AI PM interviews

---

## Executive Summary

**Goal**: Ship a Chrome extension that solves the "content graveyard" problem for AI PM learners preparing for interviews.

**Core Value Proposition**: "Learn for the future, not the hype" - Turn 87 saved posts into interview-ready knowledge in 14 days.

**MVP Scope**:
- Chrome extension for YouTube + newsletter capture
- AI-powered summarization and clustering
- Interview mode learning path generation
- Basic concept graph (text-based, not visual yet)

**Success Metrics**:
- User can save 5+ items in first session
- AI generates personalized 14-day interview prep plan
- User rates confidence ⭐⭐⭐+ on at least 3 topics
- Working end-to-end demo for user validation

---

## Sprint Timeline (4 Weeks to MVP)

### 🏗️ **Sprint 1: Foundation** (Feb 6-13, 2026) - Week 1
**Milestone**: Infrastructure + Basic Capture + AI Summarization
**Owner**: Steven (primary), Divya (Chrome extension experiments)

### 🧠 **Sprint 2: Intelligence** (Feb 14-20, 2026) - Week 2
**Milestone**: Clustering + Learning Path Generator + Working Prototype
**Owner**: Steven (backend/AI), Divya (UX validation)

### 🎯 **Sprint 3: Personalization** (Feb 21-27, 2026) - Week 3
**Milestone**: Concept Graph + Confidence Tracking + Refinements
**Owner**: Both (parallel work on features)

### ✨ **Sprint 4: Polish** (Feb 28-Mar 6, 2026) - Week 4
**Milestone**: User Testing + Landing Page + MVP Launch Prep
**Owner**: Divya (testing), Steven (bug fixes)

---

## Detailed Implementation Breakdown

---

## 🏗️ Sprint 1: Foundation (Feb 6-13, 2026)

**Theme**: Get the foundation right - infrastructure, content capture, basic AI integration

### Week 1 Goals:
- [ ] Firebase project setup with authentication
- [ ] Chrome extension that saves YouTube videos
- [ ] Basic AI summarization working (Claude API)
- [ ] Firestore schema validated
- [ ] First user can save and see summarized content

---

### **Day 1-2: Infrastructure Setup** (Feb 6-7, Thu-Fri)

#### Task 1.1: Create Product Development Repository
**Owner**: Steven
**Time**: 2 hours
**Acceptance Criteria**:
- [ ] New GitHub repo: `aipm-learning-tool`
- [ ] Separate from research repo (personal-os-aipm-learner)
- [ ] Monorepo structure with `/extension`, `/web-app`, `/functions`
- [ ] Initial README with setup instructions
- [ ] Divya has contributor access

**Technical Details**:
```bash
aipm-learning-tool/
├── extension/          # Chrome extension code
│   ├── manifest.json
│   ├── popup/
│   ├── content/
│   └── background/
├── web-app/           # React web app (future)
├── functions/         # Firebase Cloud Functions
├── firestore.rules    # Security rules
└── README.md
```

---

#### Task 1.2: Firebase Project Setup
**Owner**: Steven
**Time**: 3 hours
**Acceptance Criteria**:
- [ ] Firebase project created: `aipm-learner-prod`
- [ ] Authentication enabled (Email, Google OAuth)
- [ ] Firestore database created (us-central1)
- [ ] Firebase Functions initialized
- [ ] Remote Config setup for model selection
- [ ] Environment variables documented

**Firebase Configuration**:
```javascript
// Remote Config Parameters
{
  "summarization_model": "claude-opus-4-6",    // Can switch to haiku for cost
  "embedding_model": "text-embedding-3-large",
  "clustering_threshold": 0.7,
  "max_tokens_summary": 500
}
```

---

#### Task 1.3: Firestore Schema Design
**Owner**: Steven
**Time**: 2 hours
**Acceptance Criteria**:
- [ ] Schema documented in `/docs/firestore-schema.md`
- [ ] Collections defined with indexes
- [ ] Security rules written and tested
- [ ] Sample data seeded for testing

**Firestore Schema**:
```javascript
// Collection: users
{
  uid: string,
  email: string,
  displayName: string,
  createdAt: timestamp,
  onboardingCompleted: boolean,
  preferences: {
    learningGoal: "interview" | "project" | "mastery",
    dailyTimeCommitment: "light" | "moderate" | "intensive"
  }
}

// Collection: content
{
  id: string,
  userId: string,
  sourceType: "youtube" | "newsletter" | "article",
  url: string,
  title: string,
  metadata: {
    author: string,
    duration: number,      // in minutes
    publishedDate: timestamp,
    transcript: string     // Raw content
  },
  aiProcessing: {
    summary: string,
    keyTakeaways: [string],
    topics: [string],       // Auto-generated tags
    difficulty: "beginner" | "intermediate" | "advanced",
    prerequisites: [string],
    relatedConcepts: [string]
  },
  userAnnotations: {
    notes: string,
    confidenceRating: 1-5,  // Star rating
    bookmarked: boolean,
    completedAt: timestamp
  },
  createdAt: timestamp,
  updatedAt: timestamp
}

// Collection: topics (Clusters)
{
  id: string,
  userId: string,
  name: string,           // e.g., "RAG Architecture"
  contentIds: [string],   // References to content
  conceptGraph: {
    prerequisites: [topicId],
    relatedTopics: [topicId],
    childConcepts: [topicId]
  },
  progress: {
    totalItems: number,
    completedItems: number,
    averageConfidence: number  // 1-5
  },
  createdAt: timestamp
}

// Collection: learningPaths
{
  id: string,
  userId: string,
  goal: "interview" | "project" | "mastery",
  parameters: {
    role: string,          // "AI Product Manager"
    companyType: string,   // "AI-native"
    timeline: number,      // days
    dailyTimeCommitment: string
  },
  curriculum: [
    {
      week: number,
      day: number,
      contentIds: [string],
      estimatedTime: number,  // minutes
      focus: string,          // "System Design Patterns"
      completed: boolean
    }
  ],
  progress: {
    currentDay: number,
    completedItems: number,
    totalItems: number,
    confidenceScore: number  // 1-5
  },
  createdAt: timestamp,
  updatedAt: timestamp
}
```

---

#### Task 1.4: Model Selection & Cost Analysis
**Owner**: Steven
**Time**: 2 hours
**Acceptance Criteria**:
- [ ] Benchmark Claude Opus vs Haiku for summarization quality
- [ ] Test Gemini 1.5 for YouTube transcription
- [ ] Calculate cost per content item (summarization + embeddings)
- [ ] Document in `/docs/model-selection.md`
- [ ] Set up Firebase Remote Config for live switching

**Models to Test**:
1. **Summarization**:
   - Claude Opus 4.6 (highest quality)
   - Claude Sonnet 4.5 (balanced)
   - Claude Haiku 4.5 (cost-effective)

2. **YouTube Transcription**:
   - Gemini 1.5 Pro (native YouTube support)
   - Whisper API (fallback)

3. **Embeddings**:
   - OpenAI text-embedding-3-large
   - Voyage AI (alternative)

**Cost Estimates** (per content item):
```
Summarization (24-min YouTube video ~4000 tokens):
- Claude Opus: $0.05 per summary
- Claude Sonnet: $0.01 per summary
- Claude Haiku: $0.002 per summary

Embeddings:
- OpenAI: $0.0001 per item

Vector Storage (Pinecone):
- ~$0.05/month per 1000 items

Target: <$0.10 per content item processed
```

---

### **Day 3-4: Chrome Extension - Basic Capture** (Feb 8-9, Sat-Sun)

#### Task 1.5: Chrome Extension Manifest & Structure
**Owner**: Steven
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] Manifest v3 configuration
- [ ] Content script for YouTube detection
- [ ] Popup UI basic structure
- [ ] Background service worker for API calls
- [ ] Extension loads in Chrome successfully

**manifest.json**:
```json
{
  "manifest_version": 3,
  "name": "AI PM Learner",
  "version": "0.1.0",
  "description": "Turn saved content into interview-ready knowledge",
  "permissions": [
    "activeTab",
    "storage",
    "identity"
  ],
  "host_permissions": [
    "https://www.youtube.com/*",
    "https://*.firebaseapp.com/*"
  ],
  "background": {
    "service_worker": "background.js"
  },
  "content_scripts": [
    {
      "matches": ["https://www.youtube.com/*"],
      "js": ["content.js"]
    }
  ],
  "action": {
    "default_popup": "popup.html",
    "default_icon": "icon.png"
  }
}
```

---

#### Task 1.6: YouTube Content Detection & Extraction
**Owner**: Steven
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] Detect when user is on YouTube video page
- [ ] Extract video metadata (title, channel, duration, video ID)
- [ ] Show "Save to AI PM Learner" button overlay
- [ ] Fetch transcript using YouTube API or scraping
- [ ] Handle videos without transcripts gracefully

**Technical Approach**:
```javascript
// content.js - Inject save button on YouTube
function detectYouTubeVideo() {
  const videoId = new URLSearchParams(window.location.search).get('v');
  const title = document.querySelector('h1.ytd-video-primary-info-renderer')?.textContent;
  const channel = document.querySelector('ytd-channel-name a')?.textContent;

  return { videoId, title, channel };
}

// Use YouTube Transcript API or Gemini for transcription
async function getTranscript(videoId) {
  // Option 1: YouTube Transcript API (if available)
  // Option 2: Gemini 1.5 Pro with YouTube URL
  const response = await callGeminiAPI({
    model: "gemini-1.5-pro",
    prompt: `Transcribe this YouTube video: https://youtube.com/watch?v=${videoId}`
  });

  return response.transcript;
}
```

---

#### Task 1.7: Firebase Authentication in Extension
**Owner**: Steven
**Time**: 3 hours
**Acceptance Criteria**:
- [ ] User can sign in with Google OAuth from extension
- [ ] Auth state persists across browser sessions
- [ ] User profile displayed in popup
- [ ] Sign out functionality works
- [ ] Handle auth errors gracefully

**Chrome Extension Auth Flow**:
```javascript
// background.js - Handle OAuth
chrome.identity.getAuthToken({ interactive: true }, function(token) {
  // Exchange token for Firebase custom token
  // Sign in to Firebase
  firebase.auth().signInWithCustomToken(customToken);
});
```

---

### **Day 5-7: AI Summarization & Storage** (Feb 10-12, Mon-Wed)

#### Task 1.8: Cloud Function - Content Processor
**Owner**: Steven
**Time**: 6 hours
**Acceptance Criteria**:
- [ ] Firebase Function `onContentSaved` triggers on new content
- [ ] Calls Claude API for summarization
- [ ] Extracts key takeaways (3-5 bullets)
- [ ] Generates topic tags automatically
- [ ] Identifies difficulty level and prerequisites
- [ ] Stores results back to Firestore
- [ ] Error handling and retries implemented

**Cloud Function**:
```javascript
// functions/src/contentProcessor.js

exports.onContentSaved = functions.firestore
  .document('content/{contentId}')
  .onCreate(async (snap, context) => {
    const content = snap.data();
    const { transcript, title, url } = content.metadata;

    // Get model from Remote Config
    const config = await admin.remoteConfig().getTemplate();
    const model = config.parameters.summarization_model.defaultValue.value;

    // Call Claude API for summarization
    const prompt = `
    You are analyzing content for an AI Product Manager learning tool.

    Content Title: ${title}
    Transcript: ${transcript}

    Provide:
    1. Summary (2-3 sentences capturing core concept)
    2. Key Takeaways (3-5 actionable bullets)
    3. Topics (5-7 relevant tags like #RAG-Architecture, #Vector-Databases)
    4. Difficulty Level (beginner/intermediate/advanced)
    5. Prerequisites (concepts needed to understand this)
    6. Interview-Relevant Points (how to apply in PM interviews)

    Format as JSON.
    `;

    const response = await callClaudeAPI({
      model: model,
      prompt: prompt,
      max_tokens: 1000
    });

    // Update Firestore document
    await snap.ref.update({
      'aiProcessing.summary': response.summary,
      'aiProcessing.keyTakeaways': response.keyTakeaways,
      'aiProcessing.topics': response.topics,
      'aiProcessing.difficulty': response.difficulty,
      'aiProcessing.prerequisites': response.prerequisites,
      'aiProcessing.interviewPoints': response.interviewPoints,
      'updatedAt': admin.firestore.FieldValue.serverTimestamp()
    });
  });
```

---

#### Task 1.9: Extension Popup - Save Flow
**Owner**: Divya (with Steven support)
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] Popup shows video metadata
- [ ] User sees auto-generated tags preview
- [ ] User can add optional notes
- [ ] "Save & Summarize" button triggers save
- [ ] Loading state while processing
- [ ] Success confirmation with link to library
- [ ] Matches ASCII prototype design

**Popup UI** (React component):
```jsx
// popup/SaveContent.jsx
function SaveContent({ videoData }) {
  const [tags, setTags] = useState([]);
  const [notes, setNotes] = useState('');
  const [saving, setSaving] = useState(false);

  const handleSave = async () => {
    setSaving(true);

    // Save to Firestore (triggers Cloud Function)
    await firebase.firestore().collection('content').add({
      userId: currentUser.uid,
      sourceType: 'youtube',
      url: videoData.url,
      title: videoData.title,
      metadata: {
        author: videoData.channel,
        duration: videoData.duration,
        transcript: videoData.transcript
      },
      userAnnotations: {
        notes: notes,
        bookmarked: false
      },
      createdAt: firebase.firestore.FieldValue.serverTimestamp()
    });

    // Show success message
    toast.success('Saved! AI is summarizing...');
  };

  return (
    <div className="popup-container">
      <h2>{videoData.title}</h2>
      <p>📺 {videoData.channel} • {videoData.duration} min</p>

      <div className="auto-tags">
        AI is auto-tagging this as:
        {tags.map(tag => <span className="tag">{tag}</span>)}
      </div>

      <textarea
        placeholder="Your notes (optional)"
        value={notes}
        onChange={(e) => setNotes(e.target.value)}
      />

      <button onClick={handleSave} disabled={saving}>
        {saving ? 'Saving...' : '💾 Save & Summarize'}
      </button>
    </div>
  );
}
```

---

#### Task 1.10: Basic Content Library View (Web App)
**Owner**: Steven
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] React app initialized with Firebase integration
- [ ] User authentication working
- [ ] Display list of saved content items
- [ ] Show AI-generated summaries
- [ ] Basic filtering by topic tags
- [ ] Click to view full content details
- [ ] Hosted on Firebase Hosting

**Simple List View**:
```jsx
// web-app/src/components/ContentLibrary.jsx
function ContentLibrary() {
  const [content, setContent] = useState([]);

  useEffect(() => {
    const unsubscribe = firebase.firestore()
      .collection('content')
      .where('userId', '==', currentUser.uid)
      .orderBy('createdAt', 'desc')
      .onSnapshot(snapshot => {
        const items = snapshot.docs.map(doc => ({
          id: doc.id,
          ...doc.data()
        }));
        setContent(items);
      });

    return unsubscribe;
  }, []);

  return (
    <div className="library">
      <h1>📚 Your Learning Library ({content.length} items)</h1>

      {content.map(item => (
        <ContentCard key={item.id} content={item} />
      ))}
    </div>
  );
}
```

---

### **Sprint 1 Deliverables** (End of Week 1):

✅ **Technical Infrastructure**:
- Firebase project fully configured
- Firestore schema implemented
- Cloud Functions deployed
- Chrome extension installable

✅ **Core Features Working**:
- User can install Chrome extension
- User can sign in with Google
- User can save YouTube video from extension
- AI summarizes content automatically (Claude API)
- User can view saved content in web app

✅ **Validation Checkpoint**:
- Demo to Divya: "Save video → See summary"
- Test with 5 real YouTube videos
- Verify costs are <$0.10 per item
- Confirm quality of AI summaries

**Metrics to Track**:
- Time from save to summary: <30 seconds
- Summary quality: Useful? (Yes/No from Divya)
- Tag accuracy: Relevant? (% of tags that make sense)

---

## 🧠 Sprint 2: Intelligence (Feb 14-20, 2026)

**Theme**: Add the intelligence layer - clustering, learning paths, concept relationships

### Week 2 Goals:
- [ ] Auto-clustering content into topics
- [ ] Concept graph (text-based version)
- [ ] Learning path generator (interview mode)
- [ ] Working prototype end-to-end
- [ ] User validation with test participants

---

### **Day 8-10: Content Clustering & Topics** (Feb 14-16, Fri-Sun)

#### Task 2.1: Embeddings Generation
**Owner**: Steven
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] Generate embeddings for each content item
- [ ] Store embeddings in Pinecone vector database
- [ ] Metadata filtering works (by topic, difficulty)
- [ ] Search functionality returns relevant items
- [ ] Batch processing for existing content

**Pinecone Setup**:
```javascript
// functions/src/embeddings.js
const { PineconeClient } = require('@pinecone-database/pinecone');

exports.generateEmbeddings = functions.firestore
  .document('content/{contentId}')
  .onUpdate(async (change, context) => {
    const after = change.after.data();
    const { summary, topics } = after.aiProcessing;

    // Generate embedding from summary + topics
    const embeddingText = `${summary} ${topics.join(' ')}`;
    const embedding = await getEmbedding(embeddingText);

    // Store in Pinecone
    const pinecone = new PineconeClient();
    await pinecone.init({
      apiKey: process.env.PINECONE_API_KEY,
      environment: 'us-west1-gcp'
    });

    const index = pinecone.Index('aipm-content');
    await index.upsert({
      vectors: [{
        id: context.params.contentId,
        values: embedding,
        metadata: {
          userId: after.userId,
          topics: topics,
          difficulty: after.aiProcessing.difficulty
        }
      }]
    });
  });
```

---

#### Task 2.2: Topic Clustering Algorithm
**Owner**: Steven
**Time**: 6 hours
**Acceptance Criteria**:
- [ ] Group similar content into topic clusters
- [ ] Create topic documents in Firestore
- [ ] Assign meaningful names to clusters (using Claude)
- [ ] Calculate cluster statistics (item count, avg confidence)
- [ ] Update content items with topicId reference
- [ ] Re-run clustering when new content added

**Clustering Approach**:
```javascript
// functions/src/clustering.js
exports.clusterContent = functions.https.onCall(async (data, context) => {
  const userId = context.auth.uid;

  // Get all content for user
  const contentSnapshot = await admin.firestore()
    .collection('content')
    .where('userId', '==', userId)
    .get();

  const contentItems = contentSnapshot.docs.map(doc => ({
    id: doc.id,
    ...doc.data()
  }));

  // Query Pinecone for similar items
  const pinecone = new PineconeClient();
  const index = pinecone.Index('aipm-content');

  // Use DBSCAN or K-means clustering on embeddings
  const clusters = await performClustering(contentItems, index);

  // Generate cluster names using Claude
  for (const cluster of clusters) {
    const topics = cluster.items.flatMap(item => item.aiProcessing.topics);
    const clusterName = await generateClusterName(topics);

    // Create topic document
    await admin.firestore().collection('topics').add({
      userId: userId,
      name: clusterName,
      contentIds: cluster.items.map(item => item.id),
      createdAt: admin.firestore.FieldValue.serverTimestamp()
    });
  }

  return { clustersCreated: clusters.length };
});

async function generateClusterName(topics) {
  const prompt = `
  Given these topic tags from related content: ${topics.join(', ')}

  Generate a concise cluster name (2-4 words) that captures the core theme.
  Examples: "RAG Architecture", "Prompt Engineering", "Production ML Systems"

  Return only the cluster name.
  `;

  const response = await callClaudeAPI({
    model: 'claude-haiku-4-5',  // Cheap model for this
    prompt: prompt,
    max_tokens: 20
  });

  return response.trim();
}
```

---

#### Task 2.3: Concept Graph - Prerequisites & Relationships
**Owner**: Steven
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] Identify prerequisite relationships between topics
- [ ] Store in `topics.conceptGraph` field
- [ ] Query to get learning order (topological sort)
- [ ] Validate no circular dependencies
- [ ] API endpoint to fetch graph structure

**Graph Building**:
```javascript
// functions/src/conceptGraph.js
exports.buildConceptGraph = functions.https.onCall(async (data, context) => {
  const userId = context.auth.uid;

  // Get all topics for user
  const topicsSnapshot = await admin.firestore()
    .collection('topics')
    .where('userId', '==', userId)
    .get();

  const topics = topicsSnapshot.docs.map(doc => ({
    id: doc.id,
    ...doc.data()
  }));

  // Use Claude to identify prerequisites
  for (const topic of topics) {
    const prompt = `
    Given this AI/ML topic: "${topic.name}"

    Which of these topics are prerequisites (foundational concepts needed first)?
    Available topics: ${topics.map(t => t.name).join(', ')}

    Return as JSON array of topic names that are prerequisites.
    If none, return empty array.
    `;

    const response = await callClaudeAPI({
      model: 'claude-sonnet-4-5',
      prompt: prompt,
      max_tokens: 200
    });

    const prerequisiteNames = JSON.parse(response);
    const prerequisiteIds = topics
      .filter(t => prerequisiteNames.includes(t.name))
      .map(t => t.id);

    // Update topic with prerequisites
    await admin.firestore().collection('topics').doc(topic.id).update({
      'conceptGraph.prerequisites': prerequisiteIds
    });
  }

  return { graphBuilt: true };
});
```

---

### **Day 11-12: Learning Path Generator** (Feb 17-18, Mon-Tue)

#### Task 2.4: Interview Mode - Path Generation
**Owner**: Steven
**Time**: 8 hours
**Acceptance Criteria**:
- [ ] User inputs: role, company type, timeline, daily commitment
- [ ] AI analyzes user's saved content to identify gaps
- [ ] Generates day-by-day curriculum from user's content
- [ ] Orders topics by prerequisites (foundational → advanced)
- [ ] Estimates time per item based on duration/difficulty
- [ ] Creates learningPath document in Firestore
- [ ] Returns curriculum structure matching prototype

**Path Generation Logic**:
```javascript
// functions/src/learningPathGenerator.js
exports.generateLearningPath = functions.https.onCall(async (data, context) => {
  const userId = context.auth.uid;
  const { role, companyType, timeline, dailyTimeCommitment } = data;

  // Get user's content and topics
  const content = await getUserContent(userId);
  const topics = await getUserTopics(userId);

  // Calculate available learning time
  const timePerDay = {
    'light': 30,        // minutes
    'moderate': 90,
    'intensive': 180
  }[dailyTimeCommitment];

  const totalMinutes = timeline * timePerDay;

  // Use Claude to analyze gaps and prioritize
  const prompt = `
  You are creating a ${timeline}-day interview prep plan for an AI PM role.

  User's Goal: ${role} at ${companyType} company
  Available Content: ${content.length} items across topics: ${topics.map(t => t.name).join(', ')}
  Daily Time: ${timePerDay} minutes

  Analyze the content and create a day-by-day curriculum that:
  1. Starts with foundational topics (prerequisites first)
  2. Prioritizes interview-critical areas for ${companyType} companies
  3. Identifies gaps where user has no saved content
  4. Balances breadth (system design) vs depth (specific skills)
  5. Includes practice/review days before interview

  For each day, specify:
  - Focus area (e.g., "RAG Architecture")
  - Content items from user's library (use IDs)
  - Estimated time
  - Learning objectives

  Return as JSON in this format:
  {
    "weeks": [
      {
        "weekNumber": 1,
        "focus": "Foundations & Gaps",
        "days": [
          {
            "day": 1,
            "focus": "AI Product Fundamentals",
            "contentIds": ["abc123", "def456"],
            "estimatedTime": 45,
            "objectives": ["Understand AI PM vs Traditional PM", "..."]
          }
        ]
      }
    ],
    "gaps": ["Production ML Systems", "Evaluation Metrics"],
    "strengths": ["RAG Architecture", "Prompt Engineering"]
  }
  `;

  const response = await callClaudeAPI({
    model: 'claude-opus-4-6',  // Use best model for this
    prompt: prompt,
    max_tokens: 3000
  });

  const curriculum = JSON.parse(response);

  // Create learning path document
  const pathRef = await admin.firestore().collection('learningPaths').add({
    userId: userId,
    goal: 'interview',
    parameters: { role, companyType, timeline, dailyTimeCommitment },
    curriculum: curriculum.weeks,
    analysis: {
      gaps: curriculum.gaps,
      strengths: curriculum.strengths
    },
    progress: {
      currentDay: 1,
      completedItems: 0,
      totalItems: curriculum.weeks.flatMap(w => w.days).flatMap(d => d.contentIds).length,
      confidenceScore: 0
    },
    createdAt: admin.firestore.FieldValue.serverTimestamp()
  });

  return { pathId: pathRef.id, curriculum: curriculum };
});
```

---

#### Task 2.5: Learning Path UI (Web App)
**Owner**: Divya (with Steven support)
**Time**: 6 hours
**Acceptance Criteria**:
- [ ] Form to input interview parameters
- [ ] Show AI analysis of user's content (gaps/strengths)
- [ ] Display generated curriculum timeline
- [ ] Progress bar showing completion
- [ ] "Start Learning" button for each day
- [ ] Matches ASCII prototype design

**React Component**:
```jsx
// web-app/src/components/LearningPathGenerator.jsx
function LearningPathGenerator() {
  const [params, setParams] = useState({
    role: 'AI Product Manager',
    companyType: 'ai-native',
    timeline: 14,
    dailyTimeCommitment: 'moderate'
  });
  const [generating, setGenerating] = useState(false);
  const [path, setPath] = useState(null);

  const handleGenerate = async () => {
    setGenerating(true);

    const generatePath = firebase.functions().httpsCallable('generateLearningPath');
    const result = await generatePath(params);

    setPath(result.data);
    setGenerating(false);
  };

  return (
    <div className="path-generator">
      <h1>🎯 Create Learning Path - Interview Mode</h1>

      {/* Input Form */}
      <div className="form">
        <label>What role are you interviewing for?</label>
        <input
          value={params.role}
          onChange={(e) => setParams({...params, role: e.target.value})}
        />

        <label>Company type:</label>
        <select
          value={params.companyType}
          onChange={(e) => setParams({...params, companyType: e.target.value})}
        >
          <option value="ai-native">AI-native (Anthropic, OpenAI)</option>
          <option value="enterprise">Enterprise AI</option>
          <option value="b2b-saas">B2B SaaS + AI</option>
        </select>

        <label>Time until interview: {params.timeline} days</label>
        <input
          type="range"
          min="7"
          max="30"
          value={params.timeline}
          onChange={(e) => setParams({...params, timeline: e.target.value})}
        />

        <button onClick={handleGenerate} disabled={generating}>
          {generating ? 'Generating...' : '🔮 Generate Learning Path'}
        </button>
      </div>

      {/* Generated Path */}
      {path && <LearningPathTimeline curriculum={path.curriculum} />}
    </div>
  );
}
```

---

### **Day 13-14: Working Prototype & Validation** (Feb 19-20, Wed-Thu)

#### Task 2.6: End-to-End Integration
**Owner**: Steven
**Time**: 6 hours
**Acceptance Criteria**:
- [ ] Full flow works: Save → Summarize → Cluster → Generate Path
- [ ] Chrome extension → Web app integration seamless
- [ ] All Firebase Functions deployed to production
- [ ] Error handling and loading states polished
- [ ] Performance acceptable (<3s for most operations)
- [ ] Demo script prepared for user validation

**Integration Checklist**:
```
✅ User Flow 1: Content Capture
   1. Install Chrome extension
   2. Navigate to YouTube video
   3. Click "Save to AI PM Learner"
   4. See auto-generated tags preview
   5. Click "Save & Summarize"
   6. Redirect to web app library
   7. See summarized content within 30s

✅ User Flow 2: Learning Path Creation
   1. User has saved 10+ items
   2. Navigate to "Learning Paths" tab
   3. Select "Interview Preparation"
   4. Fill out interview parameters
   5. Click "Generate Path"
   6. See AI analysis of gaps/strengths
   7. View 14-day curriculum
   8. Click "Start Learning"
   9. See Day 1 content items

✅ User Flow 3: Content Consumption
   1. From learning path, click Day 1
   2. See list of content items for today
   3. Click content item
   4. Read AI summary
   5. View key takeaways
   6. See related content suggestions
   7. Rate confidence (1-5 stars)
   8. Mark as completed
```

---

#### Task 2.7: User Validation Testing
**Owner**: Divya (lead), Steven (support)
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] Test with 3 users (Career Transitioner persona)
- [ ] Run full demo script
- [ ] Collect feedback on:
  - Ease of saving content
  - Quality of AI summaries
  - Relevance of learning path
  - Confidence that this solves their problem
- [ ] Document issues in GitHub
- [ ] Prioritize fixes for Sprint 3

**Test Participants**:
1. Mike (career transitioner - primary persona)
2. Ricardo (continuous builder - secondary persona)
3. Evelyn (continuous builder - secondary persona)

**Validation Questions**:
```
1. Content Capture:
   - "How easy was it to save content?" (1-5)
   - "Did the auto-tags make sense?" (Yes/No)
   - "Would you use this regularly?" (Yes/No)

2. AI Summaries:
   - "Was the summary accurate?" (1-5)
   - "Did it capture the key points?" (Yes/No)
   - "Would you read this vs the full content?" (Yes/No)

3. Learning Path:
   - "Does this path feel personalized to you?" (1-5)
   - "Would this help you prepare for interviews?" (Yes/No)
   - "What's missing?" (Open-ended)

4. Overall:
   - "Would you pay for this?" (Yes/No)
   - "What's the #1 thing we should fix?" (Open-ended)
```

---

### **Sprint 2 Deliverables** (End of Week 2):

✅ **Intelligence Features Working**:
- Content auto-clusters into topics
- Concept graph identifies prerequisites
- Learning path generator creates personalized curriculum
- Interview mode tailors to specific roles/companies

✅ **Working Prototype**:
- Chrome extension → Web app flow complete
- User can save 10+ items and generate learning path
- All core features functional (not polished)

✅ **Validation Complete**:
- Tested with 3 real users
- Feedback documented
- Top 5 issues prioritized for Sprint 3

**Metrics to Track**:
- User satisfaction: ≥3.5/5 on all questions
- "Would you use this?": ≥70% yes
- "Would you pay?": ≥40% yes
- Completion rate: Did all users finish the test?

---

## 🎯 Sprint 3: Personalization (Feb 21-27, 2026)

**Theme**: Add personalization features, refine UX, improve AI quality

### Week 3 Goals:
- [ ] Concept graph visualization (text-based)
- [ ] Confidence tracking and feedback loops
- [ ] Related content recommendations
- [ ] Newsletter/article support (beyond YouTube)
- [ ] Onboarding flow for new users

---

### **Day 15-17: Concept Graph & Visualization** (Feb 21-23, Fri-Sun)

#### Task 3.1: Concept Graph API
**Owner**: Steven
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] API endpoint returns graph structure
- [ ] Includes nodes (topics) and edges (prerequisites/related)
- [ ] Progress data per node (% completed, avg confidence)
- [ ] Recommended next topics based on completion
- [ ] Optimized query (no N+1 queries)

**API Response Format**:
```javascript
// GET /api/conceptGraph?userId={uid}
{
  "nodes": [
    {
      "id": "topic123",
      "name": "RAG Architecture",
      "progress": {
        "totalItems": 12,
        "completedItems": 7,
        "averageConfidence": 3.5,
        "progressPercent": 58
      }
    }
  ],
  "edges": [
    {
      "from": "topic456",  // Vector Databases
      "to": "topic123",    // RAG Architecture
      "type": "prerequisite"
    },
    {
      "from": "topic123",
      "to": "topic789",    // Retrieval Evaluation
      "type": "related"
    }
  ],
  "recommendations": [
    {
      "topicId": "topic789",
      "reason": "Next logical step after RAG Architecture",
      "priority": "high"
    }
  ]
}
```

---

#### Task 3.2: Text-Based Graph Visualization
**Owner**: Divya
**Time**: 6 hours
**Acceptance Criteria**:
- [ ] Display topics in hierarchical tree structure
- [ ] Show progress indicators per topic (●●●○○)
- [ ] Highlight prerequisites vs related topics
- [ ] Click topic to see related content
- [ ] Recommend next topics to study
- [ ] Responsive design (works on mobile)

**Simple Tree View** (save full interactive graph for later):
```jsx
// web-app/src/components/ConceptGraph.jsx
function ConceptGraph({ graphData }) {
  const [selectedTopic, setSelectedTopic] = useState(null);

  return (
    <div className="concept-graph">
      <h1>🗺️ Your AI PM Knowledge Map</h1>

      <div className="graph-tree">
        {graphData.nodes
          .filter(node => node.isRoot)  // Start with foundational topics
          .map(node => (
            <TopicNode
              key={node.id}
              topic={node}
              children={getChildren(node.id, graphData)}
              onClick={() => setSelectedTopic(node)}
            />
          ))}
      </div>

      {/* Recommendations */}
      <div className="recommendations">
        <h2>💡 Recommended Next:</h2>
        {graphData.recommendations.map(rec => (
          <RecommendationCard key={rec.topicId} recommendation={rec} />
        ))}
      </div>

      {/* Selected Topic Details */}
      {selectedTopic && (
        <TopicDetailPanel topic={selectedTopic} />
      )}
    </div>
  );
}

function TopicNode({ topic, children, onClick }) {
  const progress = topic.progress.progressPercent;
  const stars = '●'.repeat(Math.floor(progress / 20)) + '○'.repeat(5 - Math.floor(progress / 20));

  return (
    <div className="topic-node" onClick={onClick}>
      <div className="topic-header">
        <strong>{topic.name}</strong>
        <span className="progress">{stars} {progress}%</span>
      </div>
      <div className="topic-stats">
        {topic.progress.completedItems}/{topic.progress.totalItems} items
      </div>

      {children.length > 0 && (
        <div className="children">
          {children.map(child => (
            <TopicNode key={child.id} topic={child} children={[]} onClick={onClick} />
          ))}
        </div>
      )}
    </div>
  );
}
```

---

### **Day 18-20: Confidence Tracking & Recommendations** (Feb 24-26, Mon-Wed)

#### Task 3.3: Confidence Feedback Loop
**Owner**: Steven
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] After viewing content, user rates confidence (1-5 stars)
- [ ] Prompt: "Could you explain this to an interviewer?"
- [ ] Store rating in `userAnnotations.confidenceRating`
- [ ] Calculate topic average confidence
- [ ] Re-recommend low-confidence topics in learning path
- [ ] Track confidence over time (improvement metric)

**Confidence Rating Component**:
```jsx
// web-app/src/components/ConfidenceRating.jsx
function ConfidenceRating({ contentId, currentRating, onRate }) {
  const [rating, setRating] = useState(currentRating || 0);

  const handleRate = async (stars) => {
    setRating(stars);

    // Update Firestore
    await firebase.firestore().collection('content').doc(contentId).update({
      'userAnnotations.confidenceRating': stars,
      'userAnnotations.ratedAt': firebase.firestore.FieldValue.serverTimestamp()
    });

    onRate(stars);
  };

  return (
    <div className="confidence-check">
      <h3>💭 Confidence Check</h3>
      <p>Could you explain this concept to an interviewer?</p>

      <div className="stars">
        {[1, 2, 3, 4, 5].map(star => (
          <button
            key={star}
            className={star <= rating ? 'filled' : 'empty'}
            onClick={() => handleRate(star)}
          >
            ⭐
          </button>
        ))}
      </div>

      <div className="labels">
        <span>Not yet</span>
        <span>Confidently</span>
      </div>
    </div>
  );
}
```

---

#### Task 3.4: Related Content Recommendations
**Owner**: Steven
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] When viewing content, show 3-5 related items
- [ ] Use vector similarity search (Pinecone)
- [ ] Filter by same topic cluster
- [ ] Prioritize unseen content
- [ ] Display with relevance score
- [ ] "View in context" shows position in concept graph

**Recommendation Engine**:
```javascript
// functions/src/recommendations.js
exports.getRelatedContent = functions.https.onCall(async (data, context) => {
  const { contentId, userId } = data;

  // Get content embedding from Pinecone
  const pinecone = new PineconeClient();
  const index = pinecone.Index('aipm-content');

  // Query for similar items
  const queryResponse = await index.query({
    id: contentId,
    topK: 10,
    filter: { userId: userId },
    includeMetadata: true
  });

  // Get content details from Firestore
  const relatedIds = queryResponse.matches.map(m => m.id);
  const relatedContent = await Promise.all(
    relatedIds.map(id =>
      admin.firestore().collection('content').doc(id).get()
    )
  );

  // Filter out already-completed items (prioritize unseen)
  const recommendations = relatedContent
    .filter(doc => !doc.data().userAnnotations.completedAt)
    .slice(0, 5)
    .map(doc => ({
      id: doc.id,
      ...doc.data(),
      relevanceScore: queryResponse.matches.find(m => m.id === doc.id).score
    }));

  return { recommendations };
});
```

---

### **Day 21: Newsletter/Article Support** (Feb 27, Thu)

#### Task 3.5: Article Capture (Beyond YouTube)
**Owner**: Steven
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] Extension detects when on article page (Medium, Substack, blogs)
- [ ] Extract article text using readability parser
- [ ] Same summarization flow as YouTube
- [ ] Support for newsletter emails (forward to special email address)
- [ ] Test with 5 different article sources

**Content Detection**:
```javascript
// extension/content.js - Detect article pages
function detectContentType() {
  const url = window.location.href;

  // YouTube video
  if (url.includes('youtube.com/watch')) {
    return { type: 'youtube', data: extractYouTubeData() };
  }

  // Medium article
  if (url.includes('medium.com') && document.querySelector('article')) {
    return { type: 'article', data: extractArticleData() };
  }

  // Substack
  if (url.includes('substack.com') && document.querySelector('.post')) {
    return { type: 'article', data: extractArticleData() };
  }

  // Generic article (use readability heuristics)
  const article = document.querySelector('article') ||
                  document.querySelector('main') ||
                  document.querySelector('.post-content');

  if (article && article.textContent.length > 500) {
    return { type: 'article', data: extractArticleData() };
  }

  return null;
}

function extractArticleData() {
  const title = document.querySelector('h1')?.textContent ||
                document.querySelector('title')?.textContent;

  const author = document.querySelector('[rel="author"]')?.textContent ||
                 document.querySelector('.author')?.textContent;

  // Use Readability.js to extract clean content
  const reader = new Readability(document.cloneNode(true));
  const article = reader.parse();

  return {
    title: title,
    author: author,
    content: article.textContent,
    url: window.location.href
  };
}
```

---

### **Sprint 3 Deliverables** (End of Week 3):

✅ **Personalization Features**:
- Concept graph visualization (text-based tree)
- Confidence tracking with star ratings
- Related content recommendations
- Newsletter/article support (beyond YouTube)

✅ **UX Improvements**:
- Onboarding flow for new users
- Better loading states and error messages
- Responsive design (works on mobile)

✅ **Quality Improvements**:
- AI summaries more accurate (tested with 20+ items)
- Clustering more meaningful (validated topic names)
- Learning paths better tailored (incorporated user feedback)

---

## ✨ Sprint 4: Polish (Feb 28-Mar 6, 2026)

**Theme**: User testing, bug fixes, landing page, launch prep

### Week 4 Goals:
- [ ] User testing with 5+ participants
- [ ] Bug fixes and UX polish
- [ ] Landing page with positioning
- [ ] Analytics instrumentation
- [ ] Launch plan finalized

---

### **Day 22-24: User Testing Round 2** (Feb 28-Mar 2, Fri-Sun)

#### Task 4.1: Expanded User Testing
**Owner**: Divya (lead)
**Time**: 8 hours
**Acceptance Criteria**:
- [ ] Test with 5 users (mix of personas)
- [ ] Observe full onboarding → learning path flow
- [ ] Collect quantitative + qualitative feedback
- [ ] Video recordings of sessions
- [ ] Prioritized bug/feedback list
- [ ] Success criteria: ≥4/5 on key metrics

**Test Protocol**:
```
Participants:
1. Mike (Career Transitioner - primary persona)
2. New user from same persona (blind test)
3. Ricardo (Continuous Builder)
4. Evelyn (Continuous Builder)
5. Jordan simulation (Aspiring Specialist)

Tasks:
1. Install Chrome extension (observe any confusion)
2. Save 5 pieces of content (YouTube + articles)
3. Review AI summaries (do they make sense?)
4. Create learning path for interview prep
5. Complete Day 1 of learning path
6. Rate confidence on 2 topics
7. Explore concept graph

Metrics:
- Task completion rate (% who finish all tasks)
- Time to first save (<2 min target)
- Time to learning path creation (<10 min target)
- Satisfaction scores (1-5 on each feature)
- Would recommend? (Yes/No)
- Willingness to pay ($X/month)
```

---

### **Day 25-26: Bug Fixes & UX Polish** (Mar 3-4, Mon-Tue)

#### Task 4.2: Top 10 Bug Fixes
**Owner**: Steven
**Time**: 8 hours
**Acceptance Criteria**:
- [ ] All P0 bugs from testing resolved
- [ ] Error messages user-friendly
- [ ] Loading states consistent
- [ ] Edge cases handled (no content, no topics, etc.)
- [ ] Performance optimizations (lazy loading, caching)

**Common Issues to Fix**:
```
1. Extension doesn't detect YouTube videos on first load
2. Summarization fails for very long videos (>1 hour)
3. Learning path generation times out for users with 50+ items
4. Confidence ratings don't update topic progress immediately
5. Concept graph doesn't show for users with <5 topics
6. Mobile web app layout breaks on small screens
7. Sign-in redirect loops in some browsers
8. Related content shows duplicates
9. Clustering creates too many small clusters
10. Article extraction fails for paywalled content
```

---

#### Task 4.3: Onboarding Flow
**Owner**: Divya
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] First-time user sees welcome tour
- [ ] Explain core value prop in 3 steps
- [ ] Guide through first content save
- [ ] Prompt to create learning path after 5+ saves
- [ ] Skip button for power users
- [ ] Track onboarding completion rate

**Onboarding Steps**:
```
Step 1: Welcome
"Learn for the future, not the hype.
Turn your saved AI PM content into interview-ready knowledge."

Step 2: How It Works
"1. Save content from YouTube, newsletters, articles
 2. AI summarizes and clusters your learning
 3. Generate personalized learning paths for your goals"

Step 3: First Save
"Let's save your first piece of content!
Install the Chrome extension and click 'Save' on any YouTube video."

Step 4: Learning Path (after 5+ saves)
"Great! You've saved 5 items.
Ready to create your personalized learning path?"
```

---

### **Day 27-28: Landing Page & Launch Prep** (Mar 5-6, Wed-Thu)

#### Task 4.4: Landing Page
**Owner**: Steven (build), Divya (copy)
**Time**: 8 hours
**Acceptance Criteria**:
- [ ] Clear value proposition above the fold
- [ ] Addresses 3 personas pain points
- [ ] Social proof (user testimonials from testing)
- [ ] "Install Extension" CTA
- [ ] Demo video or screenshots
- [ ] Hosted on Firebase Hosting
- [ ] SEO optimized (title, meta description)

**Landing Page Structure**:
```
=== HERO ===
Headline: "Learn for the future, not the hype"
Subheadline: "Turn 87 saved posts into interview-ready knowledge in 14 days"
CTA: [Install Chrome Extension] [Watch Demo]
Visual: Screenshot of learning path timeline

=== PROBLEM ===
"Are you an AI PM learner who..."
❌ Saves content but never reads it again? (87 LinkedIn posts in the graveyard)
❌ Consumes 10-15 hours/week but still feels behind?
❌ Can't find that article you saved when you need it for an interview?

=== SOLUTION ===
"AI PM Learner turns your content chaos into structured learning"
✅ Auto-summarize and cluster your saved content by topic
✅ Generate personalized learning paths for interviews, projects, or mastery
✅ See how concepts connect with an AI-powered knowledge graph

=== HOW IT WORKS ===
[3-step visual with screenshots]
1. Save content with one click (Chrome extension)
2. AI summarizes and organizes (Claude-powered)
3. Learn with personalized paths (Interview mode)

=== SOCIAL PROOF ===
"I went from 87 saved posts I never read to a 14-day interview prep plan
that actually uses MY content. Failed my last interview, but I'm confident
about the next one." - Mike, Career Transitioner

=== FEATURES ===
📚 Smart Content Library - Never lose a saved post again
🗺️ Concept Graph - See how topics connect
🎯 Learning Paths - Interview mode, project mode, mastery mode
💭 Confidence Tracking - Know what you actually understand
💬 AI Chat - Ask questions about YOUR content, not generic ChatGPT

=== PRICING (FUTURE) ===
Free during beta - Limited to 50 content items
Pro: $15/month - Unlimited content + advanced features

=== CTA ===
"Ready to turn content overload into confident learning?"
[Install Chrome Extension - It's Free]
```

---

#### Task 4.5: Analytics Instrumentation
**Owner**: Steven
**Time**: 3 hours
**Acceptance Criteria**:
- [ ] Track key user events (sign up, save content, create path, etc.)
- [ ] Funnel analysis (save → cluster → path → complete)
- [ ] Retention cohorts (Day 1, Day 7, Day 30)
- [ ] Performance monitoring (Cloud Functions latency)
- [ ] Error tracking (Sentry or similar)
- [ ] Dashboard in Firebase Analytics

**Key Events to Track**:
```javascript
// Analytics events
const EVENTS = {
  // Acquisition
  EXTENSION_INSTALLED: 'extension_installed',
  USER_SIGNED_UP: 'user_signed_up',

  // Activation
  FIRST_CONTENT_SAVED: 'first_content_saved',
  REACHED_5_ITEMS: 'reached_5_items',

  // Engagement
  CONTENT_SAVED: 'content_saved',
  SUMMARY_VIEWED: 'summary_viewed',
  CONFIDENCE_RATED: 'confidence_rated',

  // Value
  LEARNING_PATH_CREATED: 'learning_path_created',
  LEARNING_PATH_DAY_COMPLETED: 'learning_path_day_completed',

  // Retention
  RETURNED_DAY_7: 'returned_day_7',
  RETURNED_DAY_30: 'returned_day_30'
};

// Track in Firebase
firebase.analytics().logEvent(EVENTS.CONTENT_SAVED, {
  source_type: 'youtube',
  user_tenure_days: 5
});
```

---

#### Task 4.6: Launch Plan
**Owner**: Divya (lead), Steven (support)
**Time**: 4 hours
**Acceptance Criteria**:
- [ ] Define launch channels (Twitter, LinkedIn, Product Hunt)
- [ ] Beta user recruitment plan (target 50 users in Week 1)
- [ ] Support process (Discord, email, in-app chat)
- [ ] Pricing strategy (free tier vs pro)
- [ ] Roadmap communicated (what's next after MVP)
- [ ] Press kit (screenshots, logo, description)

**Launch Checklist**:
```
Pre-Launch (Day -3):
- [ ] Soft launch to 10 beta users (existing research participants)
- [ ] Monitor for critical bugs
- [ ] Collect initial feedback

Launch Day (Mar 6):
- [ ] Publish landing page
- [ ] Submit to Chrome Web Store
- [ ] Post on Twitter, LinkedIn (Steven + Divya personal accounts)
- [ ] Email course participants (Aman's students)
- [ ] Post in AI PM communities (Discord, Slack)

Week 1 Post-Launch:
- [ ] Daily check-ins with early users
- [ ] Fix critical bugs within 24 hours
- [ ] Product Hunt launch (Day 3)
- [ ] Collect testimonials

Week 2 Post-Launch:
- [ ] Analyze metrics (activation, engagement, retention)
- [ ] User interviews with active users (what's working?)
- [ ] Prioritize roadmap for next sprint
```

---

### **Sprint 4 Deliverables** (End of Week 4):

✅ **Launch-Ready Product**:
- User tested with 5+ participants
- Top bugs fixed and UX polished
- Landing page live with clear positioning
- Analytics tracking key metrics

✅ **Go-to-Market**:
- Beta user recruitment plan
- Launch channels identified
- Support process defined
- Initial users onboarded

✅ **Success Metrics Defined**:
- Activation: 60% save 5+ items in Week 1
- Engagement: 40% create learning path
- Value: 30% complete Day 1 of path
- Retention: 50% return in Week 2

---

## Post-MVP Roadmap (Week 5+)

### **Sprint 5: Iteration Based on Data** (Mar 7-13)

**Focus**: Analyze MVP metrics and iterate on highest-leverage improvements

**Potential Priorities** (TBD based on data):
1. If activation is low → Improve onboarding
2. If engagement is low → Better learning path UX
3. If value is low → Improve AI summary quality
4. If retention is low → Add daily notifications/reminders

---

### **Sprint 6: Advanced Features** (Mar 14-20)

**Potential Features** (based on user feedback):
- Interactive concept graph visualization (D3.js)
- Spaced repetition for confidence tracking
- Team/cohort learning (share learning paths)
- Mobile app (React Native)
- API for integrations (Notion, Obsidian)

---

## Technical Architecture Reference

### **Tech Stack**

**Frontend**:
- Chrome Extension: Vanilla JS (lightweight)
- Web App: React 18 + Firebase SDK
- Styling: Tailwind CSS
- State Management: React Context + Firebase Realtime

**Backend**:
- Firebase Authentication (Email, Google OAuth)
- Cloud Firestore (NoSQL database)
- Cloud Functions (Node.js serverless)
- Firebase Hosting (static site hosting)
- Firebase Remote Config (dynamic model selection)

**AI/ML**:
- Anthropic Claude API (summarization, clustering, path generation)
- OpenAI Embeddings API (text-embedding-3-large)
- Pinecone Vector Database (semantic search)
- Gemini API (YouTube transcription - optional)

**DevOps**:
- GitHub (version control)
- Firebase CLI (deployment)
- Firebase Analytics (product metrics)
- Sentry (error tracking)

---

### **Cost Estimates**

**MVP (First 100 Users, 50 items each)**:
```
AI Processing:
- Summarization: 5,000 items × $0.01 = $50
- Embeddings: 5,000 items × $0.0001 = $0.50
- Learning path generation: 100 users × $0.05 = $5

Infrastructure:
- Pinecone: 5,000 vectors × $0.05/1000/month = $0.25/month
- Firebase: Free tier (sufficient for MVP)
- Hosting: Free tier

Total Monthly: ~$60 for 100 users = $0.60 per user
```

**Post-MVP Optimization** (with Remote Config):
```
- Switch to Haiku for simple summarization → $0.002 per item
- Reduces cost to $0.20 per user per month
- Still profitable at $15/month pricing
```

---

## Risk Mitigation

### **Technical Risks**

**Risk 1: AI costs spiral out of control**
- Mitigation: Firebase Remote Config for live model switching
- Fallback: Use cheaper models (Haiku) for non-critical operations
- Monitor: Set up cost alerts at $100/day threshold

**Risk 2: YouTube transcription unreliable**
- Mitigation: Test Gemini API early (Day 1-2)
- Fallback: Use Whisper API or require manual paste
- Alternative: Start with articles/newsletters only

**Risk 3: Clustering quality poor**
- Mitigation: Test with 50+ real items from Steven's saved content
- Fallback: Manual topic assignment with AI suggestions
- Alternative: Use simple tag-based grouping

**Risk 4: Learning path generation too slow (>30s)**
- Mitigation: Pre-compute common templates, personalize on top
- Fallback: Use Haiku model (faster, cheaper)
- Alternative: Progressive generation (Week 1 first, then Week 2)

---

### **Product Risks**

**Risk 1: Users don't save enough content (need 10+ for value)**
- Mitigation: Onboarding guides first save, prompt at 5 items
- Fallback: Seed with recommended content for their role
- Alternative: Lower threshold to 5 items for learning path

**Risk 2: AI summaries not accurate/useful**
- Mitigation: Test with 20+ items in Sprint 1, iterate prompts
- Fallback: Allow user editing of summaries
- Alternative: Show original content alongside summary

**Risk 3: Users don't trust AI-generated learning paths**
- Mitigation: Show reasoning ("You have gaps in X, strengths in Y")
- Fallback: Allow manual editing of curriculum
- Alternative: Hybrid: AI suggests, user approves each day

**Risk 4: Chrome extension approval delayed**
- Mitigation: Submit early (Day 10), plan for 5-7 day review
- Fallback: Direct download from website (during beta)
- Alternative: Bookmarklet version (no installation needed)

---

### **Team Risks**

**Risk 1: Steven blocked on Divya's Cursor subscription**
- Mitigation: Divya upgrades by Feb 8 (Day 2)
- Fallback: Steven builds alone, Divya tests
- Alternative: Use free tier for prototyping

**Risk 2: Scope creep delays MVP launch**
- Mitigation: Ruthlessly prioritize P0 features only
- Rule: If not required for demo, it's not in MVP
- Alternative: Launch with less features (YouTube only)

**Risk 3: User testing participants unavailable**
- Mitigation: Recruit 10 participants (plan for 50% dropout)
- Fallback: Steven + Divya use product themselves
- Alternative: Reddit/Twitter recruitment

---

## Success Criteria (MVP Launch)

### **Must Have (P0)**
- [ ] Chrome extension published and installable
- [ ] User can save YouTube video in <30 seconds
- [ ] AI summarizes content in <60 seconds
- [ ] Content auto-clusters into topics
- [ ] User can generate 14-day interview learning path
- [ ] Landing page live with "Install Extension" CTA
- [ ] 5 beta users successfully onboarded

### **Should Have (P1)**
- [ ] Article/newsletter support (beyond YouTube)
- [ ] Concept graph visualization (text-based)
- [ ] Confidence tracking with star ratings
- [ ] Related content recommendations
- [ ] Mobile-responsive web app

### **Could Have (P2)**
- [ ] Interactive concept graph (visual)
- [ ] AI chat for Q&A
- [ ] Progress tracking over time
- [ ] Social sharing of learning paths
- [ ] Export to Notion/Obsidian

---

## Metrics to Track (Week 1-4)

### **Activation** (Week 1 Goal: 60%)
- % users who save 5+ items in first week
- Time to first save (<2 min target)
- Extension install → first save conversion

### **Engagement** (Week 2 Goal: 40%)
- % users who create learning path
- % users who complete Day 1 of path
- Daily active users (DAU)

### **Value** (Week 3 Goal: 30%)
- % users who rate confidence ≥3 stars
- % users who complete full learning path
- User testimonials collected

### **Retention** (Week 4 Goal: 50%)
- Day 7 retention
- Day 30 retention
- Returning users per week

### **Quality**
- AI summary accuracy (1-5 rating)
- Learning path relevance (1-5 rating)
- Bug reports per user
- Support requests per user

---

## Communication & Collaboration

### **Daily Standup** (Async)
- What I did yesterday
- What I'm doing today
- Any blockers

**Format**: GitHub Discussion or Slack thread

---

### **Weekly Sync** (Fridays, 1 hour)
- Demo progress
- Review metrics
- Prioritize next week
- Align on decisions

**Agenda Template**:
```
1. Wins this week (5 min)
2. Demo working features (15 min)
3. Review user feedback (10 min)
4. Metrics check (10 min)
5. Blockers and decisions (10 min)
6. Next week priorities (10 min)
```

---

### **Decision Log**
- Document key decisions in `/docs/decisions.md`
- Format: Date, Decision, Reasoning, Alternatives Considered

**Example**:
```
2026-02-08: Use Gemini for YouTube transcription
Reasoning: Native YouTube support, better quality than Whisper
Alternatives: Whisper API (fallback), Manual paste (too manual)
Owner: Steven
```

---

## Next Steps (Immediate)

### **Steven (This Weekend - Feb 8-9)**
1. Create product development repository
2. Set up Firebase project
3. Design and validate Firestore schema
4. Benchmark Claude models for summarization
5. Start Chrome extension structure

### **Divya (This Weekend - Feb 8-9)**
1. ✅ Upgrade Cursor subscription (BLOCKER)
2. Review Aman's course (initial sessions)
3. Experiment with Chrome extension development
4. Draft landing page copy using positioning doc
5. Recruit 5 user testing participants

### **Both (Next Sync - Feb 13)**
1. Demo: Save YouTube video → See summary
2. Review progress against Sprint 1 goals
3. Align on Sprint 2 priorities
4. Decide: On track for Feb 20 prototype?

---

## Appendix

### **Useful Resources**

**Firebase**:
- [Firebase Docs](https://firebase.google.com/docs)
- [Firestore Data Modeling](https://firebase.google.com/docs/firestore/data-model)
- [Cloud Functions Guide](https://firebase.google.com/docs/functions)

**Chrome Extension**:
- [Manifest V3 Guide](https://developer.chrome.com/docs/extensions/mv3/)
- [Content Scripts](https://developer.chrome.com/docs/extensions/mv3/content_scripts/)
- [Extension Architecture](https://developer.chrome.com/docs/extensions/mv3/architecture-overview/)

**AI APIs**:
- [Anthropic Claude API](https://docs.anthropic.com/claude/reference/getting-started-with-the-api)
- [OpenAI Embeddings](https://platform.openai.com/docs/guides/embeddings)
- [Pinecone Quickstart](https://docs.pinecone.io/docs/quickstart)

**Product Strategy**:
- `Knowledge/Specs/product-strategy-and-architecture.pdf`
- `Knowledge/Specs/ui-prototypes-ascii.md`
- `Knowledge/Research/product-user-personas.md`

---

**Last Updated**: February 6, 2026
**Status**: READY TO START
**Next Milestone**: Working Prototype (February 20, 2026)

---

*"Learn for the future, not the hype. Let's ship this."* 🚀
