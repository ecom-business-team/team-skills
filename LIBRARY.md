# Skills Library

Every plugin and skill available in the ecom-business-team marketplace. Regenerate when skills are added or removed.

> **How to install:** `/plugins install <plugin-name>` in Claude Code, after adding this marketplace (`/plugins marketplace add ecom-business-team/skills`).
>
> **Easier way:** Run `/browse-skills` — it does the discovery + install for you.

---

## `general` — recommended for everyone

**Owner:** Zachary Blake
**Install:** `/plugins install general`

| Command | What it does |
|---|---|
| `/new-workflow` | Turn a repeat process into a reusable skill through a guided interview. The daily driver for building your own skill library. |
| `/onboard` | First-run skill for someone new to Claude Code. Interviews the user about their work, scaffolds a personalized workspace with CLAUDE.md, CONTEXT.md files, and visual folder maps. |
| `/contribute-skill` | Submit a skill from your local `~/.claude/skills/` to this marketplace. Runs the quality checklist, forks + branches + commits + opens a PR on your behalf. You never touch git. |
| `/browse-skills` | Browse and install skills from this marketplace without knowing plugin commands. Shows what's available across all plugins, lets you pick, and installs. |

---

## `team-build-kit` — the three-gate build lifecycle

**Owner:** Zachary Blake
**Install:** `/plugins install team-build-kit`
**Big idea:** *Complexity is the enemy. If you can't explain it simply, it's probably too complicated.*

| Command | When to use it | Gate |
|---|---|---|
| `/new-workspace` | Before building anything — sets up a tidy home for your work | (foundation) |
| `/memo` | You have an idea worth building | **Gate 1 — should this exist?** |
| `/prd` | The idea is worth it — now design it properly | **Gate 2 — is it designed right?** |
| `/build` | The design is solid — implement it | (execution) |
| `/ship` | It works — but others will rely on it, or it touches money or real data | **Gate 3 — safe to rely on?** |
| `/quick-fix` | Something small broke or a tiny tweak — no ceremony needed | (below the gates) |

---

## `copywriting` — for copywriters

**Owner:** TBD
**Install:** `/plugins install copywriting`
**Status:** Placeholder — awaiting first contribution. Be the first to run `/contribute-skill` and submit something.

---

## `creative-strategy` — for creative strategists

**Owner:** TBD
**Install:** `/plugins install creative-strategy`
**Status:** Placeholder — awaiting first contribution.

---

## `media-buying` — for media buyers

**Owner:** TBD
**Install:** `/plugins install media-buying`
**Status:** Placeholder — awaiting first contribution.

---

## Getting updates

```
/plugins marketplace update
```

Refreshes everything you have installed. Run whenever you want the latest.
