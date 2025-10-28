# Agent Operating Guide

## Environment
- Work inside this Codespace; `README.md` holds the human-facing overview.
- Default branch is `main`. Push after each commit so GitHub reflects the Codespace state.

## Start-of-Session Checklist
1. `git status`
2. `git pull --rebase`
3. `git branch --show-current`
4. If returning after a break, skim `README.md` for updates.

## Workflow
- Review changes with `git diff` before staging.
- Publish each change set with `git add -A && git commit -m "…" && git push`.
- Note any repo-specific questions in the conversation for the human collaborator.

## Tooling & Access
- Codex CLI: launch with `codex --yolo`; if network requests fail, run `/permissions` or restart with `codex --yolo resume`.
- Claude Code: launch with `claude`.
- GitHub authentication fixes: `gh auth login --web`.
- Codex login callback workaround: copy the URL and `curl "<URL>"` (example in `README.md`).

## Troubleshooting
- Push rejected as non-fast-forward: `git pull --rebase`, resolve conflicts, commit, push.
- Missing command/runtime: install it here (e.g., `npm install -g <package>`).
- Network failure: retry when connectivity is restored and tell the human if it remains blocked.

## References
- OpenAI agents: https://platform.openai.com/docs/guides/agents
- Codex CLI: https://github.com/continuum-llms/codex-cli
- Anthropic agents & Claude Code: https://docs.anthropic.com
