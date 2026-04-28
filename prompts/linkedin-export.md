# LinkedIn Export

Your LinkedIn profile is the cleanest summary of your career and skills that already exists. Five minutes of work to add it as context.

The Background Research is about your *company*. The LinkedIn export is about *you* - your career arc, education, skills, recommendations.

---

## Steps

1. Open your LinkedIn profile in a browser.

2. Click the "More" button on your profile, then "Save to PDF" OR go to the print menu in your browser and find the "Save to PDF" button

3. Convert the PDF to markdown. Two options:

   **Option A (faster, free, no tokens):** drop the PDF into [pdf2md.morethan.io](https://pdf2md.morethan.io/). Copy the markdown output.

   **Option B (uses Claude/ChatGPT tokens):** open a new chat in your container, upload the PDF, paste:
   ```
   Convert this LinkedIn PDF into a clean markdown profile.
   Keep all the facts (roles, dates, education, skills, recommendations)
   but format as readable markdown with clear headings.
   Don't summarise or interpret - just convert format.
   ```

4. Save the markdown:
   - **Claude/ChatGPT Projects, Gemini Gem:** paste into a new file in your project, name it `linkedin.md`
   - **Cowork or Coding Agent:** save as `context/linkedin.md` in your folder

That's it. Your agent now has your career context alongside the company context and your role profile.

---

## Why this is worth doing

Without this, your coach has:
- Your role profile (what you do *now*)
- Your company background (what your company does)
- Your goals (where you're heading)

The LinkedIn export adds:
- Where you've been (full work history)
- What you're trained in (education)
- What other people say about you (recommendations - underrated)
- Skills you've collected over time

This is the difference between an agent that knows your current job and an agent that knows your career.

---

## A note on accuracy

The PDF export is a snapshot. If you change roles or update your LinkedIn, the markdown won't update unless you re-export. For most people, once a year is fine.

If you'd rather link the *live* version: not currently possible for LinkedIn (no official API for personal profiles, no Claude/ChatGPT connector for it). PDF export is the workaround.
