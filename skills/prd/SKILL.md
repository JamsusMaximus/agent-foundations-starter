---
name: prd
description: |
  Draft a Product Requirements Document (PRD) using a milestone-checkbox
  format: problem, non-goals, decisions captured, milestones with
  checkboxes, verification, out-of-scope, open questions. Use when the user
  says "PRD this", "let's draft a PRD", "/prd <topic>", "write a PRD for X",
  "scope X as a PRD", or any framing where the deliverable is a planning
  doc that will guide implementation. Does NOT implement; PRD-only. The
  output is always a milestone-chunked, checkbox-driven doc that an
  engineer can tick off as they build.
allowed-tools:
  - Read
  - Write
  - Edit
  - Bash
  - Glob
  - Grep
  - AskUserQuestion
---

# prd

Produce a PRD in a milestone-checkbox format. The PRD's purpose is to capture decisions and break the work into checkable milestones BEFORE any code is written.

## When this triggers

- "PRD this", "let's draft a PRD", "let's scope this as a PRD"
- "/prd <topic>"
- "write a PRD for X"
- Any time the user signals they want a planning doc rather than implementation

If unsure whether the user wants a PRD or wants you to start coding, ask once.

## What the PRD is NOT

- An implementation. Do not write code while drafting.
- A design doc with paragraphs of architecture prose. Decisions go in the table; mechanics go in the milestone checkboxes.
- A free-text wishlist. Every item under a milestone must be a discrete, checkable thing.
- A novel. Aim for ~250-400 lines for a typical scope; ~800+ only if the work spans many deployable PRs.

## House format (use this template)

```markdown
# <Title> PRD

**Status:** Draft, <YYYY-MM-DD>
**Owner:** <name>
**Surface:** <primary file(s) / endpoints / pages affected>

## Problem

<1-3 short paragraphs. State current state, why it's a problem, and the desired outcome. Not a sales pitch - a brief.>

We want to:
1. <outcome 1>
2. <outcome 2>
...

## Context & references

<Anything the implementer will want at their fingertips during the build. Links, file paths, transcripts, prior art, example outputs, screenshots, design docs. One bullet per item with a short note on why it's useful. Delete this section if nothing relevant exists - don't leave it as a stub.>

- [<title>](<url-or-path>) - <why it matters / what the implementer should look at>
- `path/to/relevant/file.ts` - <what's in here that the build will need>
- ...

## Non-goals

- <thing we explicitly are not doing, with the reason or where it is tracked separately>
- ...

## Decisions captured (from scoping conversation)

| Question | Decision |
|---|---|
| <decision-shaped question> | <chosen option, with constraint if any> |
| ... | ... |

## Implementation milestones

Milestones are ordered by dependency. State which milestones unblock which.

### M1 - <name>

<one-line purpose. Note dependencies if any.>

- [ ] <discrete checkable item>
- [ ] <discrete checkable item>
- [ ] ...

### M2 - <name>

<one-line purpose>

- [ ] ...

<...>

### M<N> - Verification

Run before merging:

- [ ] <acceptance check 1>
- [ ] <acceptance check 2>
- [ ] Whatever this project's standard pre-merge check is (build / type-check / tests). If the project has no test suite, manual smoke checks are fine.
- [ ] Manual smoke checks specific to the feature

## Out of scope, but worth flagging during implementation

1. <adjacent thing that may surface; how to handle if it does>
2. ...

## Open questions to resolve during implementation

- <question only the implementer can answer in-flight>
- ...
```

## Process

1. **Confirm the scope.** Before asking anything else, confirm in one sentence what you understood the user wants to PRD. If they used a vague handle ("the upsell thing", "the auth refactor"), restate it concretely.
2. **Read existing context.** Skim files the PRD will touch (the page, the API endpoint, the data file). One or two `Read` / `grep` calls. Enough to ground the questions, not a full audit.
3. **Skim ONE existing PRD as a tone reference** if the project has prior PRDs - look for `*-prd.md` files in `docs/` and read the most recent or most similar in scope. If the project has no prior PRDs, the template above is the reference.
4. **Ask clarifying questions in batches** with `AskUserQuestion`. Group decisions that shape the structure of the doc (scope boundaries, framing, what's in vs deferred). Max 4 questions per round; keep options mutually exclusive (or use `multiSelect` when truly orthogonal). Two rounds is the norm; three is fine if the topic is genuinely big. One round is acceptable if the scope is tight.
5. **Ask explicitly for context the implementer will want at hand.** A separate beat from the decision questions - the answer is *material*, not a choice. Prompt: *"Are there any links, files, transcripts, design refs, prior PRs, or example outputs you want me to pin into a 'Context & references' section for the implementer to open during the build? Drop them in now."* Capture each as a bullet under "Context & references" with a one-line note on why it's relevant. If the user has nothing, delete the section in the final draft.
6. **Convert each answered question into a row in the Decisions captured table.** This is the contract: every decision the user made is visible at the top of the doc.
7. **Draft the milestones.** Order them by dependency. State the dependency graph in one line at the top of the milestones section. Within a milestone, every line must be a checkable thing - no narrative prose between checkboxes (a single one-line purpose under the heading is fine).
8. **Write the PRD** to a sensible project path. See "Where to save" below.
9. **Update the project's docs index** if one exists. Look for `docs/index.md` (or a similar catalogue file) and add a wiki-link entry under the appropriate section.
10. **End-of-turn summary:** one or two sentences naming the file path and the milestone count. No more.

## Where to save

- Inside a git repo: `<repo>/docs/<area>/<topic>-prd.md`. Pick the area from the closest existing PRD's neighbours, or sensible top-level categories like `growth/`, `product/`, `internal/`, `infra/`. If unsure, ask the user once.
- Outside a repo: `~/Documents/prds/<topic>-prd.md` (create the directory if needed). Don't park PRDs in `/tmp` - they're durable artefacts.

Filename convention: `kebab-case-prd.md`. Lowercase. The `-prd.md` suffix is load-bearing for greps.

## Things to get right

- **Every milestone item is a discrete check.** "Update the hero" is not a check; "Hero pill copy: 'Next live cohort: late June 2026'" is.
- **State copy verbatim in the PRD** when copy is part of the deliverable. Don't write "update the hero copy"; write the exact line. The PRD is the source of truth so the implementer doesn't re-decide the wording mid-PR.
- **Include line numbers** when referring to specific spots in existing files (e.g. `path/to/file.ts:142`). A PRD that says "the CTA block" without coordinates costs an extra grep at implementation time.
- **The decisions table is non-negotiable.** Every clarification you asked must appear there. If a decision was implied (not asked), still capture it in the table so the implementer can challenge it later.
- **Milestones over PRs.** Default to milestones (M1, M2, ...). Only switch to PR-numbered sections (PR 1, PR 2a, ...) when the work clearly spans multiple deployable shipments and the user has confirmed that intent.
- **The verification milestone is mandatory.** Even small PRDs end with an M<N> that is the merge gate. Pulls together whatever this project's standard pre-merge check is plus feature-specific manual smoke.
- **Out-of-scope must say where the deferred thing is tracked** ("self-paced upsell - separate PRD, TBC") so the doc doesn't quietly drop work.
- **Context & references is for the implementer, not the reviewer.** Every bullet should be something the agent or developer will actually open during the build (design ref, prior PRD, transcript, example output, screenshot, data file). If a link is only there to justify the scope, it belongs in the Problem section, not here. If the user provides no context, delete the section rather than leaving an empty placeholder.

## Things to avoid

- Do NOT write the implementation while drafting. Resist any urge to also `Edit` the page during the PRD step. The user will say "ok let's build" as a separate signal.
- Do NOT pad the doc with rationale for every decision; the table captures it. Rationale belongs in PR descriptions and decision logs.
- Do NOT merge milestones to look smaller. M1 + M2 collapsed into "M1: do everything" defeats the point - the dependency graph and per-PR sizing are the value.
- Do NOT add testing checkboxes inside every feature milestone *and* a verification milestone - duplicates the work. Feature milestones reference unit tests they need; the verification milestone runs the full project suite once.

## Reference

The template in "House format" above is the structural reference. If this project has prior PRDs in `docs/`, skim one as a tone reference (step 3 of Process).
