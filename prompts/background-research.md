# Background Research Prompt

Open a new chat (Research mode if you're on a paid plan, regular Perplexity if you're free). Fill in the [VARIABLES] below, paste the prompt, and let it run for 5-10 minutes.

When it's done:
- **Claude/ChatGPT Projects, Gemini Gem:** click "Copy to project" / "Add to project"
- **Cowork or Coding Agent:** save the output as `context/background-research.md` in your folder
- Skim the output and delete or correct anything obviously wrong before saving

This prompt focuses on **your company**, not you personally. Your own background is captured separately via the LinkedIn export and the Role Profile Interview.

> **Got internal company docs?** A pitch deck, strategic plan, QBR, investor update, or company wiki page is a much richer starting point than the public web alone.
>
> **Recommended: download and attach.** Save as `.md` or `.txt` (not PDF). Drop the file into your Project / Gem, or save it into your folder before starting research.
>
> **If you have a Drive or Notion integration set up:** point the research agent at the *specific file by name or URL*. Don't say "look in my Drive" - it'll get lost. Say "the deck called 'Q2 Strategy' in my Drive" or paste the Notion page URL.
>
> Research will use any attached docs as primary input, fill gaps with web research, and flag anything in the public sources that contradicts the internal docs.

---

## Prompt

```
Research [COMPANY] to create a company context profile that an AI
coach can use. The person using this coach is an employee at this
company - their personal background is covered separately via their
LinkedIn export and a role-profile interview. Your sole job is the
company and market context.

If any internal company docs (pitch deck, strategic plan, QBR,
investor update, company wiki) are attached to this conversation or
referenced by name, treat those as primary input first. Fill any gaps
with web research, and flag anything in public sources that
contradicts the internal docs (newer pivot, undisclosed pricing
changes, etc.).

Company:
- Name: [COMPANY]
- Website: [COMPANY DOMAIN]
- Headquarters / main market: [COUNTRY or CITY]

---

SOURCES TO SEARCH:

1. Company website - product, pricing, positioning, customer logos,
   team page, blog, press page
2. Company blog and newsroom - topics they publish on reveal strategy,
   target customer, and current priorities
3. Press coverage - TechCrunch, Sifted, industry publications, trade
   press, local news - launches, partnerships, milestones, pivots
4. Crunchbase, PitchBook - funding rounds, investors, valuation,
   employee count
5. Product reviews - G2, Trustpilot, App Store, Capterra - how
   customers actually describe the product and what they gripe about
6. Competitors - who else operates in this space, how this company
   differentiates, where they sit in the market
7. Job postings (company careers page, LinkedIn Jobs) - what roles
   they're hiring reveals current priorities, stage, and gaps
8. Company and founder social media - LinkedIn, X, YouTube - recent
   posts about strategy, hiring, product direction
9. Podcast appearances by the founder or senior team - strategic
   context is often shared more candidly here than on the website

---

CRITICAL ACCURACY RULES:

- Only include information explicitly stated in sources. Do not infer
  or assume.
- For funding, headcount, customer names, and partnerships: only
  include what's verifiable from a primary source.
- Distinguish clearly between "confirmed" facts and "possible/likely"
  inferences. When uncertain, say so.
- Flag anything that looks out of date (e.g. "most recent press
  coverage is from 2023 - situation may have changed").
- Do not pad. A short, accurate profile beats a long speculative one.

---

STRUCTURE THE PROFILE AS FOLLOWS:

1. WHAT THE COMPANY DOES
Product, customer, business model, stage. What do they sell, to whom,
and how do they make money? Include the elevator pitch and one layer
deeper than the elevator pitch.

2. SIZE AND STAGE
Team size (approximate if exact unavailable), funding stage, revenue
signals if public, notable customers or partnerships, geographic
footprint.

3. RECENT ACTIVITY (last 18 months)
Product launches, partnerships, funding rounds, leadership changes,
pivots, press moments. Date-stamp each item. This is the section the
coach will lean on to understand what's live right now.

4. POSITIONING AND COMPETITION
Who the main competitors are and how the company differentiates in
its own words (from website, blog, PR). What customers praise and
complain about in reviews.

5. CURRENT PRIORITIES AND SIGNALS
What the company is pushing on right now, based on: hiring patterns
(roles open suggest where they're investing), blog content (topics
they're publishing on), leadership posts (strategic themes), press
coverage. Frame as observed signals, not conclusions. Example: "They
have 4 open roles in customer success and are publishing heavily on
retention - suggests current focus on reducing churn."

6. STRATEGIC CHALLENGES AND OPPORTUNITIES
Based on stage, market, and public signals: what are the likely
challenges and underexplored opportunities? Frame as observations for
a coach to explore, not diagnoses. Keep to 3-5 items.
```
