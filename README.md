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

---

# Requirements

Before installing ClaudeHAX, make sure the following are installed.

## 1. Claude Code

Install Claude Code and verify it works:

```bash
claude --version
```

## 2. Node.js

Node.js 22+ recommended.

Verify:

```bash
node -v
```

## 3. npm

Verify:

```bash
npm -v
```

## 4. HAX CLI

Install globally:

```bash
npm install -g @haxtheweb/create
```

Verify:

```bash
hax --help
```

**Important**

Do NOT use:

```bash
npx hax
```

That resolves to a different npm package.

Use:

```bash
npx @haxtheweb/create
```

or the globally installed:

```bash
hax
```

command.

---

# Install ClaudeHAX Marketplace

Inside Claude Code:

```text
/plugin marketplace add haxtheweb/claudehax
```

Install the plugin:

```text
/plugin install hax@claudehax
```

Verify installation:

```text
/plugin list
```

You should see:

```text
hax
```

---

# Example Commands

Create pages:

```text
/hax add 3 pages about iguanas
```

Analyze a site:

```text
/hax analyze this site and suggest 20 new pages
```

Add a quiz:

```text
/hax add a multiple choice quiz to this page based on the page content
```

Add flash cards:

```text
/hax find a page that would benefit from flash cards and add 5 flash cards using the best HAX web component
```

Add a quiz to a specific page:

```text
/hax add a quiz to the Penn State University page
```

Add a video:

```text
/hax find a YouTube video and add it to the Ohio State University page
```

Add interactive learning content:

```text
/hax add an interactive check-for-understanding section to the iguana overview page using HAX web components, not plain HTML
```

Recommend components:

```text
/hax inspect the available HAX web components and recommend 10 components that would improve this site
```

Create a lesson:

```text
/hax create a mini lesson page about reptile habitats and include at least two HAX web components from the elements reference
```

---

# Updating ClaudeHAX

When a new version of ClaudeHAX is released:

```text
/plugin update hax
```

This updates:

- HAX CLI knowledge
- HAX web component knowledge
- HAX workflows
- HAX examples
- HAX best practices

---

# Troubleshooting

## Plugin installed but `/hax` does not exist

Verify:

```text
/plugin list
```

If HAX is missing:

```text
/plugin install hax@claudehax
```

## Marketplace installation fails

Verify internet access and confirm:

```text
/plugin marketplace add haxtheweb/claudehax
```

is spelled correctly.

## `hax` command not found

Install the HAX CLI:

```bash
npm install -g @haxtheweb/create
```

Then verify:

```bash
hax --help
```

## Node.js version too old

Check:

```bash
node -v
```

Upgrade to Node.js 22+ if needed.

## Plugin behavior seems outdated

Update the plugin:

```text
/plugin update hax
```

## Claude is not using the latest HAX commands or web components

The plugin only knows what exists in the current plugin repository version.

The maintainer must:

```bash
npm run refresh:docs
git add .
git commit -m "Refresh HAX plugin docs"
git push
```

Then users update:

```text
/plugin update hax
```

---

# For Plugin Maintainers

Refresh generated documentation:

```bash
npm run refresh:docs
```

This updates:

```text
plugins/hax/skills/hax/docs/hax-cli-reference.md
plugins/hax/skills/hax/docs/hax-elements-reference.md
```

The CLI reference is generated from:

```bash
npx @haxtheweb/create --help
npx @haxtheweb/create site --help
```

The web component reference is generated from:

```text
https://github.com/haxtheweb/webcomponents/tree/master/elements
```

Release updates:

```bash
npm run refresh:docs
git add .
git commit -m "Refresh HAX plugin docs"
git push
```

Users can then run:

```text
/plugin update hax
```

---

# Validate

```bash
claude plugin validate .
```
