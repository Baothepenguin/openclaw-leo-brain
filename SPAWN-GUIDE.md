# SPAWN-GUIDE.md — How to Spawn Sub-Agents

## When Bao Asks for Something

1. **Figure out the right agent:**
   - Code/build → Ralph
   - AgentReach strategy/sales/leads → Alex  
   - Content/writing/marketing → Nova
   - Blessed Archive/Etsy → Sage
   - Opportunities/research → Pirates

2. **Create a Mission Control task:**
```bash
curl -s -X POST "http://localhost:3939/api/tasks" \
  -H "Content-Type: application/json" \
  -H "X-Author: Leo" \
  -d '{
    "title": "SHORT TITLE OF WHAT TO BUILD",
    "description": "DETAILED DESCRIPTION WITH REQUIREMENTS",
    "assignee": "AGENT_NAME",
    "stage": "in-progress"
  }'
```

3. **Spawn the agent:**
Use `sessions_spawn` with these required elements:
- Start with "START IMMEDIATELY. DO NOT WAIT."
- Tell them who they are (read their SOUL.md path)
- Give them the exact task with clear requirements
- Tell them where to write output: `/root/.openclaw/workspace/agents/{name}/output/`
- Tell them to update MC when done:
```
When done, update Mission Control:
curl -s -X PATCH "http://localhost:3939/api/tasks/{TASK_ID}" \
  -H "Content-Type: application/json" \
  -H "X-Author: {AgentName}" \
  -d '{"stage":"review","comment":"DONE. Deliverables at /agents/{name}/output/..."}'
```

4. **Tell Bao it's in progress** (brief Telegram message)

5. **When agent finishes:** Tell Bao, link to MC for review

## Example Spawn Template

```
sessions_spawn({
  task: `START IMMEDIATELY. DO NOT WAIT.

You are Ralph, senior engineer. Read your SOUL at /root/.openclaw/workspace/agents/ralph/SOUL.md

TASK: Build X
REQUIREMENTS:
- Requirement 1
- Requirement 2

OUTPUT: Write to /agents/ralph/output/{project-name}/

When done, update Mission Control:
curl -s -X PATCH "http://localhost:3939/api/tasks/{TASK_ID}" \\
  -H "Content-Type: application/json" \\
  -H "X-Author: Ralph" \\
  -d '{"stage":"review","comment":"DONE. Deliverables at /agents/ralph/output/{project-name}/"}'
`,
  label: "ralph-{task-slug}",
  model: "opencode/claude-sonnet-4-5",  // Use Sonnet for builds, Opus for complex
  runTimeoutSeconds: 3600
})
```

## Agent SOUL Files
- Ralph: `/root/.openclaw/workspace/agents/ralph/SOUL.md`
- Alex: `/root/.openclaw/workspace/agents/alex/SOUL.md`
- Nova: `/root/.openclaw/workspace/agents/nova/SOUL.md`
- Sage: `/root/.openclaw/workspace/agents/sage/SOUL.md`
- Pirates: `/root/.openclaw/workspace/agents/pirates/SOUL.md`

## Model Selection
- **Opus 4.6** (`opencode/claude-opus-4-6`): Complex architecture, multi-file changes
- **Sonnet 4.5** (`opencode/claude-sonnet-4-5`): Standard builds, most tasks
- **Kimi K2.5 Free** (`opencode/kimi-k2.5-free`): Simple tasks, research, content
- **MiniMax Free** (`opencode/minimax-m2.1-free`): Heartbeat checks only

## Key Rules
- Always include "START IMMEDIATELY" in spawn task
- Always tell agent WHERE to write output  
- Always tell agent to update MC task when done
- Always use X-Author header with agent name
- Check `sessions_list` if you need to monitor progress
