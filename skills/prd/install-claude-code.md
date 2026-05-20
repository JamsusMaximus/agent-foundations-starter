# Install the PRD skill - Claude Code

> The cleanest native experience. Once installed, type `/prd <topic>` in any project and the skill takes over.

## One-time install

1. Open a terminal.
2. Make sure the skills directory exists:
   ```bash
   mkdir -p ~/.claude/skills/prd
   ```
3. Save the contents of [`SKILL.md`](./SKILL.md) (sitting next to this file) to:
   ```
   ~/.claude/skills/prd/SKILL.md
   ```
   Either copy-paste the file, or download it directly:
   ```bash
   curl -o ~/.claude/skills/prd/SKILL.md <raw-URL-of-SKILL.md>
   ```
4. That's it. Claude Code picks up new skills automatically.

## How to invoke

In any project (any folder where you have a `claude` session open), say:

- `/prd <topic>` - e.g. `/prd weekly-summary-agent`
- "Help me PRD this thing"
- "Let's scope this as a PRD"
- "Write a PRD for the contractor onboarding flow"

The skill will:

1. Confirm the scope in one sentence.
2. Skim files it'll touch (one or two reads).
3. Look for a prior PRD in `docs/` as a tone reference, if one exists.
4. Ask clarifying questions in batches (max 4 per round, two rounds is normal).
5. Draft a milestone-checkbox PRD with a decisions table at the top.
6. Save it to `docs/<area>/<topic>-prd.md` (inside a repo) or `~/Documents/prds/` (outside).
7. Add a wiki-link to your `docs/index.md` if you have one.

## What it deliberately does NOT do

- Write code. The PRD is the hand-off; "OK let's build" is a separate turn.
- Pad the doc with prose rationale. Decisions go in the table; everything else goes in checkboxes.

## Updating

The skill is just a markdown file. Edit `~/.claude/skills/prd/SKILL.md` directly to tweak triggers, the template, or the process. Changes take effect on the next `/prd` invocation.

## Gotcha

If you also work in Cowork, install the same skill there separately (see [`install-cowork.md`](./install-cowork.md)) - Claude Code and Cowork don't share skills folders.
