# Plan — Fix the biggest onboarding leak

> **Artifact produced by:** `scope` &nbsp;·&nbsp; **Input:** [discovery-notes.md](../discovery-notes.md) &nbsp;·&nbsp; **Scale:** small — one engineer, two weeks. No market analysis needed; benchmarks and our own funnel are the relevant context.

## Reframe
When someone signs up, they want to reach the point where the product is obviously useful — but most never get there, so the signup growth doesn't turn into paying customers.

## Who's affected & the job
New self-serve signups (~8,000/month).
*"When I sign up for a tool, I want to get to something useful fast, so I can tell whether it's worth my time."*

## Evidence & context
- **Our funnel (last month):** 8,000 signed up → 1,900 created a first project → 700 invited a teammate. End-to-end **8.8%**.
- **Activation benchmark:** average SaaS activation is **~36% (median 30%)**; above 40% is solid. Our first-project activation is **23.8%** — we're **below median**, so this is a real gap, not just impatience. *(ChurnWard, 2026)*
- **Known fixable patterns:** in a study of 3.9M signup sessions across 480 products, cutting the form from 7 fields to 3 reduced abandonment **44.7%**, and a visible progress bar cut first-stage drop-off from **38.4% → 24.1%**. *(UXCam, 2026)*
- **Empty-state risk:** onboarding checklists retained **47.9% more** users through the 30-day activation window. *(OpenView, 2026)*
> Public 2026 benchmarks — directional. Our own funnel numbers are the ones that decide this.

*No competitive analysis here — this is an internal UX leak, not a market bet. Skipping it on purpose.*

## Riskiest assumptions
| Assumption | Status | Fastest check |
|---|---|---|
| The empty dashboard is why people stall before a first project | **Assumed** | 5 session replays + an exit survey on that screen (2 days) |
| Verification email is a minor leak, not a major one | **Known** (funnel says 8.9%) | — |
| People who create a project are meaningfully more likely to convert | **Assumed** | Compare conversion of project-creators vs. not (1 query) |

## Problem statement
New signups struggle to reach a first useful outcome because the product gives them an empty screen with no obvious next step — so only 23.8% ever create a project (vs. a ~30–36% benchmark) and signup growth doesn't convert.

## Success metrics
| Type | Metric (counting rule) | Baseline | Target |
|---|---|---|---|
| North star | **Activation rate** = users creating a first project ÷ signups, within 7 days | **23.8%** | **≥ 32%** (median-ish) |
| Leading | Step conversion, *Profile set up → First project* | **40.4%** | **≥ 55%** |
| Lagging | End-to-end signup → teammate invited | 8.8% | ≥ 12% |

**Guardrail / counter-metric:** don't buy activation with annoyance — **support tickets about onboarding and opt-outs must not rise**, and we don't force a project on people just to tick the metric (quality of first project matters).

## Scope
**In:** the single biggest leak — the step from profile setup to first project. One change, measured.
**Out (for now):** redesigning the signup form, the verification email, and the invite step. They're real, just smaller.

## Timeline (2 weeks)
1. Days 1–2: confirm the *why* (replays + exit survey). Days 3–7: build the fix. Days 8–14: run the experiment, read results.

## Hypothesis
If new users land on a pre-filled sample project instead of an empty screen, activation rises from 23.8% toward ~32% — because 2,800 of the 7,300 users we lose (38%) drop at exactly that step, and the benchmark data says empty-state friction is the usual cause.
