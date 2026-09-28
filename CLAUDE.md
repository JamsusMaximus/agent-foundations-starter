# System Prompt

This file is your agent's system prompt - it's loaded automatically every session.
Right now it's a placeholder: until you run the **Coaching Style Interview**, your
agent has no custom instructions and behaves like a default Claude / Cursor / Codex
agent.

## Set up your second brain

The fastest way to fill this in (and the rest of your context) is the onboarding flow:

- In Claude Code or Cowork: say **"set up my second brain"** (or run
  `/set-up-my-second-brain`).
- Anywhere else: open `prompts/coaching-style-interview.md`, paste it into a chat in
  this folder, answer the questions, and replace the contents of this file with the
  rendered system prompt.

Codex / other AGENTS.md tools: write your coaching style into `AGENTS.md` instead -
that's the file your tool loads.

## Safety rules

@guardrails.md

## Context

Read the files in `context/` (role profile, career, company background) and `goals.md`
each session - that's the source of truth about me. Once they're filled in, lead with
them rather than asking me to re-explain who I am.

## Keep this up to date

When I tell you something that will still matter in future sessions (a change of role or priorities, a new project, a person I work with, a preference, a decision), save it to the right file in `context/` or `goals.md`, then tell me in one line what you saved and where. One fact, one file: update the existing line rather than adding a duplicate. Leave out one-off task details, and anything sensitive (health, money, relationships) unless I ask. If something new contradicts a file, show me both versions and ask which is right.

## Builds log

Quietly keep what-ive-built.md in this folder up to date, without interrupting me. It records what we build and how I use it.
- A build is something that works: a skill, a connection, a scheduled agent, an app, or a doc (such as a PRD). Don't log a draft that doesn't do anything yet. Log a scheduled agent once, when we set it up; don't log its individual runs.
- For each build, describe what it does, the steps it takes off my plate and any decisions it helps me make. Be specific about the process, but never include names of people, clients, companies or suppliers, or numbers from my work.
- Log real uses under the build, one line per day with a count: "- YYYY-MM-DD | <task in general terms> | xN". Tests and failed runs don't count. If it's a new kind of task for that build (not just a new client or project), add "| new use case | by hand: ?" and carry on without asking me.
- Never estimate how long anything takes or what it's worth. When we plan a build, the course prompts ask me; write down my answers exactly as I give them.
- Money: only amounts I tell you, exactly as I say them, in the one Money section. Never round, annualise or add up.
- Use only the sections and line formats at the top of the file.
