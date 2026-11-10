---
name: connect-mailopoly
description: Sign in to Mailopoly so its email tools work. Use when the user asks to connect, sign in to, log in to, set up or finish installing Mailopoly, or asks about their email, inbox, tasks, bills or messages and no Mailopoly tools are available yet.
---

# Connect Mailopoly

The Mailopoly plugin is installed, but its tools only appear after the user
signs in to their Mailopoly account once. If you have no Mailopoly tools
(names containing `mailopoly`, such as `get_feed` or `search_emails`), the
sign-in has not happened yet. You cannot do it for the user: it is a browser
sign-in. Give them the steps for the app they are using, then wait.

## OpenClaw

Tell the user exactly this:

1. Open **Plugins** in OpenClaw and select **Mailopoly**.
2. Under **Accounts**, choose **Connect**.
3. Sign in to Mailopoly in the browser tab that opens and choose what the
   assistant may do (reading, making changes, sending).
4. Come back to OpenClaw and send a new message. The Mailopoly tools are
   available from that message on.

Rules for OpenClaw:

- OpenClaw keeps running the whole time. Never tell the user to quit the
  app or stop the Gateway.
- Do not run or suggest `openclaw mcp login`, `openclaw mcp add` or
  `openclaw mcp set`, and do not edit `openclaw.json`. Those commands are
  refused while OpenClaw is running, and the plugin already declares the
  server.
- If the Mailopoly page shows **Connected** but the tools are still missing,
  ask the user to start a new chat.
- If there is no **Accounts** section, the installed plugin is older than
  1.0.1: ask the user to update the Mailopoly plugin from the Plugins page.

## Claude Code

Run `/mcp`, select **mailopoly** and choose **Authenticate**.

## Cursor and Codex

Open the app's MCP settings, find **mailopoly** and choose **Sign in** (or
**Login**).

## After sign-in

Call `identify_agent` once with your assistant name and platform, then offer
one concrete next step, such as catching the user up on their inbox.

No Mailopoly account yet? Sign up at https://www.mailopoly.com (free trial,
no card needed), connect a mailbox, then follow the steps above.
