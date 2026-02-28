# AI Agent Design - Study Notes

**Goal:** Learn all weak spots of base LLMs and how agentic systems fix them, with focus on improving Little Cheerful.

**Started:** 2026-01-02
**Progress:** 4/40 concepts studied (10%)

---

## Session 1: Foundational Patterns (2026-01-02)

### Concepts Studied

1. **hierarchical-memory**
2. **memory-retrieval-strategies**
3. **rag-retrieval-augmented-generation**
4. **fresh-vs-inherited-context**

---

## Key Insights

### 1. Hierarchical Memory (Already Built)

**What I discovered:** I independently built hierarchical memory in Little Cheerful's tree.json before knowing the academic term.

**Core insight:** Knowledge isn't a flat list - it's a graph with parent/child relationships. Concepts build on each other.

**My implementation:**
```json
"concept-x": {
  "parent": "prerequisite-concept",
  "children": ["enabled-concept-1", "enabled-concept-2"]
}
```

**Accidental win:** By calling it "tree" but allowing multiple relationships, I actually built a directed graph (DAG). Knowledge has cycles - I recognized this early.

**Academic equivalent:** Semantic networks, knowledge graphs, taxonomic hierarchies.

---

### 2. Memory Retrieval Strategies (BFS by Accident)

**What I discovered:** I accidentally implemented Breadth-First Search (BFS) with depth limit by thinking in "tree family relations."

**My algorithm:**
```
When studying concept X:
1. Load concept X
2. Load parent (prerequisite)
3. Load children (what this enables)
4. Stop (don't traverse entire tree)
```

**Why it works:** Bounded context (predictable tokens) + relevant context (parents = prereqs, children = motivation).

**Academic name:** k-hop neighborhood retrieval (k=1 or k=2)

**6 Formal Strategies:**
1. **Local BFS** (my current) - concept + parent + children
2. **DFS to root** - entire ancestry chain
3. **Sibling expansion** - add lateral concepts (for creativity)
4. **Semantic search** - ignore structure, find by meaning
5. **Adaptive** - ask user what they know, adjust retrieval
6. **Working memory** - cache recently-used concepts

**Trade-off identified:**
- **Depth (BFS)** = Focus, efficiency
- **Breadth (siblings)** = Creativity, cross-pollination (piano example: physical exercises ↔ music theory)

**Potential Little Cheerful improvements:**
- Add "focus mode" vs "exploratory mode" toggle
- Exploratory mode includes siblings for lateral thinking
- Pre-session knowledge check to skip known prerequisites

---

### 3. RAG = Virtual Memory for LLMs

**What I discovered:** I called it "JIT data fetching" - that's Retrieval-Augmented Generation (RAG).

**The analogy that clicked:**

| Computer Memory | LLM Memory |
|-----------------|-----------|
| RAM (fast, limited) | Context window |
| Disk (slow, unlimited) | External knowledge base |
| Virtual memory | RAG |
| Page table | Vector index |
| Page fault | Retrieval event |

**Why RAG beats alternatives:**
- **vs Retraining daily:** Too expensive (electricity, time, data sourcing)
- **vs Infinite context:** Wastes resources, might loop forever
- **RAG:** Middle ground - small model + fetch on demand

**Full RAG pipeline:**
```
Query → Embed → Search → Retrieve (top-k) → Re-rank → Inject → Generate
```

**Little Cheerful's simplified RAG:**
```
Concept name → Direct file read → Inject → Generate
```

**Why simplified version works:**
- Curated knowledge base (I control quality)
- Explicit structure (no ambiguous search)
- User selects concept (no query interpretation)

**Semantic search clarification:**
- **What I have:** Manual links via children array (strings)
- **Semantic search:** Convert concepts to 768-dim vectors, find by cosine similarity
- **Do I need it?** No. Only useful for open-ended queries or 1000+ concept bases.

**When I'd need full RAG:**
- "Find concepts related to [vague user description]"
- Auto-suggest based on user struggles
- Fetching from unstructured sources (internet)

---

### 4. Fresh vs Inherited Context

**Decision framework:** Think about features and how they behave at context limits.

**Fresh Context Agent:**
- Starts with clean slate
- Gets explicit instructions
- **Use when:** Task is independent, context would confuse, security isolation needed

**Inherited Context Agent:**
- Sees parent conversation history
- Implicit understanding
- **Use when:** Task needs conversation context, continuing work, session summaries

**Practical examples:**

| Task | Context Type | Reasoning |
|------|-------------|-----------|
| Fetch & summarize primary source | Fresh | Independent task, explicit instructions work |
| Generate practice problems (general) | Fresh | Don't need user's specific context |
| Generate practice problems (targeted) | Inherited | Need to know user's weaknesses |
| Write session summary | Inherited | Must see entire conversation |
| Security-sensitive operations | Fresh | Don't leak API keys/personal data |

**Optimization for session summaries:** Compress first, then inherit. Summarize conversation detailedly/losslessly → then write summary. Only needed near context limits.

**Trade-offs:**

| Aspect | Fresh | Inherited |
|--------|-------|-----------|
| Token cost | Low | High (carries parent) |
| Clarity | Explicit needed | Implicit understanding |
| Isolation | Perfect | None |
| Relevance | Focused | Might get distracted |

---

## Meta-Insights

### What I Already Knew (Reverse-Engineered)
- LLMs = statistical pattern predictors
- Context windows = local optimization of general function
- Memory persistence (RAM vs disk analogy)
- Token efficiency (reasoning vs storage trade-off)
- Tool selection overhead
- JIT data fetching (RAG)

### What I Learned Today
- Academic names for patterns I discovered (hierarchical memory, RAG, BFS, k-hop retrieval)
- Formal decision frameworks (when to use which strategy)
- Trade-off analysis (depth vs breadth, fresh vs inherited)
- Virtual memory analogy for RAG (clicked perfectly)
- Semantic search vs explicit structure (vectors vs links)

### Design Philosophy Reinforced
> "The baseline is thinking in features and how they behave at context limits."

Everything in agent design is resource management under constraints. This is the correct mental model.

---

## Little Cheerful: Current State Assessment

**What works well (don't change):**
- Tree structure with parent/child links (actually a DAG)
- BFS depth=1 retrieval (efficient, focused)
- Simplified RAG (explicit file reads, no search ambiguity)
- Curated knowledge base (quality control)

**Potential improvements (not urgent):**
1. Add "exploratory mode" that includes siblings (lateral thinking)
2. Pre-session knowledge check (skip known prerequisites)
3. Session memory cache (keep recently-studied concepts hot)
4. Compression before session summary (near context limits)
5. Version control with Git (stop using multiple folders)

**What NOT to add:**
- Semantic search (overkill for structured learning)
- Full RAG pipeline (curated sources are better)
- Vector embeddings (manual links work fine)

---

## Next Priorities (Tier 1 Remaining)

5. **version-control-for-agents** - Stop using folders, use Git
6. **eval-datasets-metrics** - Test if Little Cheerful actually works
7. **context-exhaustion-solutions** - Handle long sessions
8. **memory-compression-summarization** - Compress session.md
9. **cost-optimization-tokens** - Make cheaper to run
10. **latency-optimization** - Make faster

Then move to Tier 2 (Advanced Patterns).

---

## Concepts Mastered

| Concept | Tags | Notes |
|---------|------|-------|
| hierarchical-memory | intuitive, can-apply | Already built this |
| memory-retrieval-strategies | intuitive, can-apply | Accidentally built BFS |
| rag-retrieval-augmented-generation | intuitive, can-apply | Called it "JIT data fetching" |
| fresh-vs-inherited-context | intuitive, can-apply | Context as resource constraint |

---

**Next session:** Continue with version-control-for-agents or concept of my choice.
