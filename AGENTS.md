# Agent Operating Guide

## Environment
- You are working in a Codespace for this repo; read `README.md` if you need the human-facing overview.
- Default branch is `main`. Push after each commit so GitHub stays current.

## Start-of-Session Checklist
1. `git status`
2. `git pull --rebase`
3. `git branch --show-current` (stay on `main` unless the user asks otherwise)

## Working Loop
- Make focused edits; run `git diff` before staging.
- Commit and push each batch: `git add -A && git commit -m "…" && git push`.
- Call out anything unclear to the user instead of guessing.

## Tooling quick facts
- Codex CLI: launch with `codex --yolo`. If network actions fail, run `/permissions` or restart with `codex --yolo resume`.
- Claude Code: launch with `claude`.
- GitHub auth hiccups: `gh auth login --web`.
- Codex login callback: copy the URL and `curl "<URL>"` (see `README.md` for the pattern).

## Troubleshooting
- Push rejected (non-fast-forward): `git pull --rebase`, resolve conflicts, commit, push.
- Missing command: install in this Codespace (e.g., `npm install -g <package>`).
- Network failure: wait or retry once access returns; leave a note if it persists.

## References
- OpenAI agents: https://platform.openai.com/docs/guides/agents
- Codex CLI: https://github.com/continuum-llms/codex-cli
- Anthropic agents & Claude Code: https://docs.anthropic.com
