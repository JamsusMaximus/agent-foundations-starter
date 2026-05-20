# Install the PRD skill - Cowork

> Two install paths in Cowork. Option A is cleanest if you're on Team Premium. Option B works on any plan.

## Option A: Anthropic Org Skills (Team Premium)

If your org is on Team Premium, install once and every Cowork project in your org picks it up.

1. Go to your org's **Skills** library (Anthropic dashboard).
2. Click **Add skill**.
3. Paste the contents of [`SKILL.md`](./SKILL.md) (sitting next to this file) into the editor. The frontmatter at the top (`name: prd`, `description: ...`) is what the picker uses to surface it.
4. Save. The skill is now available in every project in your org.

**To invoke:** in any Cowork chat, type `/prd <topic>` or say "Help me PRD this thing."

## Option B: Paste into a single project (any plan)

If you're not on Team Premium, install per-project. This works fine - you just have to redo it for each project where you want the skill.

1. Open the Cowork project where you'll do the work.
2. Open the **Files** tab.
3. Create a new file called `prd.md` at the project root.
4. Paste the contents of [`SKILL.md`](./SKILL.md) into it. Keep the frontmatter at the top.
5. In the chat, tell the agent once at the start of any PRD session:
   ```
   Use the PRD workflow in prd.md to scope this.
   ```
   Or just `/prd <topic>` - Cowork will read `prd.md` and follow it.

## How to invoke (either option)

- `/prd <topic>` - e.g. `/prd weekly-summary-agent`
- "Help me PRD this thing"
- "Let's scope this as a PRD"

The skill will:

1. Confirm the scope in one sentence.
2. Skim files it'll touch.
3. Look for a prior PRD in `docs/` as a tone reference, if one exists.
4. Ask clarifying questions in batches (max 4 per round, two rounds is normal).
5. Draft a milestone-checkbox PRD with a decisions table at the top.
6. Save it to a sensible location in the project.

## Gotcha

If you install via Option B (per-project `prd.md`), only the project that has the file can use the skill. If you want it everywhere, either copy the file into each project or upgrade to Option A.

The `allowed-tools` line in the frontmatter is harmless in Cowork - Cowork ignores it and uses its own tool model. Don't strip it; you'll want it back if you ever port this skill to Claude Code (see [`install-claude-code.md`](./install-claude-code.md)).
