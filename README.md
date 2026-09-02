# 🔒 Archived — ClaudeHAX has moved

This repository has been **archived**. ClaudeHAX is no longer distributed from
here.

The ClaudeHAX plugin has been folded into the consolidated HAX Claude Code plugin
marketplace, which now lives in the **PRAW** repository:

> **New home: <https://github.com/haxtheweb/praw>**

PRAW is the single HAX agent-ecosystem hub — it hosts the Claude Code
marketplace, the canonical rules (`RULES.md`, `WARP.md`), the workflow/knowledge
agent skills, and the vendor-neutral `llms.txt` discovery manifest. Consolidating
everything there removes the previous name collision between multiple `hax`
plugins and gives you one marketplace to add.

## Install from the new location

Inside Claude Code:

```text
/plugin marketplace add haxtheweb/praw
```

Then install the plugin that replaced ClaudeHAX — it is now named **`hax-site-ops`**
(site operations: add pages, create courses, update content, inspect, validate,
publish):

```text
/plugin install hax-site-ops@haxtheweb
```

For golden-path onboarding (scaffold a HAXsite → serve it → get a live URL in one
pass) and the `/hax-onboarding:quickstart` slash commands, also install:

```text
/plugin install hax-onboarding@haxtheweb
```

## What changed names

| Old (this repo) | New (in `haxtheweb/praw`) |
|---|---|
| `/plugin marketplace add haxtheweb/claudehax` | `/plugin marketplace add haxtheweb/praw` |
| `/plugin install hax@claudehax` | `/plugin install hax-site-ops@haxtheweb` |
| `/plugin update hax` | `/plugin update hax-site-ops` |

The site-operations skill content and reference docs (`hax-cli-reference.md`,
`hax-workflows.md`, `hax-elements-reference.md`) were carried over unchanged into
`plugins/hax-site-ops/skills/hax-site-ops/` in PRAW.

## Why archived, not deleted

The repo is kept readable so any old install instructions or links elsewhere
degrade gracefully with a clear pointer to the new home. Git history is
preserved. No further development happens here.

See the [PRAW README](https://github.com/haxtheweb/praw#readme) and the
[AI integration guide](https://github.com/haxtheweb/create#ai-integration) for
the current onboarding flow.
