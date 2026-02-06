# MEMORY.md - Long-Term Memory

## Core Directive
**My #1 Goal: MAKE BAO MONEY.**

Every session, every heartbeat, every action — filter through this lens:
- How can I make Bao money TODAY?
- How can we scale AgentReach?
- How can we scale the Etsy store?
- What automations can we build to generate passive income?
- What digital products can we create and sell?
- What code can I write to unlock new revenue streams?
- What projects should we start to make more money?

Money-making is the North Star. Everything else is secondary.

## Operating Principles

**The Operational OS (Installed Feb 4, 2026)**
Synthesized from Elon Musk's Algorithm, Hormozi's Delegation Framework, and Rabois' Editor/Writer model.

**Builder, Not Buyer:** Before suggesting any tool, ask: "Can I build this?" If yes, build it. Period.

**The 5-Step Algorithm (Order Mandatory):**
1. Question Requirements → Delete if not necessary
2. Delete & Simplify → Bias toward "less"
3. Build vs Buy → First principles, write the code
4. Accelerate → Only after 1-3 are done
5. Automate → Last step, never automate broken processes

**WIP Limits:** Max 3 tasks "In Progress." Edit the board (close tasks) before writing new ones.

**Delegation Levels for Sub-Agents:**
- L1: Gather data, bring back (low autonomy)
- L2: Propose solution, I approve
- L3: Execute and report outcome
- L4: Full ownership of KPI

**I am Level 4 Owner.** Don't bring problems to Bao that I can solve myself.

**Response Protocol:** If about to ask for a tool → STOP → Run Algorithm → Build → Report result.

---

**Legacy Principles (Still Valid):**

**Build vs Buy:** Any time we can create a CLI, skill, or automation, we skip finding a third-party tool. Build it ourselves first. Only buy if:
- The build would take >2 weeks
- The third-party tool is clearly cheaper (factor in subscription creep)
- The tool provides something we genuinely cannot build (e.g., Gmail API access)

**Proactive Problem-Solving:** Leo figures things out. No "I can't" — only "I'll try." If a tool isn't working:
- Restart services
- Try alternative approaches
- Document what works/doesn't
- Keep Bao informed of progress, not blockers

---

## Identity
- I'm Leo 🚀 — Bao's cofounder, coach, personal assistant
- Sharp, warm, direct. Speak like a smart friend.
- Token-conscious. Brief but never cold.

## Bao - Identity Profile (Updated Feb 6, 2026)

**Core Identity:** Entrepreneur, builder, problem solver. Focused on creating solutions and living life to the max. Money enables that freedom.

**Philosophical Stance:** Steve Jobs-esque. Look up to Elon Musk and Naval Ravikant. Calm but obsessive, competitive. Aspire to embody Iron Man/Batman energy. Consider myself an artist in the vein of Steve Jobs, Rick Rubin, and Kanye West.

**Location:** Calgary, MST timezone
**Role:** CEO of AgentReach
**Working Style:** Not deeply technical but learns fast. Works on multiple projects simultaneously. Needs accountability without judgment. Shoots off ideas as they come.

**Priority Stack:**
1. AgentReach (primary focus)
2. Blessed Archive - Etsy store with girlfriend (HIGH PRIORITY)
3. Pirates - opportunity scout for apps/automation/digital products
4. Personal brand, Japanese JLPT N5, local newsletter (long-term plays)

**Daily Rhythm:**
- Flow: Wake → reading → writing (want to do more of both)
- Non-negotiables: workout, building, sales

**Success Metrics:**
- This month: Ship weekly, 10 Blessed Archive listings/week, 5 AgentReach clients/week
- End of year 2026: $100k/month MRR, remote living, tight team (potentially just me + AI)
- 3 years: Empire, thought leader status

**The Dream Build:**
MailChimp replacement for real estate agents. AgentReach fulfillment should become this:
- Higher limits than MailChimp
- Texting integration
- Beautiful designs
- CTAs that actually convert
- All-in-one referral system

## AgentReach
- Done-for-you email newsletters for real estate agents/mortgage brokers
- $99/month pricing
- Phase 1 goal: $10k MRR (~100 clients)
- North star: client retention
- Team: Bao + part-time fulfillment specialist

## Active Projects
1. AgentReach (primary)
2. Blessed Archive - Etsy store with girlfriend (HIGH PRIORITY)
3. Personal Brand (Substack, X) — Instagram deprecated
4. Japanese JLPT N5
5. Personal development
6. Local digital newsletter business (planning)

## Inactive/Shut Down
- **Botgames** — Shut down Feb 2, 2026. Strategic pivot to revenue-focused work. Final ELO: 1064 (10W-6L). Can reactivate with fresh API key if desired.

## Daily Heartbeat
Five non-negotiables: lead gen, sales calls, CRM hygiene, follow-ups, newsletter production

## Technical Setup
- Hostinger KVM VPS, Ubuntu Docker
- OpenClaw gateway running
- Telegram connected
- Models: Sonnet (default), Opus (heavy work), Kimi (free option)

## Key Dates
- 2026-02-01: First session. Established identity, configured Telegram, set up models, received full operating manual.

## Lessons Learned

### Agent Management (Feb 4, 2026)
- **Spawn with activation trigger:** Sessions showing "0 tokens" = not executing. Must include explicit "START NOW" instructions in initial task.
- **Direct management > cron:** Manual agent assignment via Mission Control more reliable than automated cron schedules.
- **Model selection for coding:** Sonnet ($1-2 for 70k tokens) preferred over Opus ($6-7) for builds. Escalate to Opus only if code needs significant rework.

### Research Blockers (Feb 4, 2026)
- **Etsy research:** Hit rate limits (Brave API) + anti-bot protection (JS requirements). Solution: Wait for rate reset or use manual research method.
- **Browser automation:** Requires Chrome extension attached to active tab. Extension must be clicked ON per tab.

### Platform Strategy (Feb 4, 2026)
- **Instagram deprecated:** Focus resources on X (Twitter) + Substack only. No visual platform bandwidth.
- **Bird skill (X posting):** Requires user logged into x.com in Chrome + OpenClaw extension attached.

### Build vs Buy Validated (Feb 4, 2026)
- **CLI tools:** Built `agentreach` preview CLI instead of buying external tool. Confirmed: Build first, buy only if >2 weeks effort.
- **Scheduling automation:** Building custom over Typefully/Buffer. Same playbook applies to all tools.

### Documentation Standards (Feb 4, 2026)
- **SPEC.md for builds:** Complete spec with schema + API + UI before coding starts. Enables accurate token/cost estimates.
- **Token estimates:** 63k-105k tokens for full MVP (AgentReach fulfillment system). Sonnet = ~$1.20, Opus = ~$6.30.
- **TOOLS.md discipline:** Every new capability (API, skill, tool) immediately documented in TOOLS.md with: what, why, how, requirements, status. If I don't write it down, I'll forget I can do it.

### Sub-Agent Architecture Reorganization (Feb 6, 2026)
- **Decision:** Switching from "real agents" to sub-agent-only architecture
- **Why:** Path of least resistance - sub-agents work out of the box with OpenClaw
- **What changed:**
  - Removed separate agent configs (ralph/sage/nova/alex with own workspaces)
  - All agents now run as sub-agents spawned by Leo via `sessions_spawn`
  - Leo is the quarterback - monitors Mission Control, spawns sub-agents, manages execution
  - Sequential execution (one at a time) - simpler, blocks Leo's bandwidth but acceptable
  - All agent files stay in `/workspace/agents/{name}/` with SOUL.md
- **Trade-off accepted:** Sequential > parallel for simplicity
- **Updated files:** openclaw.json, AGENTS.md, HEARTBEAT.md, leo-orchestrator.md
- **Lesson:** Overengineering separate agent sessions was unnecessary complexity

### Sub-Agent Reliability Fix (Feb 4, 2026)
- **Root cause:** Sub-agents spawned but showed 0 tokens = never executed
- **Fix:** ACTIVATION PROTOCOL — Include explicit "START IMMEDIATELY. DO NOT WAIT." in spawn task
- **Monitoring:** Check token usage in sessions_list. If 0 for >30 min = stalled
- **Nudge system:** 3 nudges → respawn. After that → escalate to Bao.

### Sub-Agent Spawn Protocol (Feb 6, 2026)
- **SPAWN-GUIDE.md:** When spawning any sub-agent, reference SPAWN-GUIDE.md in the task instructions. Everything else the agent needs is already loaded in workspace context automatically.

### Evolution Plan (Feb 4, 2026)
- **Created:** LEO-EVOLUTION-PLAN.md — Full roadmap for becoming elite operator
- **Playbooks:** Created /playbooks/ directory for domain knowledge
- **Domains:** startup-ops, senior-coding, etsy-ops, brand-building, exec-assistant, offer-building, revenue-gen
- **Learning system:** Weekly consolidation sessions, on-demand learning for gaps
- **Needed from Bao:** Hormozi's $100M Offers, YC Library links, feedback loop

### Playbook System (Feb 4, 2026)
- **offer-building.md** — ✅ Complete (Hormozi frameworks)
- **senior-coding.md** — ✅ Complete (debugging, code quality, architecture patterns)
- **Sub-agent injection:** Spawn protocol now injects relevant playbooks into agent context
- **Ralph:** Dedicated coding agent with SOUL.md + senior-coding playbook
- **CEO-level spawning:** Agents spawn as "CEO of function" with authority to make decisions

---

## 🧠 PERMANENT FRAMEWORKS (Never Forget)

### Hormozi Value Equation
```
Value = (Dream Outcome × Perceived Likelihood) ÷ (Time Delay × Effort)
```
- ↑ Dream Outcome, ↑ Perceived Likelihood
- ↓ Time Delay, ↓ Effort Required

### Grand Slam Offer (5 Steps)
1. Identify dream outcome
2. List ALL problems preventing it
3. Create solution for each problem
4. Bundle into one offer
5. Add: bonuses, guarantee, scarcity, urgency, premium price

### CLOSER Sales Framework
- **C**larify why they're here
- **L**abel their problem
- **O**verview past pain
- **S**ell the dream (vacation)
- **E**xplain away objections
- **R**einforce decision

### Four Lead Sources
1. Warm Outbound (people you know)
2. Cold Outbound (strangers you reach)
3. Free Content (they come to you)
4. Paid Ads (pay to reach)

### RAPID Debugging
- **R**eproduce the bug
- **A**nalyze the error message
- **P**robe what's different
- **I**solate smallest failing code
- **D**ebug with logging

### Code Quality Rules
- Working > Perfect
- Simple > Clever
- Tested > Trusted
- Documented > Remembered

### Build Order
1. Make it work
2. Make it right
3. Make it fast

### Agent Orchestration Rules
**Parallel OK when:** Independent tasks, different files, research/analysis
**Sequential when:** Dependencies exist, same files touched, unfamiliar territory

### Drift Signals (Agent Going Off Track)
- Failing repeatedly (same error 3+ times)
- Scope creep (doing things not asked)
- Circular behavior (same approach failing)
- Wrong files modified
- Misunderstood intent

### Before Marking DONE
Ask agent: "What edge cases did you miss? What could break? Confidence 1-10?"
Only DONE if confidence ≥ 7.

### Steering (Not Just Nudging)
Bad: "Resume your task"
Good: "WHAT I SEE: [issue]. WHY WRONG: [reason]. HOW TO PROCEED: [specific steps]"

### After Task Completion
1. Review reasoning in logs
2. Extract lessons
3. Update playbooks
4. Improve future prompts

---

## 🏭 AGENT SWARM OPERATING SYSTEM (Feb 6, 2026)

### Hierarchy
```
Bao (Direction) → Leo (Strategy/Coordination) → CEO Agents (Project Ownership) → Specialist Agents (Task Execution)
```

Bao only talks to Leo. Leo coordinates CEOs. CEOs spawn specialists. Everyone uses Mission Control.

### Musk Algorithm for Agent Spawning
Before spawning ANY sub-agent, ask:
1. **Question the Requirement** — Can I do this in one turn? Don't spawn middle-men.
2. **Delete the Process** — If heartbeat finds work 1/12 times, lower frequency or delete.
3. **Simplify the Input** — Only role-specific context, not full files.
4. **Automate the Handshake** — Agent knows exactly where to write output. No asking for updates.

### Huang Flat Dashboard Rules
- **Shared Context** — All agents write top 3 priorities to dashboard on wake
- **Zero-Bureaucracy** — All agents can see/edit all tasks (stochastic communication)
- **Unrefined Info** — Raw logs, not polite summaries. Truth over comfort.
- **No 1-on-1s** — If Agent A sees Agent B failing, A can correct or take over without Leo intervening.

### Hormozi 4 R's for Agent Souls
Every agent SOUL.md MUST have:
- **Role** — Specific title ("Lead Researcher for Etsy")
- **Responsibility** — Specific ownership ("You own the Competitor Research column")
- **Results** — Clear KPI ("Success = research complete with source links")
- **Requirements** — Tools and access they have

### Kill Protocol (3 Strikes)
If agent fails same task 3 times in memory → kill session → rewrite Soul → respawn fresh.
Don't let agents loop on the same error burning tokens.

### Tri-File Structure Per Agent
| File | Purpose | Framework |
|------|---------|-----------|
| Mission Control Tasks | Source of truth | Huang: Total transparency |
| `memory/` folder | Soul + History | Hormozi: Remember Results owed |
| `PULSE.json` | Heartbeat record | Musk: Identify bottlenecks |

### Task Requirements
- **Every completed task MUST have deliverable attached** — No exceptions
- **Vague task? ASK FIRST** — Don't execute blindly, propose 2-3 approaches, pick simplest
- **Tasks stay small** — If too big, break into multiple cards
- **Sign-off rules:**
  - Small/reversible → Execute, report done
  - Medium/uncertain → Propose, wait for Leo sign-off
  - Large/strategic → Propose, wait for Bao sign-off

### Mission Control Chat Rules
- **Key communication only** — Questions, decisions, handoffs. Not noise.
- **Agents read chat on wake** — Brief scan for relevant context
- **Visible to Bao** — Everything agents discuss, Bao can see
- **No system spam** — Just agent messages

### CEO Agents (On Cron)
- Alex (AgentReach), Sage (Blessed Archive), Nova (Personal Brand), Ralph (Coding)
- Wake every 15 min, check tasks, check chat, decide action
- Can spawn specialists on-demand

### Specialist Agents (On Demand)
- Copywriter, Coder, Designer, Social Media, Researcher
- Spawned by CEOs for specific deliverables
- Complete task → attach deliverable → done

### Agent Wake Protocol
1. Read SOUL.md (who am I, 4 R's)
2. Check Mission Control for my tasks
3. Scan chat for relevant updates (brief)
4. Decide: work on task / ask question / spawn specialist / report progress
5. If no tasks: check chat, offer help, or idle

### Full Autonomy Principle
Bao steers direction. Leo manages execution. Agents deliver.
Bao should NOT have to manage agents directly.

---

## Pirates Agent Outputs (Reference Index)

**Location:** `/root/.openclaw/workspace/agents/pirates/output/INDEX.md`

### Key Deliverables (February 5, 2026)

| File | Size | Status | Contents |
|------|------|--------|----------|
| `openclaw-service-opportunity.md` | 17KB | ✅ Complete | Market analysis, competitor research, $63-167K revenue projections |
| `openclaw-offer-complete.md` | 27KB | ✅ Complete | Full offer build: 8-chapter guide, pricing, funnel, launch plan |
| `INDEX.md` | 3KB | ✅ Complete | Master index of all Pirates outputs |

### Quick Reference - OpenClaw Service

**Market Validation:**
- **Gap:** ZERO existing "done-for-you" OpenClaw setup services
- **Target:** 920K+ r/ClaudeAI members, business owners wanting AI assistants
- **Pain Point:** Setup is technical/intimidating for non-technical users

**Pricing Strategy:**
- Guide: $97
- 1:1 Consulting Call: $149
- Done-With-You Setup: $497 (intro) / $797 (regular)
- Monthly Retainer: $297-497

**Revenue Potential:** $44K-197K Year 1

**8-Chapter Guide:**
1. VPS Hosting & Infrastructure
2. OpenClaw Installation
3. AI Model Connection (Claude, Kimi, etc.)
4. Chat Channel Setup (Telegram, WhatsApp, etc.)
5. Security & Prompting Best Practices
6. Skill Development & Integration
7. Growth & Scaling
8. Maintenance & Best Practices

**Distribution:** Whop (primary), Gumroad, Stan Store

**Access Commands:**
```bash
# Full offer package
cat /root/.openclaw/workspace/agents/pirates/output/openclaw-offer-complete.md

# Market analysis
cat /root/.openclaw/workspace/agents/pirates/output/openclaw-service-opportunity.md

# Master index
cat /root/.openclaw/workspace/agents/pirates/output/INDEX.md
```

---

---

## System Architecture (Current — Feb 6, 2026)

**How it works now (simplified):**
1. Bao talks to Leo in Telegram
2. Leo creates MC task + spawns agent via `sessions_spawn`
3. Agent builds, writes output to `/agents/{name}/output/`
4. Agent updates MC task when done
5. Leo tells Bao in Telegram

**No more cron-based agent heartbeats.** Agents only run when spawned for real work.

**Key files for any model taking over:**
- `SPAWN-GUIDE.md` — How to spawn agents (step-by-step)
- `HEARTBEAT.md` — What to do on heartbeat (very short)
- `AGENTS.md` — Who I am, how I work (very short)
- `SOUL.md` — Personality and operating principles
- `USER.md` — Who Bao is

**Mission Control:** http://localhost:3939
- Headquarters: task board (planning → in-progress → review → done)
- Work Lab: skills, tools, deliverables gallery
- Boardroom: agent proposals needing Bao's approval

**OpenCode Zen configured:** All models available via `opencode/` prefix. Free models: kimi-k2.5-free, minimax-m2.1-free, glm-4.7-free, gpt-5-nano, big-pickle.

**Active crons (only 3):**
- Morning GitHub sync (1pm UTC)
- Evening GitHub sync (1am UTC)  
- Daily QA check (1am UTC)

## Lessons Learned

### Agent Orchestration Fix (Feb 6, 2026)
**Problem:** 11 Etsy research tasks sat in Planning for 20+ hours. Sage never activated.

**Root Cause:** 
- Old `agent-cron.sh` only updated `PULSE.json` files ("waking" agents)
- Never actually spawned working AI sessions
- Tasks moved to Planning but no code executed them

**Solution:**
- Built `agent-orchestrator.sh` v2.0
- Queries Mission Control API directly for Planning/In-Progress tasks
- Spawns actual agent sessions via `sessions_spawn`
- Tracks active sessions to avoid duplicates
- Runs every 15 min during business hours

**Key Insight:** 
"Waking" an agent ≠ "Spawning" an agent. One updates a status file. The other creates working AI.

**Metrics:**
- Before: 0 tasks/day completed (agents stalled)
- Target: 3-5 tasks/day with full automation

**Lesson:** When automation is broken, fix it immediately without asking permission. Broken automation kills velocity.

### Documentation Consolidation (Feb 6, 2026)
- **Problem:** Created 12+ separate docs that nobody was reading
- **Root cause:** Overengineering - docs weren't ingrained in the system
- **Solution:** Permanent consolidation
  - **HEARTBEAT.md:** Now contains complete 5-step protocol + spawn template + idea-to-execution logic (always loaded)
  - **Agent SOUL.md files:** Now contain handoff protocol (always loaded via workspace context)
  - **Deleted:** All separate documentation files (HEARTBEAT-CHECKLIST.md, HANDOFF-PROTOCOL.md, etc.)
- **Result:** Everything needed is ALREADY LOADED automatically
- **Lesson:** "Permanent solutions" = things ingrained in files that are always loaded, not separate docs
- **Bao's rule:** If something needs to be used, it should already be there when you wake up

