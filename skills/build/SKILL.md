---
name: build
description: Turn a scoped plan into the smallest real artifact that tests its core assumption — a fake door, a Wizard-of-Oz trial, a clickable flow, a thin working prototype, a spreadsheet model, or a doc. Produces a structured handoff block (artifact type, the assumption being tested, the success and kill signals, tool stack, what's faked, how it scales) plus a runnable artifact. Covers platform-agnostic tool selection across open-source, Anthropic, OpenAI, Google, Microsoft, and app builders like v0, Lovable, and Replit; a no-engineering build path; and how a model integrates if AI is involved. Use whenever a PM needs to prototype, test an idea cheaply, choose tools, or make something concrete enough for people to react to. Triggers include "build a prototype", "how do I test this", "which tools should I use", "stand up a demo", "make an MVP", "prototype without engineers", "how would this scale". This is step 2 of Scope -> Build -> Iterate.
---

# Build — the smallest artifact that proves the assumption

**Build to learn quickly, not to impress.** The goal is not a polished product. The goal is something concrete enough that people can react to it — and a reaction you can read as signal.

## Core objective
- Identify the single assumption that matters most.
- Choose the smallest artifact that can test it.
- Prefer a low-fidelity prototype, mock, script, workflow, or lightweight page over a full implementation.
- Decide **before you build** what reaction would confirm the assumption, and what would kill it.

## When to use / when not to
- **Use** once the problem, metric, and riskiest assumption are reasonably clear (ideally from `scope`).
- **Don't use** to frame the problem (`scope`) or to refine and ship what you built (`iterate`).

## Input — what this needs
A scoped plan, or at minimum: the assumption to test, who it's for, the constraint (deadline, data sensitivity, existing stack).

**Ask before inventing.** If the assumption isn't clear, ask for it — building the wrong thing fast is still building the wrong thing. **Timebox it:** state up front how long this build should take (hours for a mock, days for a thin prototype). If the estimate exceeds the learning value, say so and shrink the artifact.

## Required output shape

Produce this block first. **Core fields always; extended fields in Full mode.**

```
# core
artifact_type:      # fake door | wizard-of-oz | clickable | thin working thing | model/spreadsheet | doc
proof_goal:         # the ONE assumption this tests, stated so it could fail
success_signal:     # the reaction/result that confirms it (be specific: "3 of 5 users X")
kill_signal:        # the reaction that says stop or rethink
artifact_path:      # file path, or "n/a — manual/offline artifact"
tool_stack:         # tools chosen + the constraint that drove the choice
fakes_or_stubs:     # everything not real: data, integrations, auth, and the model itself
handoff_target:     # iterate | scope | ship

# extended (Full mode)
audience:           # who reacts to it, and how many
why_this_form:      # why this is the smallest useful version
scaling_plan:       # what changes if the signal is positive
effort:             # S / M / L, or hours–days
demo_steps:         # 3–5 beats, plus an offline fallback
```

Then add supporting notes — **reasoning, not a restatement of the block**:
- decision rationale (what you considered and rejected)
- failure modes and risks
- where a real engineer is genuinely needed (be honest; don't oversell no-code)
- a visual design note, if it's a UI artifact

## Choosing the artifact form
Pick one and justify it in `why_this_form`:

| Form | Best when the question is | Typical cost |
|---|---|---|
| **Fake door / landing test** | does anyone want this at all? | hours |
| **Wizard-of-Oz / manual trial** | is the outcome valuable, before we automate it? | days |
| **Clickable flow** | is the flow understandable? | hours |
| **Thin working thing** | does the core mechanic actually work? | days |
| **Model / spreadsheet** | do the numbers hold up? | hours |
| **Doc / spec** | do we agree on what we're doing? | hours |

Not everything is an app. If a spreadsheet or a human behind the curtain answers the question, that's the right build.

## Tool map — platform-agnostic
Let **constraints** pick the tool — data residency, existing stack, budget, control, speed — not brand loyalty. Always name an alternative.

- **Models:** open-weight (Llama, Mistral, Qwen) for control/on-prem · hosted APIs (Anthropic Claude, OpenAI GPT, Google Gemini) for speed.
- **Orchestration & retrieval:** LangChain, LlamaIndex · vector stores (pgvector, Qdrant, Weaviate, Pinecone).
- **Rapid prototyping:** coding agents (Claude Code, Cursor) · app builders (v0, Lovable, Replit, Bolt).
- **Corporate stacks:** Microsoft (Foundry, Copilot Studio) · Google (Gemini Enterprise, Vertex) · AWS (Bedrock).
- **No-code / analysis:** Power Platform, AppSheet, Airtable, a spreadsheet, your analytics tool.

State the constraint that drove the pick, e.g. *"hosted API — no sensitive data, and speed matters more than control here."*

## Visual bar (UI artifacts)
Make it feel intentional and credible, not production-grade:
- **Single-file HTML by default**, no external dependencies or CDNs — a demo that needs the network is a demo that fails on stage.
- One accent color on a neutral base; **two type sizes and one weight jump** carry the hierarchy. A system font stack is fine.
- Consistent spacing rhythm, generous whitespace, left-aligned body text.
- Lightweight icons (emoji-style or inline SVG) where they speed comprehension.
- **Show the reasoning, not a black-box answer** — evidence beside every output is what makes a prototype trustworthy.
- **Realistic sample data, never lorem ipsum.** Fake-looking data makes real logic look fake.

## Rules
- **One artifact, one question.** Don't overbuild.
- **Never use real customer data.** Synthetic or sample only, until security has cleared the path.
- Kill live external dependencies for demos: cache, stub, or pre-record, and keep an offline fallback.
- Be explicit about what's faked — including the model — so nobody mistakes a demo for production.
- Optimize for speed and rebuildability, not elegance. Pick what you can change in front of someone.
- Keep the output easy for later steps to ingest: consistent field names, a self-explanatory artifact, an explicit handoff target.

## Modes
- **Compact** (small stakes): the core block + three bullets of reasoning. Nothing else.
- **Full** (higher stakes): core + extended block, plus decision rationale, failure modes, readiness questions, and the demo script.

## 🧍 Solo-PM check
- **Timebox** — how long will this take, and does it beat the learning value?
- **Solo-doable vs. needs someone** — what can you build alone this week; what needs a designer, a data pull, or an approval? Start that dependency now.
- **Who reacts** — name the 3–5 real people who'll see it. An artifact nobody reacts to produced no signal.
- **Leaves behind** — the template, component, or dataset you'll reuse next cycle.

## Ready for Iterate?
- [ ] Does the artifact test **one** assumption, and could it fail?
- [ ] Are the success and kill signals written down *before* anyone sees it?
- [ ] Is everything faked listed — and is the data synthetic?
- [ ] Can you demo it end-to-end, offline?
- [ ] Is `handoff_target` set?

## Handoff
Pass the artifact and its signals to **`iterate`** to refine it, prove it's good enough, and decide whether to ship, pause, or hand off. If the signal shows the assumption was wrong, go back to **`scope`**.

## Example
See [`examples/prototype/funnel-leak-finder.html`](../../examples/prototype/funnel-leak-finder.html) — a single-file prototype that shows its reasoning, with an on-page view of how it scales.
