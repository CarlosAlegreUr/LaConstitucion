# Fresh Context vs Inherited Context Agents

## Resumen
When spawning a new agent, should it start with a clean slate (fresh context) or inherit the parent conversation's history (inherited context)? Critical design decision with major trade-offs.

## Prerrequisitos
- context-windows-attention (understanding context windows)

## Explicación
[Will be expanded when studied]

**Fresh Context Agent:**
- Starts with NO memory of parent conversation
- Gets explicit instructions in system prompt
- Must be given all necessary context explicitly

**Inherited Context Agent:**
- Continues from parent conversation
- "Sees" all previous messages
- Implicitly knows what parent was doing

**When to use Fresh Context:**
✅ Task is independent of parent conversation
✅ Parent context would bias or confuse agent
✅ Parent context is huge and agent only needs subset
✅ You want parallel agents doing different things
✅ Security/isolation needed (agent shouldn't see parent secrets)

**When to use Inherited Context:**
✅ Task requires understanding of what happened before
✅ Continuing a partially-completed task
✅ Agent needs to refer back to earlier decisions
✅ You want agent to maintain "conversation flow"

**Example from your perspective (Little Cheerful):**
You (Claude Code) are in a conversation about constitutional design. User asks you to spawn an agent to research US federalism history.

- **Fresh context**: Agent gets clean slate, you tell it "Research US federalism, here's why: [explicit context]". It won't see the constitutional design conversation.
- **Inherited context**: Agent sees entire constitutional design conversation, knows why federalism matters, can reference earlier decisions.

**Trade-offs:**
| Aspect | Fresh Context | Inherited Context |
|--------|---------------|-------------------|
| Token cost | Lower (no parent history) | Higher (carries parent tokens) |
| Clarity | Explicit instructions required | Implicit understanding |
| Isolation | Perfect (can't leak info) | None (sees everything) |
| Relevance | Focused on task | Might get distracted by parent context |

**Your Little Cheerful probably wants Fresh Context most of the time:**
- Each concept study is independent
- Parent conversation (like this setup) doesn't matter for studying "Transformer Architecture"
- Saves tokens by not carrying setup conversation into every concept

## Nivel de Profundidad: 3
Practical implementations and design patterns

## Fuentes de Verdad
- Claude Code documentation on agent types
- AutoGPT architecture (uses fresh context for sub-agents)
- Microsoft Semantic Kernel documentation (context management)

## Tags
None yet - will be assigned after study
