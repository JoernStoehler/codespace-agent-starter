# A Simple GitHub Repo Template For Projects with Claude Code / Codex CLI

## What is this?

I want to show a semi-quick but robust and good-enough way to use AI agents such as Codex CLI and Claude Code as a low-friction replacement with far more capabilities than the chat interfaces usually offer.

The following components are combined:
- A private GitHub repository to store and view files
- GitHub.com as a webpage to view and edit files
- Git for checkpointing so that AI mistakes can be undone even after several steps
- A GitHub Codespace as a remote machine that is quick to start and ready for AI agent usage
- The GitHub Codespace also has a web interface (VSCode) to view and edit files, and to start (one or multiple) terminals in which we can run claude code or codex CLI
- An instructions file (this file, README.md) for human users
- A basic, extensible instructions file (AGENTS.md == CLAUDE.md) for AI agents
- A subscription to ChatGPT Plus, Pro, Claude Pro, or Claude Max, so we don't have to bother with API keys

A few notes:
- AI agents know very well how to use Git, GitHub, Codespaces, VSCode, the command line, and how to interact with files in this environment. The AGENTS.md file provides the agents with the necessary context about where they are operating.
- AI agents can probably help you figure out not just how to do things, but also what to do and not do.

## First Setup Instructions

0. Go to the repository page: https://github.com/JoernStoehler/simple-agent
1. Click the green "Use this template" button at the top of this repository page.
2. Fill in the repository name (e.g. Jörn's Personal Knowledge Management), and choose whether to make it public or private.
3. Click "Create repository from template".
4. Go to the newly created repository page.
5. Click the green "Code" button, then click the "Codespaces" tab.
6. Click "Create codespace on main".
7. Wait for the codespace to start (this may take a few minutes the first time). Wait for the VSCode interface to load fully.
8. Open a terminal in VSCode. Ways to do this:
  - F1 then complete "> Terminal: Create New Terminal"
  - Or click the "Search-Icon <repo-name> [Codespaces: <adjective-noun>]" in the top menu bar, type ">", then type "Terminal" and select "Terminal: Create New Terminal"
  - Or use the menu burger in the top left corner, select Terminal, select New Terminal
  - Ctrl+Shift+C
9. Install your AI agent of choice:
  - `npm install -g @codex/cli` (the `-g` means global install, so you can run from anywhere)
  - `npm install -g @anthropic-ai/claude-code`
10. Start your AI agent of choice:
  - `codex --yolo`
  - `claude`
11. Authenticate your AI agent using your subscription (TODO: instructions for API keys)
  - For Claude Code:
    - Run `claude` and follow the login instructions.
  - For Codex CLI (yes, this one's awkward)
    - Run `codex --yolo`, follow the login instructions.
    - You will eventually be redirected to a `localhost` URL that won't load since the Codespace isn't your local machine.
    - Copy the full URL (`http://localhost:1455/auth/callback?code=ac_...`)
    - Open a second terminal in VSCode (see step 8)
    - Run `curl -X GET "<copied-url>"` in the second terminal, make sure to use double quotes around the URL without spaces.
    - The terminal should return empty output, meaning the authentication was successful. You can now close the second terminal.
    - The codex CLI should still look as if you aren't authenticated yet; just ignore that. Quit it with Ctrl+C and restart it with `codex --yolo`.
    - Run `/status` to verify that you are logged in.
12. Start your agent, ask it to tell you about the project and what example workflows it can do.
13. Enjoy!

## Regular Usage
1. Go to your repository page on GitHub.com.
2. Click the green "Code" button, then click the "Codespaces" tab.
3. Click "Open codespace" next to your codespace. Or click "New codespace" to create a new one.
4. Wait for the codespace, and then VSCode, to start (this should be faster now).
5. Open a terminal in VSCode (see step 8 above).
6. If you created a new codespace, you will have to authenticate again. Otherwise you should be good to go.
