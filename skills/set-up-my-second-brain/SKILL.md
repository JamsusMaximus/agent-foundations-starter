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

Repo (read live; raw files):
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
5. **Surface check:** if you can't write files here (some Cowork surfaces), say so
   now - you'll output the content for them to save, not pretend to.
6. **Location check:** if this looks like a software project / work repo (`src/`,
   `.git`, `package.json`), warn that personal context could get committed, and
   offer to target a dedicated personal folder instead.
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
     they'll mainly use an AGENTS.md tool) -> use `AGENTS.md` instead, so it actually
     gets loaded; migrate the placeholder content over rather than leaving an orphan.
   - Neither / genuinely unsure -> just ask "Claude or Codex (or another tool)?" once.
   You usually know this already - you're the host agent running the skill - so infer
   first and only ask when it's truly ambiguous.

If a memory-extraction was run first, its `context/` files are what you detect here.

## Step 1 - Pull the proven setup from the repo

Fetch and read, for the gaps only: `README.md` (running order) plus the matching
prompts - all under `prompts/`: `prompts/role-profile-interview.md`,
`prompts/linkedin-export.md`, `prompts/background-research.md`,
`prompts/goals-template.md`, `prompts/coaching-style-interview.md`.

If the fetch fails, say so plainly and offer to retry. Don't silently halt and
don't invent the repo's questions from memory.

## Step 2 - Run the interviews thoroughly, filling gaps

For each gap, in the repo's running order, **follow that prompt exactly** - most are
one-question-at-a-time interviews; respect that (no dumping all questions, no
summarising between answers). This thoroughness is what makes the context solid.
Fill missing sections **within** a partial file too; say what you're skipping.

- **Offer the shortcut up front:** before the career and company sections, ask if
  they have a doc to attach (LinkedIn PDF, JD, deck) rather than interviewing cold.
- **Privacy (state up front):** flag and leave out by default anything personal or
  sensitive - health, relationships, money, emotion, sensitive professional
  transitions, and any third-party/safeguarding data. Ask before recording.

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
  - coaching style -> the instructions file you identified in Step 0
    (`claude.md` / `CLAUDE.md` for Claude, `AGENTS.md` for Codex and others), at root
- **Coaching style goes in the instructions file**, not a separate
  `context/coaching-style.md`. The starter ships `claude.md` as a placeholder system
  prompt, so for Claude you replace that placeholder; for Codex (or another
  AGENTS.md-based tool) you write `AGENTS.md` instead so the host actually loads it.
  Either way, one canonical copy - don't duplicate it across both files or into
  `context/`. (Mac note: `claude.md` and `CLAUDE.md` are the same file on macOS, so
  never create both.)
- **A pre-existing user-authored instructions file is theirs - never overwrite it.**
  If `CLAUDE.md` / `AGENTS.md` already holds real content (not the starter
  placeholder), don't clobber it: merge the coaching style into a clear "How to coach
  me" section with consent, and skip it entirely if it's a code-project file - at most
  append ONE pointer line ("read `context/` each session; it's the source of truth").
- **No-write surface:** output the final content labelled with where each piece
  goes, for them to paste. Don't claim to have saved.

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
