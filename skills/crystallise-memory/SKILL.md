---
name: crystallise-memory
description: |
  Move everything the assistant knows about the user out of hidden, unreliable
  memory and into clean files they own and can carry into any tool. Reviews what
  it knows ONE category at a time (keep / cut / fix), guards personal or sensitive
  items out by default, flags every guess as NEEDS VERIFYING, and writes nothing
  until the user approves. Use when the user says "crystallise your memory into files",
  "crystallise everything you know about me", "extract what you know about me into files",
  "move your memory into context files", "/crystallise-memory", or is seeding a second
  brain / context/ folder for an agent.
allowed-tools:
  - Read
  - Write
  - Edit
  - AskUserQuestion
---

# crystallise-memory

Move the assistant's hidden, partial, often-stale memory of the user into clean
files the user owns. The output is a `context/` folder they can drop into any
folder-aware agent (Cowork, a coding agent, another project), plus a short
pointer added to that agent's main instructions file so it reads them every
session. This folder is also the seed of a second brain.

## Best run in Claude chat

Run this where the assistant holds the **richest** memory of the user - usually
Claude **chat** (or a Claude.ai Project with memory on), not a fresh agent that
only sees the current folder. Produce the files here, then the user drops the
`context/` folder into their agent project afterwards. If you are running inside
an agent that has no stored memory of the user, say so and work from whatever the
user tells you instead of inventing a memory you do not have.

## The one rule that makes this trustworthy

**Never invent a fact to fill a gap.** Every item must be something you actually
hold, tagged by how sure you are. A blank is correct; a plausible-looking guess
written as fact is not. Anything you are unsure of goes in a NEEDS VERIFYING list,
never into a context file as if it were confirmed.

## Process

Work through this WITH the user. Do not crystallise everything in one wall of text, and
do not write or save anything until they approve.

### Step 1 - Scan (quietly)

Gather everything you currently know or believe about the user and their work:
identity, role/company, goals, projects, people, preferences - anything. Tag each
item's confidence: `(certain)` / `(fairly sure)` / `(guessing)`. Do not show this
raw dump yet.

### Step 2 - Review it with them, ONE CATEGORY AT A TIME

Go category by category (e.g. Identity, Work, Goals, Projects, People,
Preferences). For each category, show just that category's items as a short list,
each with its confidence tag, then PAUSE and ask the user to go through them: for
each, they say **keep / cut / fix**, and add anything you missed. Wait for their
reply before moving to the next category. Keep it tight.

**Privacy rule (non-negotiable):** if an item is personal or sensitive - health,
relationships, money, emotional or private matters - flag it, do NOT put it in any
file by default, and ask whether to leave it out, keep it in a private file the
user controls, or drop it. **Default to leaving it out.**

### Step 3 - Propose, don't write

Once you have been through every category, show:

1. A simple file structure for the confirmed facts - a `context/` folder, one file
   per thing:
   ```
   context/
     about-me.md      identity, basics
     role.md          role, company, what they do
     goals.md         their goal + the one metric that matters
     people.md        who they work with
     preferences.md   how they like things done / their voice
   ```
   Show what goes in each.
2. **One** pointer line to add to their main instructions file (`CLAUDE.md`,
   uppercase, or the Cowork project instructions) so it reads `context/` every
   session and treats those files as the source of truth, for example:
   > Read the files in `context/` at the start of each session; they're the source
   > of truth about me. If anything you recall conflicts with them, the files win.
3. A **NEEDS VERIFYING** list holding every remaining `(guessing)` item. Do not
   promote any of these into a context file.

### Step 4 - Save only on approval

When the user signs off:

- **Write the confirmed `context/` files** (Write/Edit), ready to use in their agent
  folder.
- **Add the pointer line to `CLAUDE.md`.** Append it; never overwrite or restructure
  what's already there (`CLAUDE.md` is theirs). Ask first. Skip it, and say why, if
  `CLAUDE.md` is actually a software project's instructions file - offer a dedicated
  personal folder instead. Keep the casing: `CLAUDE.md` is uppercase, and never write
  a lowercase `claude.md` (on a Mac they are the same file and would collide).
- **No-write surface:** if you can't write files here (some Cowork surfaces), output
  the final file contents and the pointer line, each labelled with exactly where it
  goes, for the user to paste. Don't claim to have saved.

Then stop. From now on those files are the source of truth: if anything you recall
later conflicts with them, the files win - say so, so the user can update the file.

## Sidenote: moving over from another tool

If the user is migrating from ChatGPT (or another assistant with memory), tell them
to run this same process there first to pull out what its memory holds, then bring
those files across. The whole point is that the context is now portable.

## Things to avoid

- Do NOT show one giant wall of facts - it is unreviewable and the user will rubber-stamp it.
- Do NOT write any file before Step 4 approval.
- Do NOT carry sensitive items into shared files by default.
- Do NOT fill gaps with invented detail to make a file look complete.
