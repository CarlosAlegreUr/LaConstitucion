# Version Control for AI Agents

## Resumen
Why you should use Git/GitHub to version control your prompts, agent configurations, and evaluation datasets. Treat prompts like code because they ARE code - just written in natural language.

## Prerrequisitos
None (you already know Git)

## Explicación
[Will be expanded when studied]

**Why version control for agents?**

You're building Little Cheerful across multiple folders (test1, test2, etc.). This is basically manual version control. Git does this properly.

**What to version control:**
1. **System prompts** - your agent's instructions
2. **Tool descriptions** - how tools are presented to agent
3. **Config files** (like your tree.json, learning-profile.md)
4. **Evaluation datasets** - test cases to verify agent works
5. **Concept libraries** - all your concept.md files
6. **Memory templates** - session.md format, etc.

**Why it matters:**
- **Reproducibility**: Go back to working version if experiment fails
- **A/B testing**: Branch to test prompt variations
- **Collaboration**: Share agent designs, accept PRs
- **Audit trail**: See what changed when agent behavior changed
- **Rollback**: Agent started hallucinating? Git revert

**"Prompt drift" problem:**
You change system prompt slightly → agent behavior changes subtly → accumulates over time → agent behaves very differently from original.

Git lets you track these changes and understand causality.

**Best practices:**
```
.
├── prompts/
│   ├── system_prompt.md
│   ├── concept_explanation_template.md
│   └── socratic_questions_template.md
├── tools/
│   └── tool_definitions.json
├── config/
│   ├── learning-profile-schema.json
│   └── tree-schema.json
├── evals/
│   └── test_cases.json
└── .git/
```

**CI/CD for agents:**
- Push prompt change → Trigger eval suite → Auto-deploy if tests pass
- This is how production agents (ChatGPT, Claude Code, etc.) are developed

**Your current setup:**
You have multiple folders with iterations of Little Cheerful. If you Git this:
- Each folder becomes a commit or branch
- You can diff between versions
- You can cherry-pick good features from different versions
- You can merge improvements

**Relevant to your blockchain background:**
Git is a Merkle tree (like Bitcoin blockchain). Each commit is cryptographically linked to parent. Tamper-proof history. Same principles.

## Nivel de Profundidad: 2
Practical best practices, no deep theory needed

## Fuentes de Verdad
- "Prompt Engineering Guide" (DAIR.AI) - includes versioning section
- LangSmith documentation (LangChain's version control for prompts)
- Weights & Biases "Prompts" feature documentation
- Anthropic's internal practices (mentioned in blog posts)

## Tags
None yet - will be assigned after study
