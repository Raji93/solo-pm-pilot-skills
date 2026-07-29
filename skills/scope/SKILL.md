---
name: scope
description: Turn any messy problem — discovery notes, a bug pattern, a metric that moved, a stakeholder request, a product idea — into a clear, defensible plan. Produces the reframed problem and the job to be done, who it affects, evidence and benchmarks, a sized opportunity, the riskiest assumptions, a research plan to close the gaps, a one-sentence problem statement, precisely-defined success metrics with baselines and targets, a guardrail metric, stakeholders and who decides, what's in and out of scope, a visual timeline with decision gates, kill criteria, and a testable hypothesis. Use the compact version for small fixes and the full version for bigger bets. Triggers include "scope this", "turn these notes into a plan", "define the problem", "what research should I do", "who should I interview", "what metrics should I use", "how big is this", "why now", "who are the stakeholders", "when should we kill this", "should we build or buy", "where do I even start". This is step 1 of Scope -> Build -> Iterate.
---

# Scope — Any problem to a clear plan

Step 1 of the operating rhythm: **Scope → Build → Iterate → learn → repeat.**
Turn a fuzzy problem into something a PM can act on, defend in a review, and hand to the next stage.
Works for a two-week fix or a two-quarter bet; **scale the depth to the stakes.**

## Works for any problem
These sections are a checklist, not a form.
**Include what earns its place and skip the rest — "not relevant here, because…" is a good answer.**
A pricing bet needs market and competitive analysis; a broken onboarding step needs benchmarks and a funnel, not a competitor teardown.
Same skill, different depth.

## When to use / when not to
- **Use** at the fuzzy front end: a problem, idea, complaint, or metric change that isn't yet a plan.
- **Don't use** to build the thing (`build`) or to improve and ship it (`iterate`).

## Input
Anything: notes, a transcript, a metric drop, a support pattern, a one-line request.

**Ask before inventing.**
If a *decision-changing* fact is missing — the baseline metric, the affected segment, the deadline, or who decides — ask one or two pointed questions first.
If the user can't answer, proceed and mark it `[assumption]`.
Never fabricate a number to fill a gap.

**Timebox it.**
Say up front how long this scoping should take (a small fix: an hour or two; a real pilot: half a day).
Scoping is preparation, not the work.

## Before you generate: confirm the format
Before producing the scope, ask the user one quick question — which format they want:

- **Markdown / in-chat** — fastest to read and edit; good for a working draft or when they'll keep iterating.
- **HTML one-pager** — a clean, styled, shareable artifact; best for handoff, stakeholders, or a demo.

Ask it as a single question and wait for the answer. Don't generate both, and don't assume — the same content reads very differently in each, and the choice depends on what they're about to do with it.

Skip the question only if the user already stated a preference (e.g. "give me an HTML one-pager", "just markdown is fine") — honor it and generate directly. Ask **once**, when they first request the scope; don't re-ask on every follow-up edit.

Once they answer, generate the same content following the matching rules below.

## Output format — shared principles
Whichever format is chosen, the goal is identical: **let a reader grasp the bet and the recommendation in a single scan.**

- **Default to one page.** If it's longer, cut context, not decisions.
- **Compact version for small fixes**: 6–8 sections, short, one clear recommendation. **Full version for bigger bets**: expand evidence, research, and timing.
- **Open with a TL;DR line:** *problem → metric → target → the decision this enables.*
- **Follow with an at-a-glance summary** (Problem · North-star metric · Baseline → Target · Effort · Decision by) so a skimmer gets it in five seconds.
- **One idea per line. One takeaway per section.** Calm, executive tone.
- **Emphasize one thing.** The gate / recommendation is the only place that gets visual weight — don't let anything compete with it.
- **Tag every factual claim** `[data]` (our own numbers) · `[benchmark]` (external, cite the source) · `[interview]` (someone said it) · `[assumption]` (we're guessing). A reviewer should see instantly what's real.

### If Markdown: restraint rules
Clean means fewer competing signals, not less content.
- **No emoji** — not in headers, not anywhere. Plain section labels.
- **Ration bold.** Bold only the one load-bearing phrase per section — never whole sentences or mid-sentence runs. If more than ~3 words per section are bold, cut back.
- **At most two tables**, and only where the content is genuinely a grid (the at-a-glance summary, the research plan, or the timeline). Turn arithmetic and prose facts into sentences, not tables.
- **No horizontal rules between every block.** A blank line and a section label carry the break. Reserve `---` for the single break before the closing "push back" note, if used at all.

### If HTML: use the template
Generate a single self-contained HTML file from `scope-template.html` (in this skill folder). Fill the `{{PLACEHOLDERS}}` with the scoped content, delete any optional section that doesn't earn its place, and **do not change the CSS** — it already encodes the clean design (one accent color, rationed bold, no emoji, whitespace over rules, light hairline tables, the gate as the one emphasized callout and the kill criterion as the only other colored block). Save it as a `.html` artifact the user can open, share, or present.

## How to respond
Use the compact path unless the decision is high-stakes, high-cost, or likely to trigger cross-team debate.

### Frame
1. **Reframe** — one sentence: a user + a struggle + a desired outcome. If the input is a solution in disguise ("add a chatbot", "build X"), re-express the underlying problem and say so.
2. **Job to be done** — *"When [situation], I want to [motivation], so I can [outcome]."*
   Use this as a **test, not a formality**: if you can't write the job, you don't understand the problem yet — go back to the user, don't proceed. One line for a small fix; two or three jobs for a bigger bet.
3. **Who's affected** — the specific segment(s), and *how concentrated* the pain is (everyone a little, or one segment a lot — that changes the answer).

### Evidence — what we already know (pick what fits)
4. **What we know**, each claim tagged:
   - *Internal data* — what our own numbers already say (funnels, tickets, usage, revenue).
   - *Benchmarks* — what "good" looks like in our category, so we know if we're actually behind.
   - *Qualitative* — what users and stakeholders actually said.
   Use **real figures with named sources**; where you can't, name the specific thing to go find.
5. **Alternatives & competition (if relevant)** — how this gets solved today: competitors, an existing internal tool, a manual workaround, or **doing nothing**. For a buy decision: pricing models, each option's sweet spot and trade-off, where the gap is. End with the **wedge** — the narrowest place to win, or the cheapest way to learn before committing.

### Size the prize
6. **Opportunity size** — the back-of-envelope, with the arithmetic **shown**: *if we move [metric] from X to Y, that's ~N users / $M per period.* State the confidence and the load-bearing assumption.
   **Then judge it:** if the upside doesn't clearly beat the effort, **say so and recommend stopping or shrinking** — a scoping doc that never says "not worth it" isn't doing its job.

### Risks
7. **Riskiest assumptions** — tag each **Known / Assumed / Unknown**, and mark which ones **block a decision**. These are what the research plan has to close.

### Research — how we close the gaps
Research is a *phase with an end date*, not an open-ended activity. Plan it, timebox it, and say what would change your mind.

8. **Check the shelf first** — what's already been researched, measured, or written down internally (old decks, past studies, existing dashboards, support tags). Solo PMs waste weeks re-discovering things a colleague already knows. Name who to ask.
9. **Research questions** — derived from the risky assumptions above, one per assumption. Non-leading, and answerable.
10. **Method per question** — match the method to the question, and **order by cost — cheapest first**:
    | Question shape | Method | Typical cost |
    |---|---|---|
    | How many / how often? | query existing data | hours |
    | Where exactly do they fail? | session replays, funnel | hours |
    | Why / how do they think? | 5–8 user interviews | days |
    | Can they actually do it? | usability test (5 users finds most issues) | days |
    | How widespread is it? | survey | days–weeks |
    | What else exists? | competitive teardown | days |
    Run the cheap ones first — they often make the expensive ones unnecessary.
11. **Who to talk to** — segment, how many, how to recruit, and always a **disconfirming group** (people who succeeded, churned, or chose a competitor).
12. **Timebox & output** — the end date, and the artifact research produces (a findings note, a tagged dataset, a funnel).
13. **What would change our mind** — the specific finding that kills, shrinks, or redirects this plan. If nothing could, the research is theater.

### Define
14. **Problem statement** — one sentence: *[user] struggles to [do a job] because [barrier], costing [impact].* No solution language.
15. **Success metrics** — one **north-star outcome**, plus leading and lagging indicators. For each: a **precise counting rule** (numerator, denominator, time window), a **baseline**, a **target**, and its **instrumentation status** — measurable today, or needs instrumenting first (and how long that takes). Prefer outcomes over outputs. Say briefly how the leading indicators are expected to move the north star.
16. **Guardrail / counter-metric** — what must *not* get worse (quality, trust, cost, speed, another team's number).

### Stakeholders
17. **Who's who** — four lines:
    **Decides** (the one person who says go/no-go) · **Must agree** (anyone who can veto: design, legal, security, another team) · **Informed** · **Could block** (the realistic obstacle and how early to approach them).
    Name the **first conversation to have**, and a **60-second pitch** for it — a solo PM sells without authority, and the plan is the pitch.

### Scope
18. **In / out of scope** — a few things you will do; a few you deliberately won't yet.
19. **Effort & dependencies** — a rough size (S / M / L or person-weeks), and what it waits on.

### Timing
20. **Timeline — show it visually.**
Use a markdown table with one column per week and block characters (aligns reliably everywhere), and include a **Gate** row for decision points. Keep the timeline free of emoji, in line with the output rules:

```md
| Phase | W1 | W2 | W3 | W4 | Owner |
|---|---|---|---|---|---|
| Research | ███ | | | | PM |
| Build | | ███ | ███ | | Eng |
| Measure | | | | ███ | PM |
| **Gate** | *Security sign-off* | | | **Go/no-go** | |
```

In the HTML format, use the template's Timing table and the accent gate callout instead. If the surface renders Mermaid (GitHub, Notion), a `gantt` block is also fine.
Keep it to 3–6 rows — a scoping doc shows phases and gates, not a project plan.

21. **Why now** — why this ahead of the other candidates, and the **cost of delay**: what waiting a quarter costs. Be honest — if the window isn't actually closing, say so.
22. **Kill / pause criteria** — *"If [signal] isn't true by [date], we stop or pause."* Decide this **now**, while it's cheap to be objective. Ship, pause, and hand off are all legitimate endings.

### Hypothesis
23. **Hypothesis** — *"If we solve [problem] for [user], then [metric] moves by [amount], because [insight]."*
24. **The decision this enables** — what call this plan lets someone make, **who makes it**, and by when.
25. **What we'll learn either way** — the finding this cycle produces even if the answer is no. That's what feeds the next loop.

## Solo-PM reality check
No researcher, no analyst, no spare team. Before you commit, answer these six:
- **Timebox** — how long will this scoping take, and is that proportionate?
- **Solo-doable vs. needs someone** — split the plan explicitly. What can you do alone this week, and what needs another human (a data pull, a design, an approval)? Start the dependency early.
- **Data access** — can you actually get the numbers this plan depends on? If not, name the proxy or the person who can pull it.
- **Your red-teamer** — name the one skeptic who'll poke holes before you commit. With no team to catch your errors, this is the highest-value line in the doc.
- **First step Monday** — the single concrete action that starts this. Beats analysis paralysis.
- **What this leaves behind** — the template, dataset, query, or doc you'll reuse next time. Each cycle should compound.

## Guardrails
- Scope the **problem**, not the solution.
- **Do not turn this into a feature spec or implementation brief.** The output is a decision-making brief.
- **Ground every claim in real data or a named source, or tag it `[assumption]`.** Confident-but-fake numbers are the fastest way to lose trust.
- **Research must be timeboxed and falsifiable.** Cheapest method first; if no finding could change the plan, don't run it.
- Define metrics precisely — a metric without a counting rule is a vanity metric waiting to happen. A metric you can't measure yet isn't a baseline; it's a task.
- One problem, not a bundle. Every metric needs a baseline + target, or "TBD — instrument first."
- Always include a way to be wrong (a disconfirming check) and a counter-metric.
- **Be willing to recommend not doing it.** Sizing that only ever justifies the work is theater.
- **Right-size it.** Don't dress a small fix in a market analysis; don't hand-wave a big bet.

## Ready for Build?
Exit criteria — confirm each, and fix or flag any "no":
- [ ] Could a skeptical exec read the TL;DR and know what we're doing and why?
- [ ] Is every number either sourced or tagged `[assumption]`?
- [ ] Is the research timeboxed, with a stated finding that would change our mind?
- [ ] Is the north-star metric measurable today — or is instrumenting it in the plan?
- [ ] Does the opportunity size clearly beat the effort?
- [ ] Is there a kill/pause trigger, and is it clear who decides and by when?

## Handoff
Pass the plan to **`build`** to make the smallest thing that tests the hypothesis.
When the cycle completes, `iterate` feeds its learnings back here — **capture what you learned and re-scope**, rather than starting the next problem cold.
