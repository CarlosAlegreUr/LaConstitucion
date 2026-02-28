# Chain-of-Thought (CoT) Prompting

## Resumen
CoT = making the LLM "think out loud" before answering. Massively improves reasoning on complex problems. Foundation for most advanced agentic patterns.

## Prerrequisitos
- poor-multistep-reasoning (understanding why LLMs struggle without scaffolding)

## Explicación
[Will be expanded when studied]

**The core insight:**
Base LLMs generate tokens one at a time, left to right. If you ask "What's 47 * 83?" it has to guess the answer in one token. But if you say "Let's think step by step", it can work through the multiplication.

**Example without CoT:**
```
Q: Roger has 5 balls. He buys 2 more packs of 3 balls. How many balls does he have?
A: 11 balls
```
LLM has to compute in "one shot". Often gets it wrong.

**Example with CoT:**
```
Q: Roger has 5 balls. He buys 2 more packs of 3 balls. How many balls does he have?
A: Let's think step by step.
- Roger starts with 5 balls
- He buys 2 packs of 3 balls each
- 2 packs × 3 balls = 6 balls
- 5 + 6 = 11 balls
Answer: 11 balls
```
LLM breaks problem into steps. Much more accurate.

**Why it works:**
- LLMs are autoregressive (predict next token given previous tokens)
- By generating reasoning steps, each step becomes context for next step
- It's like giving the LLM a "scratch pad"

**Variations:**
- **Zero-shot CoT**: Just add "Let's think step by step" (works surprisingly well)
- **Few-shot CoT**: Show examples with reasoning steps
- **Self-consistency**: Generate multiple reasoning paths, pick most common answer

**Your Little Cheerful uses CoT:**
- Socratic questions make YOU (the user) think step by step
- When I explain concepts, I break them into reasoning steps
- This is CoT applied to human learning

## Nivel de Profundidad: 4
Original papers + variations

## Fuentes de Verdad
- "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models" (Wei et al., 2022)
- "Large Language Models are Zero-Shot Reasoners" (Kojima et al., 2022) - "Let's think step by step"
- "Self-Consistency Improves Chain of Thought Reasoning" (Wang et al., 2022)

## Tags
None yet - will be assigned after study
