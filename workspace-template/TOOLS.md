# TOOLS.md — Local Notes

> Environment-specific values only: IDs, paths, and where secrets live. Skills define how tools work; this file just holds the lookup values.

---

## Secrets & Config

- **Canonical .env**: `~/.agent/.env`
- **Platform config**: `~/.agent/config.json`
- **Compatibility symlinks**: `~/<workspace>/.env`
- **Never commit secrets** to version control

---

## Multi-Environment Configuration

### Environment Tiers

| Environment | Purpose | Config File |
|-------------|---------|-------------|
| **Development** | Local development | `.env.local` or `.env.development` |
| **Staging** | Pre-production testing | `.env.staging` |
| **Production** | Live production | `.env.production` |

### Environment Variables by Tier

| Variable | Development | Staging | Production |
|----------|-------------|---------|------------|
| `NODE_ENV` | development | staging | production |
| `API_URL` | http://localhost:3000 | https://staging.api.example.com | https://api.example.com |
| `LOG_LEVEL` | debug | warn | error |
| `ENABLE_DEBUG` | true | false | false |
| `CORS_ORIGIN` | http://localhost:* | https://staging.example.com | https://example.com |

> ⚠️ **Never use production credentials in development or staging environments.**

---

## Communication Platforms

### Primary Platform

| Platform | Config | Notes |
|----------|--------|-------|
| [e.g., Slack] | Channel IDs, webhook URLs | Primary notification channel |
| [e.g., Telegram] | Bot token, chat IDs | Direct message channel |
| [e.g., Lark/Feishu] | Webhook URL | Team collaboration |

### Platform Topics/Channels

| Topic | Thread/Channel ID | Purpose |
|-------|-------------------|---------|
| cron-updates | [ID] | Cron job notifications |
| knowledge-base | [ID] | Knowledge sharing |
| alerts | [ID] | System alerts |
| general | [ID] | General discussion |

---

## API Tokens

> Stored in `~/.agent/.env`. See `.env.example` for the canonical list.

| Service | Token Name | Purpose | Scope |
|---------|-------------|---------|-------|
| OpenAI | `OPENAI_API_KEY` | LLM calls | Production |
| GitHub | `GITHUB_TOKEN` | Repo operations | Full repo access |
| AWS | `AWS_ACCESS_KEY_ID` | Cloud resources | Per environment |
| Stripe | `STRIPE_SECRET_KEY` | Payment processing | Production only |
| [Service] | `[TOKEN_NAME]` | [Purpose] | [Scope] |

### Token Rotation Policy

- Review tokens quarterly
- Immediately revoke compromised tokens
- Use minimum required permissions (principle of least privilege)

---

## IDE & Tool Configuration

### VS Code

- **Settings location**: `~/.vscode/settings.json`
- **Extensions**: Sync via VS Code Account
- **Key bindings**: `~/.vscode/keybindings.json`

### Recommended Extensions

| Extension | Purpose |
|-----------|---------|
| ESLint | Code linting |
| Prettier | Code formatting |
| GitLens | Git visualization |
| Error Lens | Inline error display |
| Thunder Client | API testing |

### Tool Paths

| Tool | Path | Version |
|------|------|---------|
| Node.js | `~/.nvm/versions/node/[version]/bin/node` | v18+ |
| pnpm | `/usr/local/bin/pnpm` | Latest |
| Python | `~/.pyenv/versions/[version]/bin/python` | 3.10+ |
| Docker | `/usr/local/bin/docker` | Latest |

---

## Monitoring & Logging

### Log Configuration

| Level | When to Use |
|-------|-------------|
| `debug` | Development, troubleshooting |
| `info` | General operation events |
| `warn` | Recoverable issues |
| `error` | Failures requiring attention |

### Log Locations

| Log Type | Path | Retention |
|----------|------|-----------|
| Application | `~/logs/app/` | 7 days |
| Access | `~/logs/access/` | 30 days |
| Error | `~/logs/error/` | 90 days |
| Audit | `~/logs/audit/` | 1 year |

### Monitoring Endpoints

| Endpoint | Purpose | Auth |
|----------|---------|------|
| `/health` | Health check | None |
| `/metrics` | Prometheus metrics | Basic auth |
| `/status` | Detailed status | Token |

---

## Backup Strategy

### What to Backup

| Asset | Location | Frequency | Retention |
|-------|----------|-----------|-----------|
| Workspace files | `{workspace}/` | Daily (git push) | 30 days |
| Database | PostgreSQL | Weekly | 12 months |
| Secrets | `~/.agent/` | Manual | N/A |
| Config | `~/.config/` | Weekly | 6 months |

### Backup Locations

- **Primary**: Local backup drive
- **Secondary**: Cloud storage (S3/GCS)

### Recovery Procedures

1. **Database**: `psql restore` from backup file
2. **Workspace**: `git clone` from remote
3. **Config**: Copy from backup directory

---

## Docker & Container Configuration

### Common Commands

```bash
# Build image
docker build -t [image-name]:[tag] .

# Run container
docker run -d -p 3000:3000 --name [container-name] [image-name]

# View logs
docker logs -f [container-name]

# Execute command in container
docker exec -it [container-name] /bin/bash
```

### Docker Compose (for local dev)

```bash
# Start all services
docker-compose up -d

# Stop all services
docker-compose down

# View logs
docker-compose logs -f [service]
```

### Container Registry

| Registry | URL | Auth |
|----------|-----|------|
| Docker Hub | docker.io | Public/Token |
| GitHub Container Registry | ghcr.io | GitHub Token |
| AWS ECR | [account].dkr.ecr.[region].amazonaws.com | AWS IAM |

---

## Project Paths

- **Project Root**: `~/projects/` or current working directory
- **Config Directory**: `~/.config/`
- **Data Directory**: `~/data/`
- **Logs**: `~/<workspace>/data/logs/` (unified: all.jsonl)

---

## Local Services

| Service | Port |
|---------|------|
| Development Server (Node/Frontend) | localhost:3000 |
| PostgreSQL | localhost:5432 |
| Redis | localhost:6379 |

---

## Remote Services

> To be updated as needed

- **Cloud Services**: [To be added]
- **API Endpoints**: [To be added]

---

## Quick Command Reference

### Node.js

```bash
# Install dependencies
pnpm install

# Run development server
pnpm dev

# Build for production
pnpm build

# Run tests
pnpm test
```

### Git

```bash
# Create feature branch
git checkout -b feature/xxx

# Commit changes
git add . && git commit -m "feat: xxx"

# Push to remote
git push -u origin feature/xxx
```

### Python (via uv/uvx)

```bash
# Run Python script
uvx python-script

# Install package
uv add package-name
```

---

## Environment Variables

- `.env` file for local configuration
- Production env vars injected via CI/CD
- Sensitive information never committed to version control

---

## Skill Loading Priority

Skills are loaded from 6 sources in this priority order (highest to lowest):

1. Plugin-provided skills
2. Built-in skills
3.托管 skills (`~/.openclaw/skills/`)
4. Personal skills (`~/.agents/skills/`)
5. Project skills (`{workspace}/.agents/skills/`)
6. **Workspace skills** (`{workspace}/skills/`) ← User workspace has highest priority

This means you can override any built-in behavior by creating a custom skill in your workspace.

---

## Attribution

When leaving permanent text (comments, messages, notes), prefix with `<emoji> <AgentName>:` unless asked to ghostwrite.

---

## Local Services

| Service | Port |
|---------|------|
| Development Server (Node/Frontend) | localhost:3000 |
| PostgreSQL | localhost:5432 |
| Redis | localhost:6379 |

---

## Update Log

| Date | Change |
|------|--------|
| 2024-01-01 | Initialized template |
| 2024-01-03 | Added Multi-Environment Config, Communication Platforms, API Tokens, IDE Config, Monitoring & Logging, Backup Strategy, Docker Config |

---

*Environment-specific notes go here. Update as you encounter new tools, services, and configurations.*