# Mailopoly MCP plugin

Mailopoly connects all your accounts at once — Gmail, Outlook, Yahoo, iCloud
and any IMAP mailbox — and gives your AI assistant every one of them through a
single connection. With business channels added to your plan, that connection
also covers your Slack, Teams, WhatsApp,
Instagram, Messenger, TikTok and X messages too. Search across all your accounts
and channels at once, catch up on what you missed, see bills, deliveries, events
and tasks already extracted from your mail, and draft, reply or send from your
own address.

This repository is the plugin wrapper for Mailopoly's hosted MCP server. It
contains no code: just the manifests that tell Cursor, Claude Code, Codex and
other MCP clients where the server is.

```json
{
  "mcpServers": {
    "mailopoly": {
      "type": "http",
      "url": "https://fastapi.prod.aws.mailopoly.com/mcp-server/"
    }
  }
}
```

## Requirements

- A Mailopoly account with at least one connected mailbox. Sign up at
  [mailopoly.com](https://www.mailopoly.com) — free trial, no card needed.
- An MCP client that supports remote HTTP servers with OAuth.

## Install

**Cursor** — install *Mailopoly* from the Marketplace, or add the snippet above
to `~/.cursor/mcp.json` (every project) or `.cursor/mcp.json` (one project).
Cursor discovers the OAuth settings from the server; no headers or client ID
are needed.

**Claude Code** — install the plugin from this repository:

```
/plugin install mailopoly --marketplace Mailopoly/mailopoly-plugin
```

or add the server directly with
`claude mcp add --transport http mailopoly https://fastapi.prod.aws.mailopoly.com/mcp-server/`,
then `/mcp` to sign in.

**Claude.ai and ChatGPT** — search for *Mailopoly* in the connector or plugin
directory and connect from there.

**Codex, Gemini CLI, Grok, Perplexity and any other MCP client** — add the
snippet above as a remote (streamable HTTP) server.

Step-by-step guides for each client are at
[mailopoly.com/connect](https://www.mailopoly.com/connect/).

## Permissions

The first connection opens a Mailopoly sign-in in your browser. You choose what
the assistant may do:

- **Reading** — search, summaries, catch-ups, bills, events and tasks across email and connected messaging channels.
- **Making changes** — drafts, labels, folders, tasks, reminders and lists.
- **Sending** — send mail from any connected address or your @mly.life address, and reply on connected business channels.

Each permission is separate, enforced by the server on every request, and can
be revoked at any time from your Mailopoly account under Settings → Security.
Your assistant never sees a mailbox password.

## Links

- Server documentation: https://www.mailopoly.com/mcp/
- Connect guides: https://www.mailopoly.com/connect/
- Security: https://www.mailopoly.com/security/ai-email-access/
- Privacy policy: https://www.mailopoly.com/privacy/
- Terms of service: https://www.mailopoly.com/terms/
- Support: https://www.mailopoly.com/support/ · support@mailopoly.com

## License

MIT — see [LICENSE](LICENSE). The licence covers this wrapper; use of the
Mailopoly service is governed by its terms of service.
