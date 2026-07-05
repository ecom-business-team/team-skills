# ClickUp Operations

Skills for operating the team's shared ClickUp workspace — Ads Board tasks, Client Catalog lookups, brief workflows.

**Owner:** Spencer

**Scope note:** these skills carry baked-in shared-workspace IDs (ClickUp list IDs, Client Catalog doc IDs). That is intentional and allowed here because the whole team shares the same workspace and the same catalogs. If you fork this plugin for a different ClickUp workspace, you will need to swap those IDs — see each skill's `SETUP.md` for the mapping.

**Skills:**

- `/new-ad-idea` — interview-driven creation of a new ad idea task on the Ads Board (Client → Product → Concept → Type → Desire → Sub Avatar → Angle → Awareness → Format → breakthrough memo). Builds the task with all fields set.
- `/brief-template` — adds a client's blank brief template (pulled live from their Client Catalog) to Ads Board tasks that lack one. Scaffold only.
- `/top-lp` — adds the top control landing page to active briefs that have a template but a blank `Links to:` line. LP only.

Install with `/team-skills-browse` and select `clickup-operations`.
