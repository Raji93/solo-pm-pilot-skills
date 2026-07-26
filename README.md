# Solo-PM Pilot Skills — a cross-platform playbook

Three Agent Skills that walk an enterprise pilot from a messy discovery call to a production decision — as one PM, without an engineering team.

> *Platform steps verified as of 26 July 2026. These UIs and product names change fast — re-check before you rely on them.*

```
Scope  ─→  Build  ─→  Iterate
(discovery      (plan → a        (feedback + evals →
 → a scoped      working          refine, then ship
 pilot plan)     prototype)       or hand off)
```

| Skill | Takes | Gives you |
|---|---|---|
| [`scope`](./skills/scope/SKILL.md) | messy discovery notes | a scoped pilot plan: problem, JTBD, metrics, scope, timeline |
| [`build`](./skills/build/SKILL.md) | a scoped plan | a build plan + tool map + no-eng path + demo script |
| [`iterate`](./skills/iterate/SKILL.md) | a working prototype + feedback | refine from feedback, prove with evals, then decide ship vs. hand off |

Each hands its output to the next; `iterate` loops back to `scope` if the problem turns out wrong.

**Two forms, same logic:** each skill is a `SKILL.md` in [`skills/`](./skills) (canonical, auto-triggering) and a paste-ready prompt in [`prompts/`](./prompts) (`scope.md`, `build.md`, `iterate.md`) for any chat that doesn't load skills.

---

## First, the one rule that governs everything

A `SKILL.md` **auto-triggers only where the runtime implements Agent Skills** (Claude, and Microsoft Foundry / Gemini Enterprise on the platform side). **Everywhere else the skill still works** — you either paste its body as instructions, or bake it into a reusable custom agent. Same file, different door.

Two tiers to remember:
- **No setup, anyone:** paste the skill body into a chat, or save it as a custom agent (Custom GPT / Gemini Gem / Copilot Studio agent).
- **Platform, native:** the SKILL.md file loads directly (Claude Code, claude.ai, Foundry, Gemini Enterprise).

---

## Platform playbook

### 1. Claude Code — native, recommended
Skills auto-trigger by their `description`, and Claude Code can also build and run a prototype.
1. Put the three folders where Claude Code looks:
   - **This project:** copy `skills/scope`, `skills/build`, `skills/iterate` into `.claude/skills/` at your project root.
   - **All your projects:** copy them into `~/.claude/skills/` instead.
2. Start Claude Code in that folder: `claude`.
3. Verify: ask **"What skills are available?"** — you should see scope, build, iterate.
4. Run them:
   - **Auto** — just describe the task: *"Scope a pilot from these notes: …"*
   - **Manual** — force it: `/scope`, `/build`, `/iterate`.
5. Manage: update = replace the folder · disable = rename with a leading underscore (`_scope`) · remove = delete the folder.

### 2. claude.ai — native upload
1. Requires a paid plan (Pro / Team / Enterprise); on Team/Enterprise an admin may need to enable Skills.
2. **Settings → Capabilities → Skills → add a custom skill.** Upload each skill folder (zip the folder if prompted). Repeat for all three.
3. Use it: describe the task in a chat; Claude applies the matching skill automatically.
4. Note: claude.ai reasons through **scope** and **iterate** well, but can't run a local prototype — do **build** in Claude Code.

### 3. ChatGPT — paste or Custom GPT
- **Quick:** paste the matching file from [`prompts/`](./prompts) (or the `SKILL.md` body below the frontmatter) into a chat, then your input.
- **Reusable:** create a **Custom GPT**, paste the skill body into its **Instructions**, optionally attach `SKILL.md` as a knowledge file. No auto-trigger by description — the whole GPT *is* the skill.

### 4. Google Gemini — Gem or Gemini Enterprise
- **Gemini app:** create a **Gem**, paste the skill body into its instructions → a reusable version. Or paste for a one-off.
- **Gemini Enterprise / Agent Platform:** loads `SKILL.md` natively — mount skills via the **Skill Registry** or a **Cloud Storage** bucket (best practice: under `/.agent/skills`), and it supports MCP servers too.

### 5. Microsoft Copilot — paste, agent, or MCP
- **Copilot chat (M365):** can't load a SKILL.md — paste the skill body + your input in one message.
- **Copilot Studio agent (reusable):** paste the skill body into the agent's **Instructions**, add `SKILL.md` as **Knowledge**, publish to Teams / M365 Copilot.
- **MCP (closest to native triggering):** turn on generative orchestration and connect your skills via an MCP server through the MCP wizard.

### 6. Microsoft Foundry — Skills API
Register each `SKILL.md` through the **Foundry Skills API** (versioned), then deliver it either by **direct injection** (loaded as session instructions, always on) or via a **Toolbox** (MCP endpoint) so the agent discovers and loads it at runtime.

---

## Cheat sheet

| Platform | Loads SKILL.md natively? | How you use it |
|---|---|---|
| Claude Code | Yes | copy into `.claude/skills/`, then `/scope` etc. |
| claude.ai | Yes (paid) | Settings → Capabilities → Skills → upload |
| Gemini Enterprise | Yes | Skill Registry / Cloud Storage mount |
| Microsoft Foundry | Yes | Skills API → direct-inject or Toolbox (MCP) |
| ChatGPT | No | paste body, or Custom GPT instructions |
| Gemini app | No | paste body, or a Gem |
| Copilot chat | No | paste body, or Copilot Studio agent / MCP |

---

## How to trigger and troubleshoot
- Auto-triggering keys off the **`description`** in each skill's frontmatter — it reads like the way you'd naturally ask for the task.
- If a skill won't fire: confirm with **"What skills are available?"**, then force it with **`/skill-name`**. If it still misses, the description is usually the fix.

## Before you use any of them
The tools don't do the thinking. **User research, a sharp problem statement, honest metrics, and real evals are still the PM's job** — these skills structure that work, they don't replace it. A fast proof-of-concept of the wrong thing is still the wrong thing.

## License
CC0 1.0 — public domain. Use it, change it, ship it. No attribution required.

## Publish to GitHub
```bash
cd solo-pm-pilot-skills
git remote add origin https://github.com/<you>/solo-pm-pilot-skills.git
git branch -M main && git push -u origin main
```
