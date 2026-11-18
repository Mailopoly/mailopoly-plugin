# Changelog

## 1.0.2 — 2026-11-18

- `.mcp.json` in this repository no longer carries `"auth": "oauth"`: the
  Claude plugin directory accepts only its listed server fields. The server
  definition is otherwise unchanged, and Claude Code, Cursor and Codex sign in
  as before.
- OpenClaw: the package published on ClawHub keeps `"auth": "oauth"` in its
  own `.mcp.json`, so **Accounts → Connect** works as in 1.0.1.

## 1.0.1 — 2026-11-10

- OpenClaw: the server is now declared with `"auth": "oauth"`, so the plugin
  page shows **Accounts → Connect** and sign-in happens in the browser while
  OpenClaw keeps running. In 1.0.0 the server had no sign-in path in OpenClaw:
  `openclaw mcp login` cannot see servers that come from a plugin, and is
  refused while the Gateway runs.
- New `connect-mailopoly` skill, so an assistant with no Mailopoly tools yet
  can tell the user the exact sign-in steps for its app.
- README: OpenClaw install section.

## 1.0.0 — 2026-10-19

- Initial release: plugin manifests for Cursor, Claude Code and Codex pointing
  at the hosted Mailopoly MCP server.
