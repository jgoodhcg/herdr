# AGENTS

Uses the applicable guidance from `~/projects/agent-blueprint/AGENT_BLUEPRINT.md` (version: 2026-08-04.1).

## Project Overview

This repository tracks the user-owned Herdr configuration in `config.toml`. It keeps durable preferences under version control and excludes Herdr's generated session state, logs, sockets, notices, and lock files.

## Commit Style and Attribution

- Write commit messages in a factual Simplified Technical English register.
- Use an imperative subject line.
- Write the body in simple past. State what changed and why.
- Keep each commit focused on one configuration change or one policy change.

```text
Co-authored-by: [AI_PRODUCT_NAME] <[AI_PRODUCT_EMAIL]>
AI-Provider: [AI_PROVIDER]
AI-Product: [AI_PRODUCT_LINE]
AI-Model: [AI_MODEL]
```

Fill the template at commit time from the active session. Do not store concrete runtime attribution values in this file. Resolve values with `~/projects/agent-blueprint/references/commit-attribution.md`.

## Validation

- Run `git diff --check` after changes.
- Run `herdr server reload-config` after `config.toml` changes when a Herdr server is running. Require a successful `applied` result with no diagnostics.
- Check `git status --short` before each commit. Commit only the intended durable configuration and policy files.

## Project Rules

- Treat `config.toml` as the canonical Herdr configuration.
- Keep links to relevant Herdr documentation near non-obvious settings.
- Do not commit runtime state, logs, sockets, release notices, or lock files covered by `.gitignore`.
- Do not stop the Herdr server unless the user explicitly requests it. Stopping the server exits pane processes.

## Key Files

- `config.toml` — durable Herdr preferences and keybindings.
- `.gitignore` — generated Herdr files excluded from version control.
- `AGENTS.md` — repository purpose, validation, and commit policy.
