# Agent Operating Guide

## Environment
- Work inside this Codespace; consult `README.md` for the human overview when needed.
- Stay on `main` unless told otherwise. Push after each commit so GitHub mirrors local progress.

## Start-of-Session Checklist
1. `git status`
2. `git pull --rebase`
3. `git branch --show-current`
4. Skim `README.md` for recent edits if you have been away.

## Working Loop
1. Scope a single task; keep unrelated work out of the same commit.
2. After editing, inspect changes with `git diff`.
3. Ship the batch: `git add -A && git commit -m "…" && git push`.
4. Ask the user when requirements conflict or context is missing.

## Tooling & Access
- Codex CLI: start with `codex --yolo`; if network access is blocked, run `/permissions` or restart with `codex --yolo resume`.
- Claude Code: run `claude`.
- GitHub authentication issues: `gh auth login --web`.
- Codex login callback: copy the provided URL and `curl "<URL>"` (pattern in `README.md`).

## Troubleshooting
- Push rejected as non-fast-forward: `git pull --rebase`, resolve conflicts, commit, push.
- Missing command or runtime: install it here (e.g., `npm install -g <package>`).
- Network failure: retry once connectivity returns; flag it to the user if it persists.

## References
- OpenAI agents: https://platform.openai.com/docs/guides/agents
- Codex CLI: https://github.com/continuum-llms/codex-cli
- Anthropic agents & Claude Code: https://docs.anthropic.com
