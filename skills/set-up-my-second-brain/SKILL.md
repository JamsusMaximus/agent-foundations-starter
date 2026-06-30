---
name: set-up-my-second-brain
description: >
  Build solid, personalised context (a "second brain") by running the proven
  agent-foundations-starter setup - role profile, career (LinkedIn), company
  background, goals and coaching style - so the agent deeply understands the user
  and helps them hit their goals. ALWAYS inspects existing context by READING
  CONTENT (not filenames) first, fills only genuine gaps, never overwrites real
  user content, and ends with a synthesis so the user gets real insight into their
  goal and what's in the way. Use when the user says "set up my context / second
  brain", "onboard me", "fill in my context files", "check my setup", or opens a
  workspace and wants the agent to learn about them.
---

# Set up my second brain

Build genuinely solid context about the user by running the proven starter-agent
interviews thoroughly - that thoroughness is what gets great results. The context
is the foundation; once it's built, a synthesis turns it into goal-focus and
self-awareness. Don't shortcut the interviews, and don't reinvent them - the repo
is the proven source of truth.

**Not running under Claude Code?** Codex, Cursor, plain claude.ai/ChatGPT chat and
most other tools don't auto-load a `skills/` folder, so this skill won't fire by
name. If you're one of those, the user has likely just pasted this file's contents
into a chat - that's fine, follow it as written from here.

**Source the prompts locally first.** If the starter folder is already open (the
common case - it ships `prompts/`, `context/`, `README.md`), READ THOSE LOCAL FILES.
Only fall back to the live repo if a file is genuinely missing - many coding-agent
sandboxes (e.g. Codex) block network by default, and fetching a file that's sitting
next to you just wastes a call or stalls. Live fallback:
`https://raw.githubusercontent.com/JamsusMaximus/agent-foundations-starter/main/`

The pieces: role profile · career (LinkedIn) · company background · goals · coaching
style. The **coaching-style** interview is the important one - it captures the
user's derailing patterns (their "shadows") and how they want to be challenged
(drill-sergeant / sparring-partner / trigger questions), so the agent ends up
challenging them toward their goals, not just obeying. Don't let this one get
skimmed.

## Step 0 - Inspect what exists, and check it's safe to build here

Filenames lie - a file can be empty, a placeholder, or stale. Judge by content.

1. **Find context anywhere** - a `context/` folder, the named files, or any other
   file holding real info about the user (a big `CLAUDE.md`, `notes.md`). Read it.
2. **Classify each piece** by content: COVERED (real content) / PLACEHOLDER-EMPTY
   (template/headings only -> a GAP) / PARTIAL (fill empty sections) / MISSING.
3. **Flag conflicts BEFORE classifying.** Re-read what the user has said this
   session for any update or contradiction to a file (e.g. "I moved to Beta as VP
   Product"). If you find one, surface and resolve it before building anything else
   - stale identity poisons every downstream file. When two sources disagree, show
   the user the actual diverging text and ask which is right; never resolve it
   silently or mark both COVERED.
4. **Report plainly - don't hedge.** If files are placeholders or empty, say so
   directly ("X isn't actually filled in yet"); don't soften it into "looks mostly
   good". If the user believes they're already set up, correct that clearly before
   proceeding. If real content exists, say what's covered vs not and ask them to
   confirm it's still current, probing high-churn things (role, company, goals).
   Skip the currency question on an empty folder.
5. **Surface check - do this FIRST, before any interview.** Work out what this
   surface can do, and say so plainly before investing the user's time:
   - **No filesystem at all** (plain claude.ai / ChatGPT chat with no folder): you
     can't read or write files, and nothing here persists to the next chat. Say this
     up front. Recommend they move to a **Claude Project** (or ChatGPT "Project" /
     a folder tool) and upload these files so their context survives - that is the
     single biggest thing that makes a second brain worth building. If they want to
     continue in plain chat anyway, run the interviews but warn that they must save
     each output themselves, and never pretend to have saved a file.
   - **Can read but not write** (some Cowork surfaces): you'll output finished content
     for them to paste, with plain instructions on where each piece goes (see Step 3).
   - **Full read/write** (Claude Code, Cursor, most coding agents): save directly.
6. **Location check:** if this is an unrelated software project / work repo (`src/`,
   `package.json`, app code) rather than a personal-context folder, warn that personal
   context could get committed and offer a dedicated personal folder. BUT if this IS
   the agent-foundations-starter itself (it ships `prompts/` + placeholder `context/`),
   this is the intended home - don't suggest moving. Instead, if the personal files
   are git-tracked against the shared upstream, suggest they fork (or add a
   `.gitignore`) so their answers aren't pushed and `git pull` won't collide.
7. **Respect their setup** - if they have a working structure they don't want
   restructured, fill genuine gaps / fix conflicts only, with consent.
8. **Identify the instructions file** - the file the host agent auto-loads each
   session, which is where coaching style lands. Convention differs by tool:
   `CLAUDE.md` / `claude.md` for Claude, `AGENTS.md` for Codex and most other agents.
   Scan the folder and decide:
   - One of them already exists -> that's your target.
   - Both exist -> ask which tool they mainly use, and don't duplicate coaching style
     across both (pick one canonical file, point the other at it if needed).
   - Only the starter's `claude.md` is here but you're running as Codex (or they say
     they'll mainly use an AGENTS.md tool) -> target `AGENTS.md` so it actually gets
     loaded. Don't copy the `claude.md` placeholder across - it's just a to-do stub
     ("run the coaching interview, then replace this"). Write the *rendered* coaching
     style into `AGENTS.md`, and leave a one-line pointer in `claude.md` ("coaching
     style now lives in AGENTS.md") so the orphan doesn't mislead the next session.
   - Neither / genuinely unsure -> just ask "Claude or Codex (or another tool)?" once.
   You usually know this already - you're the host agent running the skill - so infer
   first and only ask when it's truly ambiguous.
   - **For Claude, prefer uppercase `CLAUDE.md`** (the standard, and it loads on
     case-sensitive filesystems too) over the starter's lowercase `claude.md`.

If a memory-extraction was run first, its `context/` files are what you detect here.

## Step 1 - Pull the proven setup from the repo

Read (local first, per the note above; fetch only if missing), for the gaps only:
`README.md` (folder structure + the "first real chat" prompts) plus the matching
prompts - all under `prompts/`: `prompts/role-profile-interview.md`,
`prompts/linkedin-export.md`, `prompts/background-research.md`,
`prompts/goals-template.md`, `prompts/coaching-style-interview.md`.

**If you have neither local files nor web access** (e.g. plain chat, no folder, no
fetch): don't halt, and don't invent the questions from memory. Instead, help the
user fetch them by hand. First explain the overall shape so they know what they're in
for - five short pieces, done one at a time, roughly 5-15 min each:

1. **Role profile** - who you are and what you do
2. **LinkedIn / career** - your career arc
3. **Goals** - what you're working toward
4. **Coaching style** - how you want to be challenged (the important one)
5. **Background research** - your company and market (done last)

Then give them the clickable links and walk them through it: "Open each link, click
**Raw** (or just copy the text), paste it back to me here, and we'll do them in order,
one at a time. Start with the first:"

- Role profile: https://github.com/JamsusMaximus/agent-foundations-starter/blob/main/prompts/role-profile-interview.md
- LinkedIn / career: https://github.com/JamsusMaximus/agent-foundations-starter/blob/main/prompts/linkedin-export.md
- Goals: https://github.com/JamsusMaximus/agent-foundations-starter/blob/main/prompts/goals-template.md
- Coaching style: https://github.com/JamsusMaximus/agent-foundations-starter/blob/main/prompts/coaching-style-interview.md
- Background research: https://github.com/JamsusMaximus/agent-foundations-starter/blob/main/prompts/background-research.md

Take the pasted prompt, run that interview, then ask for the next link. Don't make
them paste all five at once.

## Step 2 - Run the interviews thoroughly, filling gaps

Work through the gaps one piece at a time and **follow each prompt exactly** - most
are one-question-at-a-time interviews; respect that (no dumping all questions, no
summarising between answers). This thoroughness is what makes the context solid.
Fill missing sections **within** a partial file too; say what you're skipping.

**Order (this deliberately overrides the repo README's running order):** start with
the **role-profile interview**, then LinkedIn / career, then goals, then the
coaching-style interview. Do **background research LAST, never first** - the user's
own context comes first, and the research is reconciled against it once it's built.

**On every question, do these three things:**

1. **File first.** Before asking them to answer cold, ask if they already have a
   document that covers it - a LinkedIn PDF, job description, CV, deck, OKR doc,
   self-review, an old `notes.md`. If they do, read it and confirm what you extracted
   instead of making them retype it. (State the bigger shortcuts up front: before the
   career and goals sections especially.)
2. **Push on thin answers.** A one-word or one-line answer is a starting point, not
   the record. Probe once for the specifics that make context useful - a concrete
   example, a number, a "why", a recent instance - before moving on. Don't bank a
   shrug; don't interrogate either - one good follow-up, then move.
3. **Offer choices where it helps.** When a question has natural options, present them
   as a multiple-choice pick (via `AskUserQuestion` if your host supports it, else a
   plain numbered list) so they choose rather than free-type from cold - then let them
   add nuance. Good fits: coaching style (drill-sergeant / sparring-partner / trigger
   questions), how challenged they want to be, role type, goal time-horizon. Free-text
   is better for open, personal answers (their actual goal, their "shadows").

- **Privacy (state up front):** flag and leave out by default anything personal or
  sensitive - health, relationships, money, emotion, sensitive professional
  transitions, and any third-party/safeguarding data. Ask before recording.

### Background research - the last piece, and the one exception to "follow the prompt exactly"

`prompts/background-research.md` is written for a *separate* research tool, so don't
relay it verbatim. Handle it last, and let the user choose how it runs:

First ask for internal docs (a deck, strategy doc, QBR, investor update) - they beat
any web research. Then pick the route by what your surface can do:

- **If you can search the web yourself** (Claude Code, Cursor, most coding agents,
  Cowork with web tools): just run it now, inline, using the prompt's sources,
  accuracy rules and structure. This is the default - don't make them leave the tool.
- **Optional richer pass:** mention they *can* get a deeper profile by running it in a
  proper "Deep Research" mode (a slower setting in Claude or ChatGPT that browses the
  web for ~5-10 min; Perplexity if they're on a free plan), pasting the repo prompt
  with `[COMPANY]` / `[DOMAIN]` filled in plus any docs, then bringing the output
  back. Offer it as an upgrade, not the first hurdle - and explain in one plain
  sentence what "Deep Research" is, since most people have never used it.
- **If you can't search at all:** say so, and either route them to Deep Research as
  above or have them paste in what they know about the company.
- **On the way back, reconcile - don't just file it.** Cross-check the research
  against what's already in `context/` (role profile, LinkedIn, goals). **Always
  defer to context the user gave you:** where the research disagrees with the user's
  own statements or docs, the user wins - flag the discrepancy, keep their version,
  and record the research as "public sources say X" rather than overwriting. Delete
  or correct anything obviously wrong before saving.

## Step 3 - Propose, reconcile, save

- Propose each section's content and let them correct it before saving. For a terse
  user, a one-line "save this? (yes / tweak / skip)" is fine.
- **Never overwrite real user-written content** without approval. You MAY fill
  placeholders. On a conflict, show it, ask which is right, then update - noting the
  change. **One canonical file per piece; no duplicates.**
- **Canonical output files** (match the repo layout exactly - don't invent variants):
  - role profile -> `context/role-profile.md`
  - LinkedIn / career -> `context/linkedin.md`
  - company background -> `context/background-research.md`
  - goals -> `goals.md` (repo root)
  - coaching style -> the instructions file from Step 0 (`CLAUDE.md` for Claude,
    `AGENTS.md` for Codex and others), at root
- **Coaching style goes in the instructions file**, not a separate
  `context/coaching-style.md`. The starter ships `claude.md` as a placeholder system
  prompt, so for Claude you replace it - saving as **uppercase `CLAUDE.md`** (the
  standard; also loads on case-sensitive Linux/CI, where lowercase `claude.md` would
  be silently ignored). For Codex (or another AGENTS.md-based tool) write `AGENTS.md`
  so the host actually loads it. One canonical copy only - don't duplicate it across
  both files or into `context/`. (Mac note: `claude.md` and `CLAUDE.md` are the same
  file on macOS, so renaming in place is safe; never end up with both.)
- **Wire the rest in so it actually loads.** Many hosts auto-load only the instructions
  file (Claude Code loads `CLAUDE.md` and its `@`-imports; nothing else). So in that
  file add an `@guardrails.md` import (the starter's safety rules, otherwise orphaned)
  and a one-line pointer to read `context/` each session - otherwise the guardrails
  and all the context you just built sit unread on disk.
- **A pre-existing user-authored instructions file is theirs - never overwrite it.**
  If `CLAUDE.md` / `AGENTS.md` already holds real content (not the starter
  placeholder), don't clobber it: merge the coaching style into a clear "How to coach
  me" section with consent, and skip it entirely if it's a code-project file - at most
  append ONE pointer line ("read `context/` each session; it's the source of truth").
- **No-write surface:** output the final content for them to save, and make it
  followable by a non-technical user - don't just say "save as `context/role-profile.md`".
  For each piece, say in one plain sentence what it is and exactly how to save it in
  their tool (e.g. "This is your role profile. In your folder, open the `context`
  folder, make a new file called `role-profile.md`, and paste this in."). If they have
  no folder at all (plain chat), remind them to keep these somewhere reusable - a
  Claude Project or a doc - or it's gone next session. Don't claim to have saved.

## Step 4 - The synthesis (don't skip - this is what makes the context pay off)

Once the context is solid, read everything you now know and, without being asked,
tell them: what you understand about them and what they're really working toward,
what you think is genuinely getting in the way - **drawing on the derailing patterns
they named in the coaching-style step (their shadows)** - one breakthrough possible
soon, and the first concrete step they could take today. Point to specifics in their context,
then invite them to push back - the sharpest insight usually comes when they correct
your first read. (The repo's README has ready "first real chat" prompts for this.)

End by listing what's now covered, any remaining gaps, and a `NEEDS-VERIFYING` list.
The folder is portable - it moves into Cowork, a coding agent, or any future tool.
