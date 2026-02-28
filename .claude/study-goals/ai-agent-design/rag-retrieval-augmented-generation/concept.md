# RAG: Retrieval-Augmented Generation

## Resumen
RAG = "JIT data fetching" (as you called it). Instead of putting everything in the prompt, retrieve only relevant information when needed. Solves knowledge cutoff problem and context exhaustion.

## Prerrequisitos
- knowledge-cutoff-problem (understanding why LLMs don't know recent info)

## Explicación
[Will be expanded when studied]

**The problem RAG solves:**
- LLMs trained on data up to cutoff date (e.g., January 2025 for Claude)
- Context windows are limited (even with 200k tokens, can't fit entire Wikipedia)
- Hallucination increases when LLM doesn't know something

**How RAG works:**
1. User asks a question
2. Agent searches external knowledge base (vector DB, web, files)
3. Agent retrieves top-k most relevant chunks
4. Agent puts retrieved info in prompt
5. Agent generates answer grounded in retrieved data

**Your Little Cheerful uses RAG:**
- When studying presidencialismo-eeuu, you didn't put entire US Constitution in memory
- You fetched it on-demand when needed
- You read concept.md files only when studying that concept
- This is RAG - retrieve what you need, when you need it

**Classic RAG pipeline:**
```
Query → Embed → Search Vector DB → Retrieve Top-K → Inject in Prompt → Generate
```

**Trade-offs:**
- **Pro**: Massively reduces context usage, adds real-time knowledge
- **Con**: Retrieval might fetch wrong info (garbage in, garbage out)
- **Con**: Adds latency (search + embed + retrieve before generation)

## Nivel de Profundidad: 3
Academic papers + practical implementations

## Fuentes de Verdad
- "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks" (Lewis et al., 2020)
- LangChain RAG tutorial
- Pinecone/Weaviate/Chroma documentation (vector DB providers)

## Tags
None yet - will be assigned after study
