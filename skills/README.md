# Skills

This folder is where you can drop **agent skills** - reusable instruction sets that activate when relevant to the conversation.

Skills are supported in Claude Code, Cowork, and other folder-aware AI tools. Each skill is a `SKILL.md` file inside its own subfolder, with frontmatter that tells the agent when to use it.

We're shipping one starter skill so you can see the format. We'll come back to skills properly in **Week 4 (Coding Agent)**, where you'll start building your own.

## What's here

- `humanise-writing/SKILL.md` - a starter skill that activates when you ask the agent to review or improve a piece of writing. Strips AI tells (em dashes, rhetorical reversals, generic adjectives) and pushes for sharper, more human copy. Useful for emails, LinkedIn posts, internal comms, anything you'd be embarrassed to ship as obviously AI-generated.

## How skills work (briefly)

When you start a conversation with your agent, it reads the SKILL.md frontmatter from each skill in this folder. If the skill's description matches what you're trying to do, the agent loads the full skill content and follows its instructions.

Skills are different from the system prompt (`claude.md`) which loads on every conversation. Skills are conditional - they only fire when relevant.

## Container notes

- **Cowork:** Skills supported. Cowork scans `./skills/` in your project folder automatically. Drop the folder in and they're picked up.
- **Coding Agent (Claude Code, Cursor, etc.):** Skills supported. Claude Code reads `./skills/` (project-local) and `~/.claude/skills/` (global) automatically.
- **Claude.ai web Projects:** Skills are supported but *not* via this folder. To use a skill in a web Project you have to upload it separately through your Claude.ai settings (zip the skill folder, upload, then enable per-project). Just attaching the folder as a file does not work.
- **ChatGPT Projects / Gemini Gems:** No native skills concept. Closest equivalent is attaching individual files - which means losing the conditional "load only when relevant" behaviour.

So if you're on Claude.ai web Projects and you want this `humanise-writing` skill to behave the same as on Cowork or a Coding Agent, you'd need to take an extra step (zip + upload via Claude.ai settings). For most web Project users it's fine to skip skills today and revisit in Week 4.

We'll go deeper in Week 4. For now, this folder is a placeholder showing where skills live.
