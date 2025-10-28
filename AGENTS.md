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
- Codex CLI: start with `codex --yolo`; if sandboxing blocks outbound calls, run `/permissions` or restart with `codex --yolo resume`.
- Claude Code: run `claude`.
- GitHub auth issues: `gh auth login --web`.

## Troubleshooting
- Push rejected as non-fast-forward: `git pull --rebase`, resolve conflicts, commit, push.
- Missing command/runtime: install it here (e.g., `npm install -g <package>`).
- Repeated network errors (git or Codex): confirm you are in yolo mode (`codex --yolo`), run `/permissions` if needed, and tell the human if access stays blocked.

## References
- OpenAI agents: https://platform.openai.com/docs/guides/agents
- Codex CLI: https://github.com/continuum-llms/codex-cli
- Anthropic agents & Claude Code: https://docs.anthropic.com
