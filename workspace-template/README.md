# Skills Agent Hub

> A comprehensive workspace template for AI Agents, inspired by OpenClaw architecture.

## Overview

This repository contains a complete workspace file system for AI Agents, consisting of 7 core files that enable persistent memory, self-evolution, and personalized interactions.

## The 7 Core Files

| File | Purpose |
|------|---------|
| **SOUL.md** | Agent identity, personality, values |
| **USER.md** | User profile, preferences, habits |
| **AGENTS.md** | Rules, lessons learned, mistakes to avoid |
| **TOOLS.md** | Environment configuration, paths, tokens |
| **SKILL.md** | Skills directory and development guide |
| **MEMORY.md** | Synthesized long-term memory |
| **memory/** | Daily conversation logs |

## Architecture

```
workspace/
├── SOUL.md          # Agent identity
├── USER.md          # User profile
├── AGENTS.md        # Rules & lessons
├── TOOLS.md         # Environment config
├── SKILL.md         # Skills catalog
├── MEMORY.md        # Long-term memory
├── memory/          # Daily logs
│   ├── 2024-01-01.md
│   └── 2024-01-02.md
└── skills/          # Skills directory
    └── system/
        └── workspace-bootstrap/
            └── SKILL.md
```

## Key Features

- **Self-Evolving**: Agent learns from every interaction
- **Persistent Memory**: Workspace files serve as long-term memory
- **Skill System**: Extensible skill framework for different domains
- **Role-Based**: Supports multiple roles (Business Analyst, Developer, Researcher, etc.)

## Getting Started

1. Clone this repository
2. Customize the 7 core files for your use case
3. Add domain-specific skills to `skills/`
4. Configure your AI Agent to use these files

## Skills

### System Skills

- **workspace-bootstrap**: Explains how to use the workspace file system

### Domain Skills (Extensible)

- Business Analysis: SWOT, Brand Analysis, Competitor Analysis
- Data & Analytics: Data Exploration, Statistical Analysis
- Medical & Research: Clinical Study Analysis, Literature Review
- Administration: Org Design, Policy Development
- Software Development: Code Review, API Design
- And more...

## License

MIT License

## Credits

Inspired by [OpenClaw](https://github.com/open-source/openclaw) architecture.