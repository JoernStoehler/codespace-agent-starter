# Simple Codespace Template for Codex CLI / Claude Code

## Why this exists
The template gives you a Codespace that is already friendly to AI agents. You get:
- A repo and Codespace you can clone without extra setup.
- `README.md` for humans and `AGENTS.md` / `CLAUDE.md` for agents.
- A workflow that keeps commits small so mistakes are easy to undo.

If you already have an environment you trust, you can ignore this. Otherwise the sections below walk you through the minimal steps.

## Before you start
- GitHub account with access to create repositories and Codespaces.
- Active subscription that allows `@openai/codex` and/or `@anthropic-ai/claude-code`.
- A few minutes in the Codespace terminal; everything else is point-and-click.

## One-time setup
1. **Copy the repo**
   - Visit https://github.com/JoernStoehler/simple-agent.
   - Click **Use this template**, choose a name and visibility, then create the repo.
2. **Create a Codespace**
   - On your new repo, click **Code → Codespaces → Create codespace on main**.
   - Wait for the VS Code UI to load fully.
3. **Open a terminal inside the Codespace**
   - `F1` → `> Terminal: Create New Terminal`, or use the top menu (**Terminal → New Terminal**), or `Ctrl+Shift+C`.
4. **Install the CLIs you need**
   ```bash
   npm install -g @openai/codex    # docs: https://github.com/openai/codex
   npm install -g @anthropic-ai/claude-code
   ```
   Skip the one you do not plan to use.
5. **Authenticate**
   - **Claude Code**
     1. Run `claude`.
     2. Follow the browser prompts to log in.
   - **Codex CLI (Codespace workaround)**
     1. Run `codex --yolo` and start the login flow.
     2. When the browser shows `http://localhost:1455/auth/callback?...`, copy that full URL (the page itself will not load).
     3. Open a second terminal tab and run:
        ```bash
        curl -X GET "<copied-url>"
        ```
        Keep the URL inside double quotes.
     4. The command prints nothing if the login succeeded. Close the second tab.
     5. Restart `codex --yolo`, run `/status`, and confirm you are logged in. If it still claims you are logged out, try again; if that fails, give up since OpenAI broke their headless login flow again.
6. **Verify everything works**
   - Run `codex --yolo` and/or `claude` to start an agent.
   - Ask it to check if the environment is set up correctly.
   - Ask it to onboard you and present the typical workflow from your perspective.
   - Ask it to edit `AGENTS.md` if you have custom instructions for your AI agents.

## Day-to-day usage
1. Reopen the Codespace from your repo (Code → Codespaces).
2. Launch `codex --yolo` or `claude`.
3. If this is a brand-new Codespace, repeat the login step; otherwise you should be ready immediately.
4. The agents will use git to checkpoint changes automatically, as per `AGENTS.md`.

## Where agents look for guidance
- `AGENTS.md` — main set of operating instructions.
- `CLAUDE.md` — just forwards to `AGENTS.md`.
- External references:
  - AGENTS.md format: https://agents.md
  - Codex CLI: https://github.com/openai/codex
  - Claude Code: https://claude.md

If you change how the repo should be used, update `AGENTS.md` so the next agent sees it.
