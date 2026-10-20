# Agent setup

Practice starting an AI coding agent and logging it in, inside a Codespace. The agent works in
the terminal next to your code: it can read your files, run them, run the tests, and fix what
fails. The login lives inside each Codespace, so you will do this again every time you start a
new one. Learn it here, where nothing else depends on it.

## 1. Get your own copy and open it

1. Click **Use this template**, then **Create a new repository**. Keep it private.
2. In your new repository, click **Code**, then the **Codespaces** tab, then **Create codespace
   on main**.
3. Wait for the setup to finish (a few minutes the first time). The terminal at the bottom is
   ready when it shows a prompt and stops scrolling.

## 2. Start your agent and log in

Every Codespace from this repo has three agent CLIs installed. Use one you have an account for:

| Agent | Start it with | Account |
|---|---|---|
| Claude Code | `claude` | a paid Claude plan (Pro or above) |
| Codex | `codex` | a ChatGPT plan that includes Codex |
| Antigravity CLI | `agy` | a Google account |

Type the command in the terminal and follow the prompts. The first time, it asks a few setup
questions (colors, and whether to trust this folder); trust the folder. Then it gives you a
sign-in link. After you sign in, one of two things happens:

- The page shows a code. Copy it and paste it into the terminal.
- The page fails to load ("This site can't be reached"). That is expected: the agent is waiting
  for the address, not the page. Copy the **whole address** from the browser's address bar and
  paste it into the terminal.

Gemini CLI (`gemini`) is installed too, for anyone with a work or paid Gemini account. Copilot
CLI and Cursor also read this repo's instructions, but you would install them yourself.

## 3. Check that it works

Ask the agent these two things:

1. "What rules are you following in this repo?" It should describe the rules in `AGENTS.md`:
   how to run files and tests, how the database changes, and to ask before deleting data.
2. "Run hello.rb." It should run `bin/rails runner hello.rb` **without asking you first**, and
   show the greeting.

If both work, you are done. If either doesn't, ask for help now, while there is time to fix it.

## Every new Codespace after this

The same three moves, in whichever repository you are working in: start the agent, log in, and
ask the rules question once. The login does not carry over from one Codespace to the next.

## If something goes wrong

- **"command not found"** when you type the agent's name: open a new terminal with the **+** on
  the terminal panel and try again.
- **The rules answer doesn't mention `AGENTS.md`:** check that the terminal is in the top folder
  (the one with this README), then quit the agent and start it again.
- **"Run hello.rb" asks for permission first:** say yes this time, and ask for help. The
  agent's settings did not load.
- **The login keeps failing:** quit the agent (**Ctrl-C**, sometimes twice) and start it again.
  If you have access to a second agent, try that one.

## Why the agent follows this repo's rules

`AGENTS.md` is plain-English instructions that every agent reads before it starts. Next to it
are each agent's settings (`.claude/`, `.codex/`, `.gemini/`): routine commands such as running
a file or the tests go ahead without a permission prompt, and anything that deletes data always
asks. You can open and read all of it. That is most of what makes an agent predictable: written
instructions, and limits on what it may do without asking.

The rest of the repo is `hello.rb`, a one-line Ruby file to run, and a small Rails app for the
agents to work in.
