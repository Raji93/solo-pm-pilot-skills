# Test & ship plan — the onboarding fix

> **Artifact produced by:** `iterate` &nbsp;·&nbsp; **Input:** the [prototype](../prototype/funnel-leak-finder.html) + team feedback &nbsp;·&nbsp; **Note:** no AI in this solution, so Phase 2–3 use an experiment and test cases rather than evals and a golden dataset.

## Phase 1 · Refine (from feedback)
| Feedback | Change | Impact / effort |
|---|---|---|
| "It ranked steps by % — that pointed us at the invite step, which barely loses anyone" | **Rank by users lost**, flag the steepest % separately | High / Low ✅ done |
| "I want to see the leak, not read a table" | Added a kept-vs-lost bar per step | Med / Low ✅ done |
| "It tells me *where*, not *why*" | Correct — that's a human + session-replay job (and where a model would help later) | — acknowledged, out of scope |
| "Can it pull from Amplitude directly?" | Deferred; pasting a funnel is enough to make the call this week | — deferred |

Each change was checked against the guardrail: nothing here pushes us toward gaming activation.

## Phase 2 · Define "good enough"
The instrument is an **A/B test**, not an eval — this is a UI change, not a model.

| What we're checking | How | Pass bar (set before we look) |
|---|---|---|
| Does the sample project raise activation? | A/B test, activation within 7 days | **≥ +6 points** (23.8% → ≥30%), statistically significant |
| Did we annoy anyone? | Support tickets tagged onboarding + opt-outs | **No increase** vs. the prior 2 weeks |
| Is the activation real, not hollow? | % of activated users who return in 7 days | **Not lower** than today's returning rate |
| Does it work on mobile and slow connections? | QA test cases | All pass before launch |

**Sample size:** ~100–500 conversions per variant is the usual bar for a readable result at this effect size — at 8,000 signups/month, that's roughly a two-week run. Decide the duration up front and don't peek early.

## Phase 3 · Build the test set
- **Experiment cohorts:** new signups only, randomly assigned, cohorted by signup week (not a before/after snapshot — that would smuggle in seasonality).
- **QA test cases:** empty state on mobile · slow connection · a user who deletes the sample project · a returning user who already has projects (must *not* see it) · screen-reader pass.
- **Edge cases to watch:** users who create the sample project but never open it — that's activation theater, and the returning-rate check is what catches it.
- **Held back:** don't touch the signup form or verification email during the test, or we won't know what moved the number.

## Phase 4 · Run it
- Run two weeks, read against the pass bars, and check the counter-metric **before** celebrating.
- **If it passes:** ship to 100%, then re-run the funnel — the next-biggest leak becomes the next project (probably signup → account created, at 2,400 users).
- **If it fails:** the diagnosis was wrong, not the method. Go back to the replays and the exit survey before building anything else.
- **Regression:** keep the QA cases; re-run them on the next onboarding change.

## Path forward
**Readiness checklist**
| Area | Status |
|---|---|
| Security / privacy (no new data collected) | Ready |
| Governance (an owner for the activation metric) | Ready — this PM |
| Accessibility (screen reader, contrast) | **Gap** — in the QA cases above |
| Reliability (sample project creation can fail) | **Gap** — needs an error path |
| Support readiness (docs + a note to the support lead) | Gap — before launch |

**The decision:** **ship it ourselves.** Small blast radius (new signups only), no sensitive data, no new integrations, one engineer for two weeks, and the PM owns the metric. This does not need an engineering hand-off or a vendor.

**What we'd revisit:** if the fix works and we want the *why* automated across every step — session replays, exit surveys and tickets summarized per leak — that's a bigger build and the point where a model earns its place. Different decision, different scope. Start it back at `scope`.
