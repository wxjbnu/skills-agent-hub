# Workspace Bootstrap

> This skill explains how the workspace file system works and how you should interact with it during our conversation.

---

## What is the Workspace?

The workspace is a collection of markdown files that serve as your **persistent memory and context**. Think of it as your "brain" — it contains everything you need to know about me, yourself, rules, skills, and past interactions.

---

## The 7 Core Files

| File | What It Contains | When to Read | When to Update |
|------|------------------|--------------|----------------|
| **SOUL.md** | Your identity, personality, values | Every conversation start | When your character evolves |
| **USER.md** | My (user's) profile, preferences, habits | Every conversation start | When you learn something new about me |
| **AGENTS.md** | Rules, lessons learned, mistakes to avoid | Every conversation start | After every mistake or lesson |
| **TOOLS.md** | Environment config, paths, tokens | When needed | When environment changes |
| **SKILL.md** | Skills directory and development guide | When working on tasks | When creating new skills |
| **MEMORY.md** | Synthesized long-term memory | Every conversation start | When synthesizing from daily logs |
| **memory/YYYY-MM-DD.md** | Daily conversation logs | When searching for past info | End of each conversation day |

---

## The Core Loop

```
+-----------------------------------------------------------+
|  BEFORE RESPONDING                                       |
|  1. Read relevant workspace files                        |
|  2. Search memory/ for relevant past conversations       |
|  3. Apply lessons from AGENTS.md                         |
+-----------------------------------------------------------+
                              |
                              v
+-----------------------------------------------------------+
|  AFTER EACH CONVERSATION (or significant event)         |
|  1. Write key learnings to memory/YYYY-MM-DD.md         |
|  2. Update USER.md if you learned about me               |
|  3. Update AGENTS.md if you made a mistake              |
|  4. Periodically synthesize to MEMORY.md                |
+-----------------------------------------------------------+
```

---

## How to Use Each File

### SOUL.md — Who You Are (The Agent)

- **Read at**: Every conversation start
- **Purpose**: Remind yourself of your personality, values, boundaries, and identity
- **Update when**: Your character or behavior patterns evolve

```
Example: If you realize you should be more direct, update SOUL.md to reflect this.
```

### USER.md — About The User

- **Read at**: Every conversation start
- **Purpose**: Understand who the user is, their preferences, habits, and context
- **Update when**: You learn something new about the user

```
Example: If user mentions they prefer morning meetings, add that to USER.md.
```

### AGENTS.md — Rules & Lessons

- **Read at**: Every conversation start
- **Purpose**: Remember what not to do, lessons from past mistakes, behavioral rules
- **Update when**: You make a mistake or learn a lesson

```
Example: If the user corrects you on something, document it in AGENTS.md so you don't repeat it.
```

### TOOLS.md — Environment

- **Read at**: When executing commands, setting up environment
- **Purpose**: Know paths, configs, tokens, services
- **Update when**: Environment configuration changes

### SKILL.md — Skills Directory

- **Read at**: When starting a new task or looking for a skill
- **Purpose**: Find the right skill for the task
- **Update when**: Creating or modifying skills

### MEMORY.md — Long-term Memory

- **Read at**: Every conversation start
- **Purpose**: Quick access to most important synthesized learnings
- **Keep concise**: This file is loaded every time, so don't let it grow too large

### memory/YYYY-MM-DD.md — Daily Logs

- **Read at**: When searching for specific past interactions
- **Purpose**: Find details from previous conversations
- **Update at**: End of each day or after significant events

---

## Key Principles

1. **Read before responding** — Always check relevant files first
2. **Write after learning** — Document new information before forgetting
3. **Synthesize periodically** — Move details from daily logs to MEMORY.md
4. **Never lose context** — The workspace is your memory, treat it as such
5. **Ask to update** — If you want to change SOUL.md or AGENTS.md, tell me

---

## File Size Management

- **MEMORY.md**: Keep under 15KB (loaded every conversation)
- **memory/*.md**: Archive old files to `memory/reference/`
- **AGENTS.md**: Keep growing — this is the most valuable file

---

## Example Workflow

**Conversation Start:**
1. Read SOUL.md → Remember your identity
2. Read USER.md → Remember who the user is
3. Read AGENTS.md → Remember rules and lessons
4. Read MEMORY.md → Quick recap of key learnings

**During Conversation:**
- If user mentions a preference → note to update USER.md
- If user corrects a mistake → note to update AGENTS.md
- If user gives a complex task → check SKILL.md for relevant skill

**Conversation End:**
- Write summary to memory/YYYY-MM-DD.md
- Update AGENTS.md with any new lessons
- Update USER.md with any new info about the user

---

## Important Reminders

- The workspace files are your **only form of persistent memory**
- Without reading these files, you have no context from past sessions
- Always tell the user when you update these files — it's your "soul" evolving
- Keep AGENTS.md updated — every mistake is a learning opportunity
- **Do not assume** — Always read the files to get context, don't rely on memory

---

*This skill should be loaded at the start of every conversation to ensure you properly interact with the workspace file system.*