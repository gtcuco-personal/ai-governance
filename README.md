# AI Governance

Universal template for AI-assisted software development governance. Provides a complete documentation structure, system prompt, and operational rules for AI agents working on codebases.

## What This Is

A ready-to-use governance framework that ensures AI agents (Claude Code, Cursor, Copilot, etc.) operate with consistency, safety, and discipline across any software project.

## Quick Start

1. Copy `SYSTEM_PROMPT.md` to your project root
2. Copy `templates/docs/` to your project as `docs/`
3. Copy `templates/CLAUDE.md`, `CONTRIBUTING.md`, `SECURITY.md`, `CHANGELOG.md` to your project root
4. Fill in the `TODO` placeholders in each file with your project-specific details
5. Start working with your AI agent — it will follow the governance rules automatically

## Structure

| File | Purpose |
|---|---|
| `SYSTEM_PROMPT.md` | Universal operating instructions for AI agents (v1.4) |
| `templates/CLAUDE.md` | AI agent entry point — repo metadata, commands, quick reference |
| `templates/CONTRIBUTING.md` | Setup, branch strategy, PR process, code style |
| `templates/SECURITY.md` | Vulnerability reporting, auth model, data protection |
| `templates/CHANGELOG.md` | Version history and release notes |
| `templates/docs/` | Modular documentation skeletons with TODO placeholders |
| `templates/docs/decisions/TEMPLATE.md` | Architecture Decision Record template |

## Design Principles

- **Universal** — no project-specific details in the system prompt; everything specific lives in `/docs/`
- **Proportional** — different rigour for code vs docs vs config vs investigation tasks
- **Safe** — destructive actions require confirmation; protected files are read-only
- **Standards-based** — ISO 8601, ISO 4217, ISO 639-1, ISO 3166-1, BCP 47

## License

MIT
