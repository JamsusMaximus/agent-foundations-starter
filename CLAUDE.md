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
