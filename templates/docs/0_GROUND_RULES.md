# Ground Rules

## Stack

| Layer | Technology | Notes |
|---|---|---|
| Framework | TODO | |
| Styling | TODO | |
| Components | TODO | |
| Routing | TODO | |
| State | TODO | |
| Forms | TODO | |
| Validation | TODO | |
| Backend | TODO | |
| Deployment | TODO | |

## Inviolable Rules

1. Do NOT introduce new dependencies without explicit approval.
2. Do NOT refactor unrelated code.
3. Do NOT rename or delete files without justification and approval.
4. TODO: Add project-specific rules (e.g., i18n, design tokens, database prefixes).

## Internationalisation

- **i18n enabled:** TODO (yes/no)
- **Languages:** TODO (e.g., `pt`, `en`, `es`, `fr`, `it`)
- **Implementation:** TODO (e.g., react-i18next with JSON files, inline translations)

## Lint Warnings Policy

- **Allowed warnings:** TODO (list specific warning codes that are acceptable, or "none")

## Error Handling Patterns

- TODO: Define project-specific error response format
- TODO: Define logging strategy and tools

## Protected Files (Read-Only)

- TODO: List all auto-generated or externally managed files
- Example: `src/integrations/supabase/types.ts`
- Example: `.env`
- Example: `package-lock.json`

## Post-Task Protocol

After every code change:
1. List all changed files
2. Update `docs/5_ROADMAP_AND_TASKS.md`
3. Run build, lint, and test
