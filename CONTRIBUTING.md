# Contributing to the Skills Marketplace

The bar for this marketplace is high on purpose: **every skill here is production-quality.** When a teammate installs a skill from this repo, they should be able to trust it the same way they'd trust a shipped tool.

## The standard

A skill can be merged into this marketplace when it clears every item on this checklist. The `/git-add` command walks you through it — you don't need to check them manually.

- [ ] **Clear one-line description** in the skill's frontmatter that tells another teammate *when to invoke it*, not just what it does.
- [ ] **Runs end-to-end on a fresh machine.** No hardcoded paths to `/Users/yourname/...`. No assumed local files that only exist on your Mac.
- [ ] **No secrets, no personal API keys, no personal IDs.** Nothing that would break for someone else or leak your credentials.
- [ ] **No workspace-specific IDs baked in** (ClickUp list IDs, n8n workflow IDs, Supabase keys) unless the skill is scoped to a domain where those are shared.
- [ ] **At least one usage example** in the skill body — a real prompt a teammate might type.
- [ ] **The author has actually used it for real work** — not just written it. If you haven't run it in anger at least once, it doesn't belong here yet.
- [ ] **Fits its plugin's domain.** Copywriting skills go in `copywriting`. Cross-role skills go in `general`. If it doesn't fit any existing plugin, propose a new one in the PR.

## The lifecycle framing

If you're familiar with the `/memo -> /prd -> /build -> /ship` lifecycle, this checklist is the `/ship` gate applied to a skill. The skill IS the shipped artifact. The PR to this repo is the go-live moment. Reviewers verify it's safe for the whole team to rely on.

Skills that are half-built, personal experiments, or workspace-specific don't belong here — keep those in your own `~/.claude/skills/` folder until they're ready.

## The submission flow (for non-technical teammates)

You do not need to know git. Use `/git-add` in Claude Code:

1. It asks which skill you want to submit.
2. It runs the checklist above and flags anything missing so you can fix it first.
3. It picks the right plugin (`general`, `copywriting`, etc.).
4. It forks the repo, branches, commits, and opens a PR on your behalf.
5. The plugin owner reviews. If it passes, they merge. Everyone gets it on their next `/plugins marketplace update`.

## Review

Each plugin has an owner (see the plugin's own README). The owner is the person who reviews PRs to that plugin and decides what belongs. When a PR is opened, the plugin owner:

1. Verifies the checklist above.
2. Reads the skill and considers whether it fits the plugin's domain.
3. Merges, requests changes, or closes with a reason.

## Removing a skill

If a skill has gone stale, is duplicated by a better one, or was merged in error, open a PR removing it. Same review process in reverse.
