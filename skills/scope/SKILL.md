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

## Output format
Make it scannable and short enough to actually get read.

- **Default to one page.** If it's longer, cut context, not decisions.
- **Use the compact version for small fixes**: short bullets, 6–8 sections, one clear recommendation.
- **Use the full version for bigger bets**: expand the evidence, research, and timing sections.
- **Open with a TL;DR line:** *problem → metric → target → the decision this enables.*
- **Then a summary table** (Problem · North-star metric · Baseline → Target · Effort · Decision by), so a skimmer gets it in five seconds.
- Give each section its icon, mapped 1:1 to the structure below: 🎯 Frame · 🔎 Evidence · 📐 Size · ⚠️ Risks · 🔬 Research · 📏 Define · 👥 Stakeholders · ✅ Scope · ⏱️ Timing · 🧪 Hypothesis.
- Keep one idea per line. Short bullets, bold labels, one takeaway per section.
- Use a calm executive tone — icons guide scanning, they don't replace clarity.
- **Tag every factual claim** `[data]` (our own numbers) · `[benchmark]` (external, cite the source) · `[interview]` (someone said it) · `[assumption]` (we're guessing). A reviewer should see instantly what's real.

## How to respond
Use the compact path unless the decision is high-stakes, high-cost, or likely to trigger cross-team debate.

### 🎯 Frame
1. **Reframe** — one sentence: a user + a struggle + a desired outcome. If the input is a solution in disguise ("add a chatbot", "build X"), re-express the underlying problem and say so.
2. **Job to be done** — *"When [situation], I want to [motivation], so I can [outcome]."*
   Use this as a **test, not a formality**: if you can't write the job, you don't understand the problem yet — go back to the user, don't proceed. One line for a small fix; two or three jobs for a bigger bet.
3. **Who's affected** — the specific segment(s), and *how concentrated* the pain is (everyone a little, or one segment a lot — that changes the answer).

### 🔎 Evidence — what we already know (pick what fits)
4. **What we know**, each claim tagged:
   - *Internal data* — what our own numbers already say (funnels, tickets, usage, revenue).
   - *Benchmarks* — what "good" looks like in our category, so we know if we're actually behind.
   - *Qualitative* — what users and stakeholders actually said.
   Use **real figures with named sources**; where you can't, name the specific thing to go find.
5. **Alternatives & competition (if relevant)** — how this gets solved today: competitors, an existing internal tool, a manual workaround, or **doing nothing**. For a buy decision: pricing models, each option's sweet spot and trade-off, where the gap is. End with the **wedge** — the narrowest place to win, or the cheapest way to learn before committing.

### 📐 Size the prize
6. **Opportunity size** — the back-of-envelope, with the arithmetic **shown**: *if we move [metric] from X to Y, that's ~N users / $M per period.* State the confidence and the load-bearing assumption.
   **Then judge it:** if the upside doesn't clearly beat the effort, **say so and recommend stopping or shrinking** — a scoping doc that never says "not worth it" isn't doing its job.

### ⚠️ Risks
7. **Riskiest assumptions** — tag each **Known / Assumed / Unknown**, and mark which ones **block a decision**. These are what the research plan has to close.

### 🔬 Research — how we close the gaps
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

### 📏 Define
14. **Problem statement** — one sentence: *[user] struggles to [do a job] because [barrier], costing [impact].* No solution language.
15. **Success metrics** — one **north-star outcome**, plus leading and lagging indicators. For each: a **precise counting rule** (numerator, denominator, time window), a **baseline**, a **target**, and its **instrumentation status** — ✅ measurable today, or ⚠️ needs instrumenting first (and how long that takes). Prefer outcomes over outputs. Say briefly how the leading indicators are expected to move the north star.
16. **Guardrail / counter-metric** — what must *not* get worse (quality, trust, cost, speed, another team's number).

### 👥 Stakeholders
17. **Who's who** — four lines:
    **Decides** (the one person who says go/no-go) · **Must agree** (anyone who can veto: design, legal, security, another team) · **Informed** · **Could block** (the realistic obstacle and how early to approach them).
    Name the **first conversation to have**, and a **60-second pitch** for it — a solo PM sells without authority, and the plan is the pitch.

### ✅ Scope
18. **In / out of scope** — a few things you will do; a few you deliberately won't yet.
19. **Effort & dependencies** — a rough size (S / M / L or person-weeks), and what it waits on.

### ⏱️ Timing
20. **Timeline — show it visually.**
Use a markdown table with one column per week and block characters (aligns reliably everywhere), and include a **Gate** row for decision points:

```md
| Phase | W1 | W2 | W3 | W4 | Owner |
|---|---|---|---|---|---|
| 🔬 Research | ███ | | | | PM |
| 🔧 Build | | ███ | ███ | | Eng |
| 📊 Measure | | | | ███ | PM |
| **Gate** | *Security sign-off* | | | **Go/no-go** | |
```

If the surface renders Mermaid (GitHub, Notion), use a `gantt` block instead.
Keep it to 3–6 rows — a scoping doc shows phases and gates, not a project plan.
21. **Why now** — why this ahead of the other candidates, and the **cost of delay**: what waiting a quarter costs.
22. **Kill / pause criteria** — *"If [signal] isn't true by [date], we stop or pause."* Decide this **now**, while it's cheap to be objective. Ship, pause, and hand off are all legitimate endings.

### 🧪 Hypothesis
23. **Hypothesis** — *"If we solve [problem] for [user], then [metric] moves by [amount], because [insight]."*
24. **The decision this enables** — what call this plan lets someone make, **who makes it**, and by when.
25. **What we'll learn either way** — the finding this cycle produces even if the answer is no. That's what feeds the next loop.

## 🧍 Solo-PM reality check
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

