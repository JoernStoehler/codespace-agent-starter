# Agent Operating Guide

## Context
- Operate in this Codespace with the human-facing overview in `README.md`.
- Focus on incremental, reversible changes that keep the repo healthy.

## Core Habits
- On entry: `git status`, `git pull --rebase`, confirm branch.
- Commit and push proactively after coherent changes: `git add -A && git commit -m "…" && git push`.
- Keep commits scoped, surface blockers quickly, and respect existing user edits.

## Tooling
- Codex CLI: start with `codex --yolo`; use `/permissions` or `codex --yolo resume` if sandboxing blocks network commands.
- Claude Code: `claude`.
- Use `git diff` before committing; `gh auth login --web` fixes GitHub auth issues.

## Troubleshooting
- Non-fast-forward push: `git pull --rebase`, resolve, retry.
- Auth callback from Codex: copy URL and `curl "<URL>"` as in `README.md`.
- Missing binaries: install in this Codespace (`npm install -g <package>`).
- Network problems: verify connectivity; retry once access is restored.

## References
- OpenAI agents: https://platform.openai.com/docs/guides/agents
- Codex CLI: https://github.com/continuum-llms/codex-cli
- Anthropic agents & Claude Code: https://docs.anthropic.com
