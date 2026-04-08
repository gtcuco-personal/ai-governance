# AI Governance

Governance tools and templates for AI-assisted software projects. Reference implementation of the universal governance template (SYSTEM_PROMPT.md v1.10).

## Repository

| Key | Value |
|-----|-------|
| **Local path** | `~/Documents/github/ai-governance` |
| **Remote** | `https://github.com/gtcuco-personal/ai-governance.git` |
| **GitHub account** | `gtcuco-personal` |
| **Production URL** | N/A (GitHub Template) |

## Structure

```
templates/          # Reusable governance templates
SYSTEM_PROMPT.md    # Universal AI agent instructions (v1.10)
CLAUDE.md           # This file — repo entry point
```

## Context Loading Policy

Before starting any task, load only the files relevant to that task type.

| Task type | Load | Skip |
|---|---|---|
| Template maintenance | `docs/0_GROUND_RULES.md`, `SYSTEM_PROMPT.md` | All others |
| Roadmap / planning | `docs/5_ROADMAP_AND_TASKS.md` | All others |
| Weekly health check | `docs/6_HEALTH_CHECK.md` | All others |
| Code — UI copy / i18n | `docs/0_GROUND_RULES.md`, `docs/7_CONTENT_I18N.md` | `docs/2_ARCHITECTURE.md`, `docs/4_SEO_AND_AEO.md`, `docs/6_CONTENT_AND_SOCIAL.md` |
| Code — data / analysis | `docs/0_GROUND_RULES.md`, `docs/8_DATA_AND_ANALYSIS.md` | `docs/3_UI_UX_GUIDELINES.md`, `docs/4_SEO_AND_AEO.md`, `docs/6_CONTENT_AND_SOCIAL.md` |
| Agent skill — create/edit | `docs/9_AGENT_SKILLS.md`, `skills/template/SKILL.md` | All others |
| Agent safety review | `docs/10_AGENT_SAFETY.md`, `SYSTEM_PROMPT.md` | All others |

> Always load `docs/0_GROUND_RULES.md` for any task — it is the override document.

## Agent Skills

Este repo inclui um directório `skills/` com templates para criar Agent Skills específicas ao projecto. Skills globais (usadas em múltiplos repos) vivem em `~/.claude/skills/`.

Ver `docs/9_AGENT_SKILLS.md` para o guia completo (framework KEPT, estrutura, regras).

## Git Workflow

> **NEVER push directly to `main`.**

1. Create a feature branch: `git checkout -b feat/description`
2. Push: `git push -u origin feat/description`
3. Open PR: `gh pr create`
4. Wait for review and approval before merging

## Related Projects

| Project | Relationship |
|---------|-------------|
| `ai-product-architecture-template` | Parent template (GitHub Template repo) |
