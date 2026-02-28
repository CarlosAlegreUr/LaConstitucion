# Context Windows and Attention Mechanisms

## Resumen
Context window = how much text the LLM can "see" at once. Understanding this is critical for agent design because it's your fundamental resource constraint.

## Prerrequisitos
- transformer-architecture-overview (attention mechanism)

## Explicación
[Will be expanded when studied]

**What is a context window?**
Maximum number of tokens (words/sub-words) the model can process in one request.

**Current state (2025):**
- GPT-4: 8k-128k tokens depending on version
- Claude: 200k tokens
- Gemini: 1M tokens (experimental)
- Open source (Llama 3): 8k-128k

**Why is there a limit?**
Attention mechanism is O(n²) in sequence length:
- For each token, model attends to every other token
- Double the context → 4x the computation
- This is the quadratic wall you mentioned

**Practical implications for agents:**
1 token ≈ 0.75 words (English)
- 1k tokens ≈ 750 words
- 10k tokens ≈ 7,500 words (small book chapter)
- 100k tokens ≈ 75,000 words (short novel)
- 200k tokens ≈ 150,000 words (decent-sized textbook)

**Agent design challenge:**
If your agent conversation goes long, context fills up:
- System prompt: 2k tokens
- Tool descriptions: 5k tokens
- Conversation history: grows unbounded
- Retrieved documents: variable
→ Eventually hits limit

**Solutions (covered in other concepts):**
- **Compression**: Summarize old messages
- **Forgetting**: Drop old context
- **RAG**: Don't put everything in context, retrieve on-demand
- **Fresh context agents**: Start new conversation
- **Hierarchical memory**: Store in external DB, load selectively

**Your Little Cheerful insight:**
You correctly identified that loading full context wastes reasoning tokens. Tree structure + selective loading = efficient use of context window.

## Nivel de Profundidad: 3
Technical understanding + practical optimization

## Fuentes de Verdad
- "Attention Is All You Need" (Vaswani et al., 2017) - quadratic complexity
- Anthropic's "Long Context Windows in Production" blog post
- Various model cards (GPT-4, Claude, Llama) for current limits

## Tags
None yet - will be assigned after study
