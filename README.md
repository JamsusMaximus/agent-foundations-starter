# Agent Foundations Starter

Prompts and skills for building your first AI agent in the [Agent Accelerator](https://jamesmcaulay.co.uk/agent-accelerator). You don't need to download or clone anything: your agent fetches what it needs from here while it sets you up.

---

## Get started

1. **Make a folder called `secondbrain`** on your computer.
2. **Open it in your AI app:** Claude Code, Codex, Claude or ChatGPT.
3. **Paste in the Master Interview Prompt**, copied from Chapter 1 of the Agent Accelerator course page.

Your agent fetches the [`set-up-my-second-brain`](skills/set-up-my-second-brain/SKILL.md) skill from this repo and runs it: it interviews you one piece at a time and saves everything into your `secondbrain` folder. It opens with three quick questions (where you want to be in five weeks, and a year from now) and saves a first draft of your five-week mission within about ten minutes.

The full set-up usually takes 90 minutes to 3 hours, and you can do it over a few sittings: stop when you need to and pick it back up later.

When it says **"Second Brain interview complete ✅"**, go back to the course page for the next step.

---

## What's in here

```
.
├── README.md                       This file
├── CLAUDE.md                       System prompt (placeholder until you run the Coaching Style Interview)
│                                   On Codex/other AGENTS.md tools, an AGENTS.md is created to hold this instead
├── guardrails.md                   Safety rules for any agent in this folder
├── editor-recommendations.md       Free markdown editors if you don't have one
│
├── context/                        Facts about you — written once, updated occasionally
│   ├── goals.md                    Your goals (living doc)
│   ├── role-profile.md             Output of the Role Profile Interview
│   ├── linkedin.md                 Your career arc (from LinkedIn export)
│   └── background-research.md      Public info about your company (output of Background Research)
│
├── projects/                       One folder per piece of work with a finish line (created when needed)
├── notes/                          Meeting notes and ideas, one dated file each (created when needed)
├── sources/                        Original files you drop in: CV, LinkedIn PDF, decks (created when needed)
│
├── prompts/                        Interview prompts and templates — paste these into chats
│   ├── role-profile-interview.md
│   ├── coaching-style-interview.md
│   ├── background-research.md
│   ├── linkedin-export.md
│   └── goals-template.md
│
└── skills/                         Reusable agent skills (covered properly in Week 2)
    ├── README.md
    ├── set-up-my-second-brain/     The onboarding flow (this folder's setup)
    ├── crystallise-memory/
    ├── humanizer/
    ├── multi-agent-refine/
    ├── owasp-security-check/
    ├── prd/
    └── weekly-retro/
```

---

## Running order

The `set-up-my-second-brain` skill does this for you. To drive it yourself, do your
own context first and the company research last:

0. **Three quick goal questions** - where you want to be in about five weeks and a year from now. Then ask for a short five-week mission (the goal, what's in the way, a first step) and save it at the top of `context/goals.md`.
1. **Role Profile Interview** - `prompts/role-profile-interview.md`. Output → `context/role-profile.md`.
2. **Goals** - fill in `context/goals.md` directly (or attach your existing OKRs / planning doc), building on the quick questions.
3. **LinkedIn export** - `prompts/linkedin-export.md`. Output → `context/linkedin.md`.
4. **Coaching Style Interview** - `prompts/coaching-style-interview.md`. Output replaces `CLAUDE.md` at the root (or write `AGENTS.md` if you're on Codex).
5. **Background Research** - `prompts/background-research.md`. Do this **last**, then reconcile it against what you wrote above: your own context wins on any conflict.

---

## The first real chat

Once everything's set up, run these two prompts in order in a fresh chat:

**Prompt 1 — Synthesis + diagnosis:**

```
Take a moment to read everything you know about me - my goals, role
profile, background, and anything else I've shared. Without me having
to brief you, tell me:

- What you see as my biggest goal right now
- What you think is actually getting in the way
- One breakthrough that's possible in the next four weeks
- The first concrete step I could take today

Point to specific things in my context where you can. I want your
actual read, not a checklist of options.
```

**Prompt 2 — Push to commitment:**

```
Good. Now we've narrowed it down: what would be different in my world
four weeks from now if I made real progress on this? Be specific - what
would I have shipped, said, decided, or stopped doing? And what's the
smallest version of step one I can do this afternoon, before the day
ends?
```

The first answer is a draft. **Push back.** Tell it where it's wrong about your situation. Tell it which obstacle it missed. The breakthrough usually comes in round 2 or 3, not round 1.

---

## Keeping up to date

Pull updates between cohorts:

```bash
git pull origin main
```

If you've edited any of the placeholder files, your edits stay; only files we change at source (templates, README, prompts) will update.

**Your answers are personal.** `CLAUDE.md` and the files in `context/`, `projects/`, `notes/` and `sources/` hold your own details. A `.gitignore` keeps new personal files out of git, but the shipped placeholders are already tracked — so if you don't want your answers under version control (or you hit conflicts on `git pull`), never push them to a fork (a fork of this public repo is public too). Keep them local, or push to a new **private** repo, or run once: `git rm --cached CLAUDE.md context/*.md`.

---

## Licence

Provided as-is for Agent Accelerator participants. Feel free to fork and adapt for your own use.
