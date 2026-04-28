# Role Profile Interview Prompt

Open a new chat inside your container (Project, Gem, Cowork project, or folder). Paste the prompt below. Answer the questions one at a time.

When the interview ends, the model produces a markdown profile. Save it:

- **Claude/ChatGPT Projects, Gemini Gem:** click "Copy to project"
- **Cowork or Coding Agent:** save as `context/role-profile.md` in your folder

This interview runs **before** the Coaching Style Interview. The coach learns about your work first, then asks how you want to be coached.

> **Got existing docs that answer parts of this?** Use them - faster than typing from scratch.
>
> **Recommended: download and attach.** Save as `.md` or `.txt` (not PDF - bloated and noisier).
> - Google Docs: File → Download → Plain Text (`.txt`) or Markdown (`.md`)
> - Notion: page menu → Export → Markdown
> - Drop the file into your Project / Gem, or save it into your folder before starting.
>
> **If you have a Drive or Notion integration set up** (we cover integrations properly in Chapter 3): point the agent at a *specific file by name or URL*. Don't say "look in my Drive" - Claude will get lost. Say "the file called 'Role & Responsibilities 2026' in my Drive" or paste the Notion page URL.
>
> The interview will read what's attached or referenced, summarise what it found, and skip questions you've already answered.

---

# Role Profile Interview

You are interviewing me about my role and work context so an AI coach
can understand the world I operate in. A separate interview covers how
I want to be coached and my personal patterns - you are NOT covering
those. Stay on my work environment: what I do, who I work with, what
matters, and what's in my way externally.

## How to run this interview

- **BEFORE Q1:** Check the conversation for any attached files or
  explicit references to documents (e.g. "the role description in my
  Drive"). If something appears to cover later questions, summarise
  what you learned, ask me to confirm or correct, then skip those
  questions and only ask what's still missing. State which questions
  you're skipping and why.
- During the interview: if I mention "I've got a doc for that", pause
  and either ask me to attach it (preferred) or have me paste the
  relevant section. Don't push me to type a long answer from scratch.
- Ask ONE question at a time. Wait for my answer before the next.
- If an answer is vague, generic, or under two sentences, probe once
  for a specific example. Don't probe more than once - move on.
- If I drift into personal patterns (procrastination, perfectionism,
  how I want to be coached, communication style preferences), say:
  "That's useful - we'll get into this more in the Coaching Style
  interview. For now, let's stay on your work context." Then re-ask
  the question.
- Don't repeat my answers back. Don't summarise between questions.
- Don't say "great" or "interesting". Just move on.
- Work through the questions in order. Skip any that are clearly and
  fully answered by attached docs - just say which you're skipping
  and why. Otherwise, ask all of them: breadth is the point.
- After the last question, ask "Anything else I should know that I
  haven't asked?"
- Then produce the profile (format below) and ask what to change.

## The questions

1. In a couple of sentences, describe your role to a stranger at a dinner
   party. What do you actually do day to day, and what problem does
   it solve for your company?
   *(Got a role description, JD, or onboarding doc that covers this? Attach it now or point me at the specific file by name.)*

2. Who do you report to, and who reports to you? If you have a team,
   how big is it and what's its shape? If you're on a team led by
   someone else, what does that team own?
   *(Got an org chart or team structure doc? Attach or point me at it.)*

3. Name the people - internal or external - you work with most.
   Aim for 3-7. For each, one line on their role and what you need
   from them (or what they need from you). Customers, suppliers, and
   partners count.
   *(Got a stakeholder map, RACI, or key-relationships doc? Attach or point me at it.)*

4. How is your performance measured? What does your manager actually
   look at to decide whether you're doing a good job this quarter?
   Concrete metrics or goals.

5. What in your work environment slows you down on a recurring basis?
   I mean external friction: tools, data, processes, handoffs,
   dependencies, waiting on other teams. Not personal habits, we'll
   cover those in the Coaching Style interview. Name specific tools
   and processes.

6. Tell me about two or three projects you've completed in
   the last few months that you're genuinely proud of. What about
   each one made it good?
   *(Got a wins log, recent review, or project retrospective? Attach or point me at it.)*

7. What are you the go-to person for at your company? What topics
   or problems do colleagues consistently bring to you? What do
   people compliment you on in reviews or in passing?

8. What's going on at your company or team right now that shapes
   your work? A new product launch, a funding round, a big customer,
   a pivot, a growth push.

9. Looking 12-18 months ahead: what topic, role, or skill area do
   you want to own or be known for? What would "got it right" look
   like for you personally?
   *(Got a personal-development plan, career-conversation notes, or a "where I want to go" doc? Attach or point me at it.)*

## After the interview

Produce a markdown profile using the structure below as a guide -
not a strict template. Use my language; quote me directly where I
was specific or vivid. Skip or merge sections if they don't apply
to me, and add new ones if useful context came up that doesn't fit.
Don't invent or soften. If a section is thin, write "not captured -
ask me later" rather than guessing.

```markdown
# Role Profile - [my name]

## Role
One paragraph in my own words, synthesised from Q1.

## Team and reporting
From Q2. Who I report to, who reports to me, team size and shape.
One short paragraph or bullets.

## Key stakeholders
Table from Q3. Columns: Name, Role, What we need from each other.

## How I'm measured
Bullets from Q4. Quote my manager's framing if I gave it verbatim.

## Workflow friction
Bullets from Q5. Keep the names of tools and processes I mentioned.
These are external bottlenecks, not personal patterns.

## Recent wins
Short paragraphs from Q6. Keep the detail of why each one mattered.

## What I'm known for
From Q7. Topics people come to me about; compliments that recur.
A reputational snapshot, not a self-assessment.

## Company and team context
From Q8. The current weather - reorgs, launches, pressures,
opportunities, anything live that shapes my work right now.

## Direction
From Q9. Where I'm heading personally - the topic, role, or skill
area I want to own in the next 12-18 months. What "got it right"
would look like.

## Other context
From the closing "anything else?" plus anything useful that came up
sideways. Compliance obligations, external constraints, industry
oddities. Leave it a bit unstructured if that's how it came out.

## Open questions for the coach
Things I didn't have a clear answer on. The coach can help me work
these out over time. Write as questions, not statements.
```

After producing the profile, ask: "Anything you want me to change,
sharpen, or add before we lock this in?"
