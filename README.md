# @sero-ai/plugin-daily-quote

Daily inspirational quote app for Sero — AI-generated wisdom each day.

## Sero Plugin Install

Install in **Sero → Admin → Plugins** with:

```text
git:https://github.com/monobyte/sero-daily-quote-plugin.git
```

Sero clones the source repo, installs its dependencies locally, builds the UI,
and then hot-loads the plugin into the sidebar.

## Pi CLI Usage

Install as a Pi package:

```bash
pi install npm:@sero-ai/plugin-daily-quote
```

The agent gains a `daily_quote` tool (get, set) and a `/quote` command.
Use `/quote` to display today's quote or generate a fresh one if none
exists yet.

## Sero Usage

When loaded in Sero, the web UI mounts in the main app area and displays
the current quote. Tap the refresh button to ask the agent for a new one.
Changes from the agent or the UI are reflected instantly in both
directions.

## State File

This is a global-scoped app. State lives under the Sero home directory:

```
~/.sero-ui/
└── apps/
    └── daily-quote/
        └── state.json
```

When running under the Pi CLI (no `SERO_HOME`), state falls back to a
workspace-relative path:

```
workspace-root/
└── .sero/
    └── apps/
        └── daily-quote/
            └── state.json
```

```json
{
  "quote": {
    "text": "The only way to do great work is to love what you do.",
    "author": "Steve Jobs",
    "generatedAt": "2025-01-01T12:00:00.000Z"
  },
  "lastRefreshDate": "2025-01-01"
}
```
