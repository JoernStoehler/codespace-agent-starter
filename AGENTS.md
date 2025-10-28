# Agent Operating Guide

## Mission & Context
- You are operating inside a GitHub Codespace for the template repo described in `README.md`. Review that file whenever you need the big-picture goals or setup steps.
- Prioritize delivering helpful, incremental progress while keeping the repository in a good state for both humans and other agents.

## Quick Start Checklist
1. Run `git status` to understand the current working tree.
2. Run `git pull --rebase` to make sure you are up to date, unless the user explicitly requests otherwise.
3. Skim `README.md` for any changes since your last session.
4. Confirm the active branch with `git branch --show-current`; stay on `main` unless directed to create another branch.

## Core Practices
- **Commit & push frequently:** Stage (`git add -A`), commit (`git commit -m "Brief summary"`), and push (`git push`) after each self-contained change or at least every few steps. Do this proactively; do not wait for the user to ask.
- **Explain your work:** Note what you changed and why in commit messages and conversation summaries.
- **Keep changes scoped:** Avoid mixing unrelated updates in the same commit.
- **Respect existing files:** Never revert user-provided changes unless asked.
- **Flag uncertainties quickly:** If something is ambiguous, ask the user before proceeding.

## Git Workflow
- **Staging & committing**
  ```bash
  git add -A
  git commit -m "Describe the change in one sentence"
  ```
- **Pushing**
  ```bash
  git push
  ```
- **If no upstream branch exists**
  ```bash
  git push -u origin $(git branch --show-current)
  ```
- **Review before you commit:** `git diff` to check your work.
- **Troubleshooting auth errors:** Use `gh auth login --web` to refresh GitHub credentials if `git push` fails with authentication issues. Run `git remote -v` to confirm the remote URL.

## Tooling Reference
- **Codex CLI**
  - Start: `codex --yolo`
  - Docs: https://github.com/continuum-llms/codex-cli and https://www.npmjs.com/package/@codex/cli
  - Ensure you are logged in (`/status`) before running long sessions.
- **Claude Code**
  - Start: `claude`
  - Docs: https://docs.anthropic.com/en/docs/build-with-claude/claude-code/overview
  - Authenticate from within the Codespace UI if prompted.

## Official Guides & References
- OpenAI Agents Quickstart: https://platform.openai.com/docs/guides/agents
- Anthropic Agent Guide: https://docs.anthropic.com/en/docs/agents/overview
- Anthropic Claude CLI Setup: https://docs.anthropic.com/en/docs/build-with-claude/claude-code/install
- GitHub Codespaces documentation: https://docs.github.com/en/codespaces

## Example Workflows
- **Document a new onboarding tip**
  1. Capture the idea in `README.md`.
  2. Update `AGENTS.md` if agents need new guidance.
  3. Run `git status`, review changes, then commit and push.
- **Run a check and summarize**
  1. Execute the relevant command, e.g. `npm test`.
  2. Summarize the output in the conversation.
  3. Commit documentation or code updates related to the findings.
- **Sync with external edits**
  1. `git pull --rebase`
  2. Resolve any conflicts, documenting the resolution.
  3. Re-run applicable checks, then commit and push.

## Troubleshooting
- **`git push` fails (network):** Verify the Codespace has outbound network access. If DNS resolution fails, wait and retry or ask the user to enable network connectivity.
- **`git push` fails (auth):** Run `gh auth login --web`, then retry.
- **`git push` fails (non-fast-forward):** Run `git pull --rebase` to integrate remote changes, resolve conflicts, then push.
- **Agent cannot reach authentication URL:** Copy the login URL, open a new terminal, and use `curl "<URL>"` as described in `README.md`.
- **Command missing:** Install globally (`npm install -g <package>`) within the Codespace.
- **Network commands blocked in Codex:** In `/status` look for sandbox warnings; run `/permissions` or restart with `codex --yolo resume` to re-request elevated access.

## Communication Notes
- Always summarize the current state, mention pending tasks, and suggest logical next steps for the user.
- If you encounter unexpected repository changes you did not make, pause and ask how to proceed.
- Keep the tone professional, concise, and focused on helping the user move forward.
