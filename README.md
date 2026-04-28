# Agent Foundations Starter

Starter folder for building your first AI agent in the [Agent Accelerator](https://jamesmcaulay.co.uk/agent-accelerator). Clone or download, then open it in **Cowork**, **Claude Code**, **Cursor**, or any folder-aware AI tool.

For the full participant tutorial (with screenshots), see the chapter Google Doc James shared. This README is the kick-off prompt for clone-and-go users.

---

## Get started — paste this into your agent

Open the cloned folder in Cowork or your coding agent. Start a new chat and paste:

```
I've just cloned the agent-foundations-starter into this folder.

Please:
1. Read the README and skim the folder structure so you know what's here.
2. Read claude.md (root) so you know how I want to be coached.
3. Check which of these context files are still placeholders vs filled in:
   - context/role-profile.md
   - context/linkedin.md
   - context/background-research.md
   - goals.md
   - claude.md (root — this is the system prompt)

For each one that's still a placeholder, walk me through filling it in
using the matching prompt from prompts/. Pick whichever you think will
take least time to a useful state and start there.

If I have any existing docs (role description, OKRs, working-style
notes, a pitch deck) I can attach now and you can use them to short-cut
the relevant interview - say "if you have a [type of doc], drop it in
now and I'll work from that instead of running the full interview."

Don't try to fill them all in one shot - do one, save the output to the
right file, then ask me before moving on to the next.
```

That's it. Your agent takes you through the rest.

---

## What's in here

```
.
├── README.md                       This file
├── claude.md                       System prompt (placeholder until you run the Coaching Style Interview)
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
    └── humanise-writing/
        └── SKILL.md
```

---

## Running order

If you'd rather drive the process yourself instead of using the prompt above:

1. **Background Research** — kick off first; it runs for 5-10 minutes in the background. See `prompts/background-research.md`.
2. **Role Profile Interview** — `prompts/role-profile-interview.md`. Output goes into `context/role-profile.md`.
3. **LinkedIn export** — `prompts/linkedin-export.md`. Output goes into `context/linkedin.md`.
4. **Goals** — fill in `goals.md` directly (or attach your existing OKRs / planning doc and let the agent reference it).
5. **Coaching Style Interview** — `prompts/coaching-style-interview.md`. Output replaces `claude.md` at the root.

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

---

## Licence

Provided as-is for Agent Accelerator participants. Feel free to fork and adapt for your own use.
