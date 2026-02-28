# Hallucination: Types and Causes

## Resumen
Why do LLMs make up facts, citations, and code that doesn't exist? Understanding the root causes helps you design agents that minimize hallucination.

## Prerrequisitos
- training-vs-inference (understanding LLMs can't "learn" at runtime)

## Explicación
[Will be expanded when studied]

**What is hallucination?**
LLM generates plausible-sounding content that is factually wrong or doesn't exist.

**Types of hallucination:**
1. **Factual errors**: "The Eiffel Tower was built in 1920" (wrong date)
2. **Fabricated citations**: References to papers that don't exist
3. **Invented APIs/functions**: Code using methods that don't exist
4. **Contradictory statements**: Says X in one paragraph, NOT X later
5. **Out-of-distribution extrapolation**: Confidently answers about things it has no data on

**Root causes:**
1. **Statistical nature**: LLM predicts next likely token, not next TRUE token
2. **Training data quality**: Errors in training data → errors in outputs
3. **Lack of grounding**: No connection to real-time truth source
4. **Reinforcement of plausibility**: RLHF optimizes for "sounds good", not "is true"
5. **Pressure to complete**: Model prefers generating something over saying "I don't know"

**Why "you know this is wrong, right?" often works:**
- Model has uncertainty across multiple possible completions
- When you challenge it, you shift probability distribution
- But this is unreliable - don't count on it

**Mitigation strategies (what agentic systems do):**
- **RAG**: Ground in retrieved facts
- **Citation**: Force model to cite sources
- **Verification**: Use tools to check claims
- **Uncertainty quantification**: Model outputs confidence scores
- **Multi-agent validation**: Have another agent fact-check

**Your blockchain background is relevant here:**
You think about "proof of correctness" in smart contracts. LLMs have NO proof mechanism - they're probabilistic, not deterministic. Agent design is about adding verification layers.

## Nivel de Profundidad: 4
Research papers on hallucination + practical mitigation

## Fuentes de Verdad
- "Survey of Hallucination in Natural Language Generation" (Ji et al., 2023)
- "Trustworthy LLMs: a Survey and Guideline" (Sun et al., 2024)
- Anthropic's research on Constitutional AI (reduces harmful hallucinations)

## Tags
None yet - will be assigned after study
