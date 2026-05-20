# Skills

This folder is where you can drop **agent skills** - reusable instruction sets that activate when relevant to the conversation.

Skills are supported in Claude Code, Cowork, and other folder-aware AI tools. Each skill is a `SKILL.md` file inside its own subfolder, with frontmatter that tells the agent when to use it.

We're shipping a few skills so you can see the format and use them from day one. We'll come back to skills properly in **Week 4 (Coding Agent)**, where you'll start building your own.

## What's here

- `humanizer/SKILL.md` - vendored from [blader/humanizer](https://github.com/blader/humanizer) (MIT, attribution in `humanizer/SOURCE.md`). Activates when you ask the agent to review or improve a piece of writing. Strips the full catalogue of AI tells (em dashes, rule of three, vague attributions, inflated symbolism, negative parallelisms, AI vocabulary) using Wikipedia's "Signs of AI writing" guide as the rulebook. Useful for emails, LinkedIn posts, internal comms, anything you'd be embarrassed to ship as obviously AI-generated.
- `prd/SKILL.md` - the skill you'll meet properly in **Week 4 (Coding Agent)**. Triggers on "PRD this", "let's draft a PRD", or `/prd <topic>`. Produces a milestone-checkbox planning doc with a decisions table at the top, then stops - so you can hand the PRD to a coding agent in a separate turn. Drafts only; does NOT implement.
- `owasp-security-check/SKILL.md` - vendored from [sergiodxa/agent-skills](https://github.com/sergiodxa/agent-skills) (MIT, attribution in `owasp-security-check/SOURCE.md`). Runs a structured pass over a codebase using OWASP Top-10 rules in `owasp-security-check/rules/`. Useful before sharing a build with anyone - catches hardcoded API keys, missing auth checks, insecure CORS, and other common production-killers.

## How skills work (briefly)

When you start a conversation with your agent, it reads the SKILL.md frontmatter from each skill in this folder. If the skill's description matches what you're trying to do, the agent loads the full skill content and follows its instructions.

Skills are different from the system prompt (`claude.md`) which loads on every conversation. Skills are conditional - they only fire when relevant.

## Container notes

- **Cowork:** Skills supported. Cowork scans `./skills/` in your project folder automatically. Drop the folder in and they're picked up.
- **Coding Agent (Claude Code, Cursor, etc.):** Skills supported. Claude Code reads `./skills/` (project-local) and `~/.claude/skills/` (global) automatically.
- **Claude.ai web Projects:** Skills are supported but *not* via this folder. To use a skill in a web Project you have to upload it separately through your Claude.ai settings (zip the skill folder, upload, then enable per-project). Just attaching the folder as a file does not work.
- **ChatGPT Projects / Gemini Gems:** No native skills concept. Closest equivalent is attaching individual files - which means losing the conditional "load only when relevant" behaviour.

So if you're on Claude.ai web Projects and you want these skills to behave the same as on Cowork or a Coding Agent, you'd need to take an extra step (zip + upload via Claude.ai settings). For most web Project users it's fine to skip skills today and revisit in Week 4.

We'll go deeper in Week 4. For now, this folder gives you three working skills out of the box.
