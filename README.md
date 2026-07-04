# Ecom Business Team — Skills Marketplace

Shared skills for the team. Organized by functional domain. Install once, get updates forever.

## What this is

A collection of **skills** — natural-language commands you can type in Claude Code. Skills are packaged into **plugins** by role. Everyone installs `general` and `team-build-kit`. You install your domain plugin (`copywriting`, `creative-strategy`, `media-buying`, etc.) and any others you find useful.

When someone on the team improves a skill or adds a new one, you get it with a single command.

## First-time setup (3 commands)

Inside Claude Code, run:

```
/plugins marketplace add ecom-business-team/skills
/plugins install general
/plugins install team-build-kit
```

Then install your role's plugin — for example:

```
/plugins install media-buying
```

That's it. The skills are now available in every Claude Code session.

## Getting updates

Anytime you want the latest skills the team has published:

```
/plugins marketplace update
```

Anything you have installed gets refreshed. Nothing else changes.

## Discovering new skills

Don't want to memorize commands. Instead:

```
/git-browse
```

Interactively browse what's available across all domains and install what looks useful. (Installed as part of `general`.)

## Contributing a skill

Built something useful in Claude Code and want to share it with the team?

```
/git-add
```

Walks you through the quality checklist, runs the checks, and opens a pull request against this repo on your behalf. You never touch git. (Installed as part of `general`.)

## Plugins

| Plugin | Who | What's inside |
|---|---|---|
| `general` | Everyone | `new-workflow`, `onboard`, `git-add`, `git-browse` |
| `team-build-kit` | Everyone | `memo` -> `prd` -> `build` -> `ship` lifecycle for building tools you can trust |
| `copywriting` | Copywriters | *(placeholder — awaiting first contribution)* |
| `creative-strategy` | Strategists | *(placeholder — awaiting first contribution)* |
| `media-buying` | Buyers | *(placeholder — awaiting first contribution)* |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for the standard every skill must meet. Short version: skills must be **complete, standalone, and shipped-quality** — the same bar you'd use for something you rely on in production.
