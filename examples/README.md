# See the skills in action

A problem every PM has lived — *"signups are up, conversion is flat, and everyone has a different theory about why."* Run through all three skills, with the **real artifacts** each produces.

> **Scenario.** 8,000 signups last month; only 700 ever invited a teammate. The designer wants to redesign the empty state, growth wants to cut form fields, support wants to fix the verification email. There's **one engineer for two weeks**. The PM has to pick one thing and explain why. Full input: [`discovery-notes.md`](./discovery-notes.md).

This example is deliberately **small and non-AI** — it shows the skills right-sizing themselves. (The same three skills handle a market-facing bet; they just pull in market and competitive analysis when it's relevant, and evals when a model is involved.)

---

## 1 · Scope → a plan you can defend
📄 **[`artifacts/plan.md`](./artifacts/plan.md)**

Reframes the problem, sizes it against **real 2026 benchmarks** (our 23.8% activation vs. a ~30–36% median — so this is a genuine gap, not impatience), lists the riskiest assumptions with fast checks, and defines metrics **precisely** (activation = first project within 7 days) with a counter-metric that stops us gaming it. Note what it *skips*: **no competitive analysis** — this is an internal UX leak, not a market bet, and the plan says so.

## 2 · Build → the smallest real thing
🖥️ **[`prototype/funnel-leak-finder.html`](./prototype/funnel-leak-finder.html)** — open it in any browser.

Paste your funnel steps → where users are lost and **what to fix first**. The insight it makes on screen: **steepest ≠ biggest.** The steepest drop is the invite step (63%), but it only loses 1,200 people; the biggest leak is *profile → first project*, which loses **2,800 — 38% of everyone you lose.** Percentages point at small steps late in the funnel; people are lost where the traffic is. Below the demo, a **"how this scales"** view marks the one place a model would actually help: diagnosing *why* people drop, not *where*.

## 3 · Iterate → prove it, then ship
📝 **[`artifacts/test-and-ship-plan.md`](./artifacts/test-and-ship-plan.md)**

Refinements from the team, then — because this is a UI change, not an AI system — the "good enough" check is an **A/B test with pass bars set before looking** (≥+6 points activation, no rise in support tickets, no drop in return rate), plus QA cases and the sample-size/duration decided up front. Ends with a readiness checklist and a clear call: **ship it ourselves** — small blast radius, no sensitive data, one owner. No hand-off, no vendor.

---

## The trail
```
discovery-notes.md → plan.md → funnel-leak-finder.html → test-and-ship-plan.md
   (raw input)        SCOPE       BUILD                      ITERATE
```
One PM, one week: a noisy debate turned into one defensible decision, an artifact that proves it, and a test that will tell you if you were right.
