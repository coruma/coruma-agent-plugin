# Coruma Health Data Agent Plugin

Connect AI assistants to the Apple Health data you explicitly authorize in Coruma.

Coruma exposes a remote, read-only Model Context Protocol (MCP) server for activity, workouts, sleep, heart rate, energy, body measurements, synchronization status, and optional workout GPS routes. Access is protected by OAuth and can be revoked from Coruma.

> Coruma is a personal data portability tool. It is not a medical device and does not diagnose, treat, or recommend care.

## What this plugin provides

- `coruma-health-summary`: summarize authorized records for a bounded period.
- `coruma-workout-review`: review workout history and retrieve an authorized GPS route when requested.
- `coruma-sync-status`: check devices, authorized categories, and synchronization freshness.

The plugin uses the hosted MCP endpoint at `https://api.coruma.app/mcp`. No API key or health data is stored in this repository.

## Try it

- “Summarize my Apple Health activity and workouts from the last seven days.”
- “Compare my sleep duration this week with the previous week.”
- “Check when my health data last synchronized.”
- “Show the GPS route for my latest outdoor workout.”

## Installation

### Cursor and Grok Bot

Install the plugin from its marketplace listing when available. For local development, clone this repository into Cursor's local plugin directory and reload Cursor:

```text
~/.cursor/plugins/local/coruma-agent-plugin
```

### Grok Build

Install from this repository while testing:

```bash
grok plugin install id49/coruma-agent-plugin --trust
```

### MCP clients

Clients that support remote HTTP MCP servers can connect directly to:

```text
https://api.coruma.app/mcp
```

The client opens Coruma's OAuth flow. Sign in, review the requested categories, and authorize only the data you want the assistant to read.

## Privacy and safety

- Tools are read-only and restricted to the authenticated Coruma account.
- Access is limited by the scopes selected during authorization.
- Revoking an agent in Coruma stops future access.
- An empty result applies only to the requested range and authorized categories.
- Synchronization freshness does not prove that Apple Health contains every possible record.
- The plugin must not be used for diagnosis, treatment, emergencies, or medical recommendations.

Read the [privacy notice](https://app.coruma.app/privacy) and visit [support](https://app.coruma.app/support).

## Development

All examples and tests must use synthetic data. Do not commit access tokens, credentials, `.env` files, health payloads, or screenshots containing personal data.

The MCP server implementation lives in Coruma's private application repository. This public repository contains only portable plugin metadata, workflow instructions, and discovery tests.

## License

MIT
