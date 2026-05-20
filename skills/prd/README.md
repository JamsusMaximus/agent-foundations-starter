# The PRD skill

A reusable skill that turns "PRD this" into a properly-scoped, milestone-checkbox planning doc with a decisions table at the top. Drafts the PRD, captures every clarifying question as a decision row, then stops - so you can hand it to a coding agent in a separate turn.

## Files

- [`SKILL.md`](./SKILL.md) - the canonical skill. Same body works in Claude Code and Cowork.
- [`install-claude-code.md`](./install-claude-code.md) - install path for Claude Code (`~/.claude/skills/prd/SKILL.md`).
- [`install-cowork.md`](./install-cowork.md) - install path for Cowork (Org Skills or paste-into-project).

## What it produces

A markdown file with this structure:

```
# <Title> PRD

**Status / Owner / Surface**

## Problem
## Non-goals
## Decisions captured (table)
## Implementation milestones
  ### M1 - ...  (checkboxes)
  ### M2 - ...  (checkboxes)
  ### M<N> - Verification  (checkboxes)
## Out of scope, but worth flagging
## Open questions to resolve during implementation
```

Saved to `<repo>/docs/<area>/<topic>-prd.md` inside a repo, `~/Documents/prds/<topic>-prd.md` outside.

## What it deliberately does NOT do

- Write code. PRD-only. "Let's build" is a separate turn.
- Pad the doc with rationale. Decisions go in the table; checkboxes carry the rest.
- Merge milestones to look smaller. The dependency graph and per-PR sizing are the value.

## Picking your install path

| Your surface | Install file | Notes |
|---|---|---|
| Claude Code | [`install-claude-code.md`](./install-claude-code.md) | Cleanest. `/prd <topic>` in any project. |
| Cowork (Team Premium) | [`install-cowork.md`](./install-cowork.md) Option A | Install once via Org Skills; available everywhere. |
| Cowork (any plan) | [`install-cowork.md`](./install-cowork.md) Option B | Paste `prd.md` into each project that needs it. |

## Customising

The skill is just a markdown file with frontmatter. Edit `SKILL.md` to:

- Change the template (e.g. add a "Risks" section, or a "Stakeholders" line in the header)
- Tighten or loosen the triggers (the `description:` block in frontmatter)
- Adjust the process (e.g. require an architecture diagram for any PRD over 400 lines)

Re-install after editing. Both surfaces read the file fresh on the next invocation.
