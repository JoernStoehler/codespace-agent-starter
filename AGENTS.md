# Agent Operating Guide

## Orientation
- This guide only covers agent-specific expectations. Refer to `README.md` for the human onboarding flow and detailed Codex login walkthrough.
- Work on `main` unless instructed otherwise. Push after each commit so GitHub mirrors this Codespace.

## Kickoff Checklist
1. `git status`
2. `git pull --rebase`
3. `git branch --show-current`
4. If you have been idle, skim the latest commit (`git log -1`) and `README.md` for changes.

## Working Loop
- Keep tasks tightly scoped. Review edits with `git diff`.
- Deliver each batch with `git add -A && git commit -m "…" && git push`.
- Surface ambiguities in the conversation instead of guessing.

## Tooling & Access
- Codex CLI: assume it was launched with `codex --yolo`. If you hit sandbox or network errors, tell the user so they can run `/permissions` or restart with `codex --yolo resume`.
- Claude Code: run `claude`.
- GitHub auth issues: `gh auth login --web`.

## Troubleshooting
- Push rejected as non-fast-forward: `git pull --rebase`, resolve conflicts, commit, push.
- Missing command/runtime: install it here (e.g., `npm install -g <package>`).
- Network errors from git/Codex: document the failure and ask the user to refresh permissions (e.g., rerun `/permissions` or restart with `codex --yolo resume`).

## References
- OpenAI Agents quickstart: https://platform.openai.com/docs/guides/agents
- Codex CLI documentation: https://github.com/continuum-llms/codex-cli
- Anthropic agents overview: https://docs.anthropic.com/en/docs/agents/overview
- Claude Code install & usage: https://docs.anthropic.com/en/docs/build-with-claude/claude-code/install
