# Agent Foundations Starter

Starter folder for building your first AI agent in the [Agent Accelerator](https://jamesmcaulay.co.uk/agent-accelerator). Clone or download, then open it in **Cowork**, **Claude Code**, **Cursor**, or any folder-aware AI tool.

For the full participant tutorial (with screenshots), see the chapter Google Doc James shared. This README is the kick-off prompt for clone-and-go users.

---

## Get started

**Quickest path — let the skill drive it.** In **Claude Code** (or **Cowork** with the
starter's skills installed), start a chat and say **"set up my second brain"** (or run
`/set-up-my-second-brain`). It checks what's here, runs the interviews one at a time,
and saves everything for you. Prefer to drive it by hand? Use the prompt below.

**First, get this folder in front of your agent:**

- **Cowork / Claude Code / Cursor (folder tools):** [download the ZIP](https://github.com/JamsusMaximus/agent-foundations-starter/archive/refs/heads/main.zip), unzip it, and open the folder in your tool. (Comfortable with git? `git clone` instead.) Step-by-step screenshots are in the participant tutorial Google Doc James shared.
- **Plain claude.ai or ChatGPT chat (no folder):** a normal chat can't open a folder and won't remember anything next session. Create a **Project** (Claude) or equivalent, upload these files into it, and work there — that's what makes your context persist.

**Then start a new chat and paste:**

```
I'm setting up the agent-foundations-starter. The files are in this
workspace — if you can see a folder, read it; if you can't, I'll paste
files in as you ask for them.

Please:
1. Read the README and skim the folder structure so you know what's here.
2. Read the instructions file (CLAUDE.md if you're Claude, AGENTS.md if
   you're Codex) so you know how I want to be coached.
3. Check which of these are still missing/placeholder vs filled in:
   - context/role-profile.md
   - context/linkedin.md
   - context/background-research.md
   - goals.md
   - the coaching style in CLAUDE.md / AGENTS.md (the most important one)

For each gap, walk me through it using the matching prompt from prompts/,
ONE at a time. Before each, ask if I already have a doc that covers it
(CV, LinkedIn PDF, JD, OKRs, a deck) so I don't retype it, and push me
for specifics if I answer too briefly. Do background research LAST.

Save each output to the right file, then check with me before the next.
```

That's it. Your agent takes you through the rest.

---

## What's in here

```
.
├── README.md                       This file
├── CLAUDE.md                       System prompt (placeholder until you run the Coaching Style Interview)
├── guardrails.md                   Safety rules for any agent in this folder
├── goals.md                        Your 2026 goals (living doc)
├── editor-recommendations.md       Free markdown editors if you don't have one
│
├── context/                        Static reference material — written once, updated occasionally
│   ├── role-profile.md             Output of the Role Profile Interview
│   ├── linkedin.md                 Your career arc (from LinkedIn export)
│   └── background-research.md      Public info about your company (output of Background Research)
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

1. **Role Profile Interview** — `prompts/role-profile-interview.md`. Output → `context/role-profile.md`.
2. **LinkedIn export** — `prompts/linkedin-export.md`. Output → `context/linkedin.md`.
3. **Goals** — fill in `goals.md` directly (or attach your existing OKRs / planning doc).
4. **Coaching Style Interview** — `prompts/coaching-style-interview.md`. Output replaces `CLAUDE.md` at the root (or write `AGENTS.md` if you're on Codex).
5. **Background Research** — `prompts/background-research.md`. Do this **last**, then reconcile it against what you wrote above — your own context wins on any conflict.

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

**Your answers are personal.** `CLAUDE.md`, `goals.md` and the `context/` files hold your own details. A `.gitignore` keeps new personal files out of git, but the shipped placeholders are already tracked — so if you don't want your answers under version control (or you hit conflicts on `git pull`), either **fork** this repo, or run once: `git rm --cached CLAUDE.md goals.md context/*.md`.

---

## Licence

Provided as-is for Agent Accelerator participants. Feel free to fork and adapt for your own use.
