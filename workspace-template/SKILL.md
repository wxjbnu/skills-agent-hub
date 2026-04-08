# SKILL.md — Skills Directory & Development Guide

> This file serves as a **Skills Catalog** — a guide for finding the right skill for the right task, and a framework for developing new skills. Think of it as the "skill ecosystem" index.

---

## 🎯 How to Use This File

### Finding the Right Skill

1. **Identify your role/task domain** (see Section 1: Skill Domains)
2. **Find the relevant skill** in that domain
3. **Read the skill file** at `{workspace}/skills/[domain]/[skill-name].md`
4. **Follow the skill's instructions** for that specific task

### Skill Loading Priority

Skills are loaded from 6 sources (highest to lowest priority):

| Priority | Source | Path |
|----------|--------|------|
| 1 (Highest) | Workspace skills | `{workspace}/skills/` |
| 2 | Project skills | `{workspace}/.agents/skills/` |
| 3 | Personal skills | `~/.agents/skills/` |
| 4 | 托管 skills | `~/.openclaw/skills/` |
| 5 | Built-in skills | (core framework) |
| 6 (Lowest) | Plugin skills | (plugins) |

> 💡 **User workspace skills can override any built-in behavior.** To customize or extend a skill, create your own in `{workspace}/skills/`.

---

## Section 1: Skill Domains

### 🏢 Business Analysis (For Business Analysts)

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `swot-analysis` | SWOT analysis framework | When analyzing company strengths, weaknesses, opportunities, threats |
| `brand-analysis` | Brand positioning and equity analysis | When evaluating brand health, perception, differentiation |
| `competitor-analysis` | Competitive landscape mapping | When researching competitors, market positioning |
| `financial-analysis` | Financial statement analysis | When analyzing revenue, profit, cash flow, ratios |
| `valuation-analysis` | Company valuation methods | When estimating fair value, DCF, comparable |
| `market-research` | Market size and trend analysis | When assessing TAM, growth, market segments |
| `stakeholder-analysis` | Stakeholder mapping and management | When identifying key stakeholders and their interests |

### 📊 Data & Analytics (For Data Analysts/Scientists)

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `data-exploration` | Exploratory data analysis | When first looking at a dataset |
| `statistical-analysis` | Statistical tests and inference | When testing hypotheses, significance |
| `visualization-design` | Data visualization best practices | When creating charts, dashboards |
| `sql-optimization` | Query performance tuning | When optimizing slow queries |
| `a/b-testing` | A/B test design and analysis | When running experiments |

### 🔬 Medical & Research (For Medical Researchers)

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `clinical-study-analysis` | Clinical trial data interpretation | When analyzing study results, efficacy |
| `literature-review` | Academic paper synthesis | When reviewing research literature |
| `statistical-analysis` | Biostatistics methods | When analyzing medical research data |
| `pathology-analysis` | Pathological findings interpretation | When analyzing pathology reports |
| `regulatory-compliance` | FDA/EMA regulatory requirements | When ensuring compliance |
| `drug-safety-analysis` | Pharmacovigilance and safety | When analyzing adverse events |

### 🏛️ Administration (For Administrative/HR Professionals)

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `org-design` | Organizational structure design | When designing org charts, reporting lines |
| ` succession-planning` | Succession planning frameworks | When identifying and developing talent pipeline |
| `policy-development` | Policy writing and governance | When creating organizational policies |
| `meeting-facilitation` | Meeting coordination and minutes | When organizing and running meetings |
| `project-charter` | Project charter development | When initiating new projects |

### 💻 Software Development (For Developers)

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `code-review` | Code review best practices | When reviewing PRs or submitted code |
| `debugging-systematic` | Systematic debugging methodology | When debugging complex issues |
| `refactoring-patterns` | Code refactoring patterns | When improving existing code |
| `api-design` | RESTful API design | When designing or consuming APIs |
| `database-design` | Database schema design | When designing data models |
| `testing-strategy` | Testing pyramid and strategy | When planning test coverage |

### 📝 Content & Writing (For Content Professionals)

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `copywriting-framework` | Persuasive writing frameworks | When writing marketing copy |
| `technical-writing` | Technical documentation | When writing docs, manuals |
| `seo-optimization` | Content SEO best practices | When optimizing for search |
| `storytelling-structure` | Narrative structure frameworks | When crafting stories, case studies |

### ⚖️ Legal & Compliance (For Legal Professionals)

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `contract-review` | Contract clause analysis | When reviewing agreements |
| `regulatory-research` | Regulatory framework research | When researching compliance requirements |
| `risk-assessment` | Legal risk evaluation | When identifying and mitigating risks |

---

## Section 2: Developing New Skills

### When to Create a New Skill

Create a new skill when:
- You find yourself repeatedly giving the same instructions
- A complex task has a repeatable workflow
- A domain-specific process needs consistent execution

### Skill File Structure

```
{workspace}/skills/[domain]/[skill-name]/
├── SKILL.md          # Required: Main skill definition
├── PROMPT.md         # Optional: Detailed prompt template
├── EXAMPLES.md       # Optional: Example inputs/outputs
└── resources/       # Optional: Reference materials
```

### SKILL.md Template

```markdown
# [Skill Name]

> One-line description of what this skill does.

## When to Use

- Context: When should this skill be invoked?
- Example: "User asks for X"

## What This Skill Does

1. Step 1: Description
2. Step 2: Description
3. Step 3: Description

## Input Format

- Expected input description
- Example input

## Output Format

- Expected output description
- Example output

## Key Principles

- Principle 1
- Principle 2

## Common Pitfalls

- Pitfall 1: How to avoid
- Pitfall 2: How to avoid
```

### Example: Creating a SWOT Analysis Skill

```
skills/business/swot-analysis/
└── SKILL.md
```

```markdown
# SWOT Analysis

> Conduct a structured SWOT (Strengths, Weaknesses, Opportunities, Threats) analysis.

## When to Use

- Context: When analyzing a company's strategic position
- Example: "Analyze this company's competitive position"

## What This Skill Does

1. **Gather context**: Understand the company, industry, time frame
2. **Identify Strengths**: Internal positive factors (resources, capabilities)
3. **Identify Weaknesses**: Internal negative factors (gaps, limitations)
4. **Identify Opportunities**: External positive factors (market, trends)
5. **Identify Threats**: External negative factors (competition, risks)
6. **Synthesize**: Connect insights into strategic recommendations

## Input

- Company name and background
- Industry context
- Specific focus areas (if any)

## Output

- Structured SWOT matrix
- Key insights for each quadrant
- Strategic implications

## Framework

- Use established frameworks (Porter's Five Forces, etc.)
- Support with data and evidence
- Prioritize findings by significance
```

---

## Section 3: Skill Naming Convention

| Domain | Prefix | Example |
|--------|--------|---------|
| Business | `business-*` | `business-swot`, `business-competitor` |
| Data | `data-*` | `data-exploration`, `data-visualization` |
| Medical | `medical-*` | `medical-clinical`, `medical-regulatory` |
| Admin | `admin-*` | `admin-org-design`, `admin-policy` |
| Development | `dev-*` | `dev-code-review`, `dev-api-design` |
| Content | `content-*` | `content-copywriting`, `content-seo` |
| Legal | `legal-*` | `legal-contract`, `legal-risk` |

---

## Section 4: Maintaining Skills

### Review Checklist

- [ ] Skill name clearly indicates purpose
- [ ] "When to Use" section is clear and actionable
- [ ] Steps are specific and reproducible
- [ ] Examples demonstrate expected input/output
- [ ] Pitfalls are documented from real usage

### Lifecycle

1. **Draft**: Create initial version
2. **Test**: Use with real tasks, iterate
3. **Refine**: Update based on feedback
4. **Document**: Add to this catalog
5. **Deprecate**: Mark obsolete if replaced

---

## Section 5: Adding New Domains & Custom Skills

### 🚀 When to Create a New Domain

Create a new domain (category) when:
- You have a distinct role not covered by existing 7 domains
- A new project/industry requires specialized skills
- Existing domains don't fit your workflow

### 📋 How to Add a New Domain

**Step 1: Define the Domain**

Add a new section in Section 1 with:

```markdown
### 🎯 [Domain Name] (For [Target Role])

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `skill-name` | What it does | When to invoke |
```

**Step 2: Create the Skill File**

```
{workspace}/skills/[domain-name]/
└── skill-name/
    └── SKILL.md
```

**Step 3: Register in This Catalog**

Update Section 1 to include the new domain.

---

### 🔧 Custom Skill Development Guide

#### Creating a Skill from Scratch

**1. Analyze the Task**

- What is the input?
- What is the desired output?
- What are the steps to get there?
- What frameworks/ methodologies apply?

**2. Choose the Approach**

| Task Type | Approach |
|-----------|----------|
| Analysis/Assessment | Framework-based (use established methodologies) |
| Research/Investigation | Structured search + synthesis |
| Creation/Generation | Template + guidelines |
| Review/Validation | Checklist + criteria |

**3. Write the SKILL.md**

Follow the template:

```markdown
# [Skill Name]

> One-line description

## When to Use

- Context:
- Example inputs:

## What This Skill Does

1. Step 1: Description
2. Step 2: Description

## Input Format

- Required fields
- Example:

## Output Format

- Expected structure
- Example:

## Frameworks/References

- Framework 1: [link/description]
- Framework 2: [link/description]

## Quality Criteria

- Criteria 1: What "good" looks like
- Criteria 2:

## Common Pitfalls

- Pitfall 1: How to avoid
- Pitfall 2: How to avoid
```

#### Skill File Organization

```
{workspace}/skills/
├── business/              # Domain
│   ├── swot-analysis/
│   │   ├── SKILL.md       # Required
│   │   ├── PROMPT.md      # Optional: detailed prompt
│   │   └── EXAMPLES.md    # Optional: examples
│   └── brand-analysis/
├── [new-domain]/          # Your custom domain
│   ├── skill-1/
│   │   └── SKILL.md
│   └── skill-2/
│       └── SKILL.md
└── README.md              # This file
```

---

### 📝 Domain Template (Copy & Customize)

Copy this template to create a new domain:

```markdown
### 🆕 [Domain Name] (For [Target Role/Persona])

> Brief description of this domain and who it's for.

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `skill-name-1` | Description | Context |
| `skill-name-2` | Description | Context |
| `skill-name-3` | Description | Context |

**Common use cases:**
- Use case 1
- Use case 2
```

---

### 🌐 Example: Adding a "Finance & Investment" Domain

```markdown
### 💰 Finance & Investment (For Financial Analysts/Investors)

| Skill | Description | When to Use |
|-------|-------------|-------------|
| `equity-research` | Equity analysis and recommendations | When analyzing stocks |
| `portfolio-review` | Portfolio performance assessment | When reviewing holdings |
| `risk-metrics` | Risk measurement (VaR, Beta, etc.) | When quantifying risk |
| `ipo-analysis` | IPO pricing and valuation | When evaluating new listings |
| `credit-analysis` | Credit worthiness assessment | When evaluating borrowers |
```

Create the skills at: `{workspace}/skills/finance/equity-research/SKILL.md`

---

### 🔄 Domain Evolution

| Phase | Action |
|-------|--------|
| **Discovery** | Identify recurring task patterns |
| **Prototype** | Create basic SKILL.md |
| **Test** | Use with real tasks, gather feedback |
| **Refine** | Update based on usage |
| **Document** | Add to this catalog |
| **Share** | Consider contributing to community |

---

## Section 6: Skill Quality Checklist

Before marking a skill as "ready":

- [ ] **Name is clear**: Does it indicate what the skill does?
- [ ] **When to Use is specific**: Can a user easily determine when to invoke?
- [ ] **Steps are actionable**: Can someone follow the steps without ambiguity?
- [ ] **Input/Output is defined**: Is the contract clear?
- [ ] **Frameworks are referenced**: Are established methodologies cited?
- [ ] **Examples are provided**: Are there concrete input/output examples?
- [ ] **Pitfalls are documented**: Have common mistakes been identified?

---

## Update Log

| Date | Change |
|------|--------|
| 2024-01-01 | Initialized as code development manual |
| 2024-01-03 | Restructured to task-oriented Skills Catalog |
| 2024-01-03 | Added Section 5: Adding New Domains & Custom Skills Development Guide |