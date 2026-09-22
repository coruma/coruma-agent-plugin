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

### Grok Bot

After Coruma is available in the Grok Bot marketplace:

1. Open **Plugins** in the Grok Bot sidebar. On mobile, open your avatar menu and select **Plugins**.
2. Search for **Coruma Health Data** and select **Add**.
3. Choose **Authorize** or **Authenticate** and complete the Coruma sign-in and consent flow in your browser.
4. Return to Grok Bot and confirm that Coruma appears under **Marketplace → Yours → Installed**.

If Grok Bot shows **Waiting for authorization**, choose **Reopen** and finish the authorization in the browser. Team administrators may need to allow Coruma before members can install it.

Installing directly from a Git repository is not the Grok Bot installation flow. See the official [Grok Bot plugin guide](https://cursor.com/help/grok-bot/connect-plugins).

### Cursor local development

For local development before the marketplace listing is available, clone this repository into Cursor's local plugin directory and reload Cursor:

```text
~/.cursor/plugins/local/coruma-agent-plugin
```

### Grok Build

Grok Build is the terminal coding agent and uses a separate CLI installation flow. Install Coruma directly from this public repository:

```bash
grok plugin install coruma/coruma-agent-plugin --trust
```

Review the repository before using `--trust`. After installation, open `/plugins` or start a new Grok Build session so the plugin is loaded. See the official [Grok Build plugins and marketplaces documentation](https://docs.x.ai/build/features/skills-plugins-marketplaces).

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
