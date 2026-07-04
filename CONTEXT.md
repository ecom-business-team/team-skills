# Skills Marketplace — System Context

**What it is:** The `ecom-business-team/team-skills` GitHub repo. A Claude Code plugin marketplace that lets the whole team share, install, and improve skills from one central place. Every skill is production-quality (see [CONTRIBUTING.md](CONTRIBUTING.md)).

**Repo:** https://github.com/ecom-business-team/team-skills

**Local clone:** this folder (`/Users/zacharyblake/Desktop/ClaudeCode/team-skills/`) is the working copy of the repo. Edits here + `git push` = published to the team.

## Purpose

Solve the "how does the team share work across Claude Code" problem without inventing infrastructure. Uses Claude Code's native plugin/marketplace mechanism plus standard GitHub PR flow. Two custom skills (`/team-skills-add`, `/team-skills-browse`) hide git and the `/plugins` command surface so non-technical teammates never need to learn either.

## What lives here

| File / Folder | What it is | Living or disposable |
|---|---|---|
| `README.md` | Team-facing onboarding — the 3-command install and update flow | Living |
| `CONTRIBUTING.md` | The shipped-quality checklist every skill must pass | Living |
| `CONTEXT.md` | This file — the local index (Zak's personal map) | Living |
| `LIBRARY.md` | Enumerated list of every plugin and skill with descriptions | Living — regenerate when skills are added/removed |
| `flow.html` | Interactive diagram of the publish + install flow (team-visible) | Living — update when the mechanism changes |
| `.claude-plugin/marketplace.json` | The manifest Claude Code reads when adding this marketplace | Living |
| `plugins/general/` | Skills recommended for everyone (`new-workflow`, `onboard`, `team-skills-add`, `team-skills-browse`) | Living |
| `plugins/team-build-kit/` | The `/memo -> /prd -> /build -> /ship` lifecycle | Living |
| `plugins/copywriting/` | Copywriter skills — placeholder pending first contribution | Living |
| `plugins/creative-strategy/` | Creative strategist skills — placeholder pending first contribution | Living |
| `plugins/media-buying/` | Media buyer skills — placeholder pending first contribution | Living |

## How to find X

| Question | Look here |
|---|---|
| "What plugins exist and what's in them?" | [LIBRARY.md](LIBRARY.md) |
| "How does a teammate install this?" | [README.md](README.md) — 3 commands |
| "How does a teammate submit a skill?" | [CONTRIBUTING.md](CONTRIBUTING.md) + `/team-skills-add` |
| "How does the whole system work end-to-end?" | [flow.html](flow.html) — visual diagram |
| "Who owns each plugin?" | Each plugin's own `README.md` |
| "What's the source of truth for what's live?" | `.claude-plugin/marketplace.json` on `main` |

## Plugin owners

| Plugin | Owner | Status |
|---|---|---|
| `general` | Zachary Blake | Live |
| `team-build-kit` | Zachary Blake | Live |
| `copywriting` | TBD | Placeholder |
| `creative-strategy` | TBD | Placeholder |
| `media-buying` | TBD | Placeholder |

## Governance

- **PR-only** — direct commits to `main` are blocked (except for Zak as org admin, for seeding)
- **1 required approval** per PR
- Plugin owners are the reviewers for PRs to their plugin
- New plugins are proposed via PR (open against `general`, note the request in the description)

## The two custom skills (why they exist)

The whole point of this system is that **teammates never touch git or memorize `/plugins` commands.** Two skills carry that promise:

- **`/team-skills-add`** — teammate says "I want to share this skill." Skill runs the CONTRIBUTING checklist against the skill, forks the repo, branches, commits, opens the PR. Teammate sees a PR URL and confirmation.
- **`/team-skills-browse`** — teammate says "what's available?" Skill fetches the marketplace catalog live from GitHub, presents plugins + skills with descriptions, installs what's picked.

Both live in `general` so every teammate has them from day one.

## What this system does NOT include (yet)

- **Centralized context sharing** — deferred by Zak's call. Skills and repos only for now. Revisit when team is actively using this and a specific context-sharing pain surfaces.
- **Workflow (n8n) sharing** — deferred. Team isn't using shared n8n workflows yet.
- **A knowledge base** — Zak's flagged as future work, not priority now.

## Cross-workspace links

Points down (sub-areas):
- Each `plugins/<name>/` is its own logical sub-area with its own README and owner.

Points up (cross-workspace):
- Root [CLAUDE.md](../CLAUDE.md) routing table (this system is registered there)
- The `team-build-kit/` folder at the workspace root is the **source** for the `team-build-kit` plugin content; if that folder is updated, propagate the change into `plugins/team-build-kit/skills/`

## Don't Load (for this system)

- `ad-bounty/`, `northstar/`, `ad-analysis/`, `personal-os/` — unrelated systems
- The workspace's own `~/.claude/skills/` — Zak's local skills. Only relevant if the current task is publishing one of them into the marketplace.
