# Changelog

## 2026-09-09 — Governance policy v3.1 sync

- Aligned the portable agent entry point, runtime-owned instruction hierarchy,
  live-source rule and task-source routing with the canonical template.
- Synced the governance, CI-detection and scaffolding validators without
  changing the repository profile or product/evidence contract.

→ `AGENTS.md`, `SYSTEM_PROMPT.md`, `scripts/`

## 2026-09-03 — Redução de execuções do GitHub Actions

- Centralizada a detecção de Node, Deno e fixtures do template num único job; os jobs pesados deixam de arrancar apenas para fazer skip.
- `build-test`, `deno-check`, `template-tests` e `governance-check` passam a correr apenas em pull requests; `gitleaks` mantém cobertura em pull requests e em pushes directos para `main`.

All notable changes to this project will be documented in this file.

## [2.0] — 2026-07-19

### Changed

- Declared the minimal product-and-evidence contract and profile.

## 2026-05-07 — Migração path local: ~/Documents/github → ~/devs/github (#14)

- Repo movido localmente para fora do iCloud Drive (eviction provocava falhas de acesso)
- Path references actualizadas em CLAUDE.md (mergeada em PR #14)

## [Unreleased]

[preencher]
