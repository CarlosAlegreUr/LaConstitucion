# ReAct: Reasoning + Acting

## Resumen
ReAct is THE foundational agentic pattern. It interleaves reasoning (thinking) and acting (using tools) to solve problems. This is how Claude Code, ChatGPT with plugins, and most modern agents work.

## Prerrequisitos
- inability-to-act (understanding why base LLMs can't act)

## Explicación
[Will be expanded when studied]

**The ReAct loop:**
1. **Thought**: Agent reasons about what to do next
2. **Action**: Agent uses a tool or takes an action
3. **Observation**: Agent sees the result
4. **Repeat**: Loop until task is done

**Why it works:**
- Base LLMs can only generate text
- ReAct gives them a structured way to "think out loud" before acting
- Interleaving thought + action prevents premature decisions

**Example:**
```
Thought: I need to know the weather in Paris
Action: search("weather Paris")
Observation: 15°C, cloudy
Thought: Now I have the info, I can answer
Action: respond("The weather in Paris is 15°C and cloudy")
```

**Your Little Cheerful system uses this:**
- You think (Socratic questions)
- You act (Read files, Write concepts, Update progress)
- You observe (file contents, user responses)
- You loop

## Nivel de Profundidad: 4
Original paper + implementation details

## Fuentes de Verdad
- "ReAct: Synergizing Reasoning and Acting in Language Models" (Yao et al., 2022)
- LangChain ReAct agent documentation
- Anthropic's Claude tool use documentation

## Tags
None yet - will be assigned after study
