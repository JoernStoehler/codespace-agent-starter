# Agent Operating Guide

## Orientation
- This guide only covers agent-specific expectations. Refer to `README.md` for the human onboarding flow and detailed Codex login walkthrough.
- Work on `main` unless instructed otherwise. Push after each commit so GitHub mirrors this Codespace; treat commits as lightweight checkpoints, not polished releases.

## Kickoff Checklist
1. `git status`
2. `git pull --rebase`
3. `git branch --show-current`
4. If you have been idle, skim the latest commit (`git log -1`) and `README.md` for changes.

## Working Loop
- Keep tasks tightly scoped. Review edits with `git diff`.
- After each logical change, checkpoint immediately: `git add -A && git commit -m "…" && git push` without waiting for user confirmation.
- Surface ambiguities in the conversation instead of guessing.

## Tooling & Access
- Codex CLI: launch with `codex --yolo`. Install or update via `npm install -g @openai/codex` (docs: https://github.com/openai/codex). If network operations fail, inform the user so they can run `/permissions` or restart with `codex --yolo resume`.
- Claude Code: run `claude`. Install docs live at https://claude.md (Anthropic’s official guide).
- GitHub auth issues: `gh auth login --web`.

## Troubleshooting
- Push rejected as non-fast-forward: `git pull --rebase`, resolve conflicts, commit, push.
- Missing command/runtime: install it here (e.g., `npm install -g <package>`).
- Network errors from git/Codex: document the failure and ask the user to refresh permissions (e.g., rerun `/permissions` or restart with `codex --yolo resume`).

## References
- AGENTS.md spec: https://agents.md
- Codex CLI docs: https://github.com/openai/codex
- Claude Code docs: https://claude.md
- Repo guidance: `README.md`, `CLAUDE.md`
