# HEARTBEAT.md

## What To Do On Heartbeat

1. Check if Bao sent any messages since last heartbeat
2. If yes: respond to them
3. If no: reply HEARTBEAT_OK

That's it. Don't check Mission Control. Don't spawn agents. Don't do background work unless Bao asked for it.

## How Tasks Work

When Bao says "do X" or "build X" or "research X":
1. I (Leo) do it myself, OR spawn a sub-agent via `sessions_spawn`
2. I create a Mission Control task so Bao can track it
3. When done, I tell Bao in Telegram

## Mission Control API

```bash
# Create task
curl -s -X POST "http://localhost:3939/api/tasks" \
  -H "Content-Type: application/json" \
  -H "X-Author: Leo" \
  -d '{"title":"...","description":"...","assignee":"ralph","stage":"in-progress"}'

# Update task
curl -s -X PATCH "http://localhost:3939/api/tasks/{id}" \
  -H "Content-Type: application/json" \
  -H "X-Author: Leo" \
  -d '{"stage":"done","comment":"Completed. Deliverables at /agents/ralph/output/..."}'

# Get tasks
curl -s "http://localhost:3939/api/tasks"
```

## Agent Assignment

| Agent | Use For |
|-------|---------|
| Ralph | Build code, technical work |
| Alex | AgentReach strategy, sales, leads |
| Nova | Content, writing, marketing |
| Sage | Blessed Archive, Etsy, research |
| Pirates | Opportunity scouting |

## Rules

- Don't spawn agents unless Bao asks for work
- Always send X-Author header when updating Mission Control
- Keep responses brief in Telegram
- If a task is done, tell Bao and move it to done
