---
name: browse-skills
description: Browse and install skills from the ecom-business-team marketplace without needing to know plugin commands or GitHub. Shows what plugins and individual skills are available, lets the user pick, and installs. Use when the user asks "what skills are available", "what can I install", or "show me what the team has built".
---

# /browse-skills

**Purpose:** Give the user a friendly, interactive way to discover and install skills from the ecom-business-team marketplace. Hide the `/plugins` command surface — the user shouldn't need to know it exists.

**Marketplace repo:** `https://github.com/ecom-business-team/skills`

## Flow

### Step 1 — Ensure the marketplace is added

Check if the user has the marketplace added. If not, run:

```
/plugins marketplace add ecom-business-team/skills
```

(You can invoke this directly. If Claude Code prompts the user for confirmation, that's fine — one-time cost.)

### Step 2 — Fetch the marketplace catalog

Pull the current manifest so you show what's live *right now*, not stale info:

```bash
curl -sL https://raw.githubusercontent.com/ecom-business-team/skills/main/.claude-plugin/marketplace.json
```

Parse the `plugins` array. For each plugin, note: `name`, `description`, `category`.

### Step 3 — Present the catalog

Show plugins grouped by category (`general` first, then `domain` plugins). Format:

```
GENERAL — recommended for everyone
  ✓ general           General-purpose skills (new-workflow, onboard, contribute-skill, browse-skills)
  ✓ team-build-kit    The memo -> prd -> build -> ship lifecycle

DOMAIN — pick your role
    copywriting       Skills for copywriters
    creative-strategy Skills for creative strategists
    media-buying      Skills for media buyers
```

Mark installed plugins with `✓`. Check installed status by inspecting the user's local plugin state (whatever mechanism Claude Code uses — read from settings if available; if not, ask the user to confirm what they already have).

### Step 4 — Drill in (optional)

Ask if the user wants to see individual skills inside a plugin before installing. If yes, fetch the plugin's skill list from GitHub:

```bash
# List skill folders in the plugin
curl -sL https://api.github.com/repos/ecom-business-team/skills/contents/plugins/<plugin>/skills
```

For each skill, fetch its SKILL.md frontmatter and show `name: description:` as a one-liner.

### Step 5 — Install what they picked

For each plugin the user wants:

```
/plugins install <plugin-name>
```

Confirm each install worked. If a plugin fails (network, permission), print the error and continue with the rest.

### Step 6 — Report

Tell the user:
- *"Installed: `<list>`. These skills are available in every Claude Code session from now on."*
- *"To get the latest versions in the future, run `/plugins marketplace update`."*
- *"To browse again, run `/browse-skills`."*

## Design notes for future maintainers of this skill

- **Do not hardcode the skill list.** Always fetch from GitHub live. That way when someone contributes a new skill, it shows up here immediately without needing to update this skill.
- **Do not require the user to know about `/plugins`.** The whole point of this skill is to hide that mechanism. Only surface it if the user explicitly asks.
- **Fail gracefully offline.** If the fetch fails, tell the user the marketplace is unreachable and suggest they check their internet.
