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


## Isolated Work (worktree subagents)

Este repo inclui subagents pré-configurados em `.claude/agents/` para trabalho que não deve tocar directamente no working directory principal.

| Subagent | Isolamento | Quando delegar |
|---|---|---|
| `isolated-worker` | `worktree` (git worktree temporário) | Refactors >3 ficheiros, migrações de schema, upgrades de dependências, experiências arriscadas |
| `safe-explorer` | read-only (sem Write/Edit/Bash) | Perguntas de exploração, "onde está X", "como funciona Y", investigações de arquitectura |

**Como invocar (a partir da sessão principal):**

```
Agent({
  subagent_type: "isolated-worker",
  isolation: "worktree",
  description: "Refactor auth middleware",
  prompt: "<detailed task brief>"
})
```

**Limitação conhecida:** A sessão principal do Claude Code edita sempre directamente no working directory — o isolamento por worktree só se aplica a subagents spawnados via `Agent` tool. Para trabalho directo na sessão principal, manter a regra *"nunca push directo para `main`"* (ver Git Workflow acima).

**Quando NÃO usar isolated-worker:** edits simples (<3 ficheiros), bug fixes pontuais, alterações de copy/content. O overhead de criar worktree não compensa.

## Git Workflow

> **NEVER push directly to `main`.**

1. Create a feature branch: `git checkout -b feat/description`
2. Push: `git push -u origin feat/description`
3. Open PR: `gh pr create`
4. Wait for review and approval before merging

## Context7 — Documentação de Bibliotecas

Para qualquer biblioteca, framework, SDK, API ou CLI listada no **Tech Stack** acima, usar **Context7** antes de responder sobre ela — evita sintaxe desactualizada e garante que as respostas reflectem a versão em uso.

| Quando usar | Como usar |
|---|---|
| Pergunta sobre API/sintaxe de uma lib | `mcp__context7__resolve-library-id` → `mcp__context7__query-docs` |
| Review de arquitectura (`/arch-review`) | Context7 para cada tecnologia do stack |
| Debugging de lib específica | Context7 com tópico relevante (ex: `authentication`, `rls`, `hooks`) |
| Migração de versão | Context7 com tópico `migration` ou `changelog` |

> Não usar Context7 para: lógica de negócio, refactoring, code review, conceitos gerais de programação.

## Related Projects

| Project | Relationship |
|---------|-------------|
| `ai-product-architecture-template` | Parent template (GitHub Template repo) |
