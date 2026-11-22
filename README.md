![Multitool](assets/icon.png)

# Multitool Ads — MCP server for Meta Ads

Connect Claude, ChatGPT, Codex, Cursor, VS Code, Gemini CLI, Antigravity, OpenCode or any MCP client
to all your Meta ad accounts.

[![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=multitool&config=eyJ1cmwiOiJodHRwczovL21jcC5tdWx0aXRvb2xzLnByby9tY3AifQ%3D%3D)
[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_server-0098FF?style=for-the-badge)](https://vscode.dev/redirect/mcp/install?name=multitool&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.multitools.pro%2Fmcp%22%7D)
[![Add to Claude](https://img.shields.io/badge/Claude-Add_connector-D97757?style=for-the-badge&logo=claude&logoColor=white)](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Multitool%20Ads&connectorUrl=https%3A%2F%2Fmcp.multitools.pro%2Fmcp)

[Русская версия](README.ru.md)

---

Ask about spend and results in plain language, find what is not delivering, rank campaigns and
creatives, and pause, resume or change budgets — every change is previewed and sent to Meta only
after you confirm it.

| | |
|---|---|
| **Server URL** | `https://mcp.multitools.pro/mcp` |
| **Transport** | Streamable HTTP |
| **Sign-in** | OAuth with your Multitool account — no API keys |
| **You need** | A [Multitool](https://multitools.pro) account with your Facebook profiles connected |

Every install below ends the same way: a browser window opens Multitool — **sign in, choose a
workspace, click Allow**.

## Install

- [Cursor](#cursor) · [VS Code](#vs-code) · [Claude (web and desktop)](#claude-web-and-desktop) · [ChatGPT](#chatgpt)
- [Claude Code](#claude-code) · [Codex](#codex) · [Gemini CLI](#gemini-cli) · [OpenCode](#opencode)
- [Antigravity](#antigravity) · [Windsurf and other clients](#windsurf-and-other-clients)
- [Let your AI agent install it](#let-your-ai-agent-install-it)

### Cursor

Click **Add to Cursor** at the top of this page, then **Install**. Open **Customize** in the sidebar
and sign in to `multitool` when Cursor asks.

### VS Code

Click **Install in VS Code** at the top of this page, then **Install**. VS Code opens the sign-in
page the first time it connects. Requires GitHub Copilot in agent mode.

### Claude (web and desktop)

Click **Add to Claude** at the top of this page, then **Add** and **Connect**.

By hand: **Customize → Connectors → Add custom connector**, name `Multitool Ads`, URL
`https://mcp.multitools.pro/mcp`. In a chat, make sure **Multitool Ads** is on under **+ → Connectors**.

### ChatGPT

Open [chatgpt.com/plugins](https://chatgpt.com/plugins), click **+**, then **Add custom MCP server**.
Name `Multitool Ads`, URL `https://mcp.multitools.pro/mcp`, confirm the warning, create it and sign in.

### Claude Code

```shell
claude mcp add --transport http --scope user multitool https://mcp.multitools.pro/mcp
```

```shell
claude mcp login multitool
```

As a plugin instead: run `/plugin marketplace add multitool-ads/mcp`, then
`/plugin install multitool@multitool-ads`, then sign in from `/mcp`.

### Codex

```shell
codex mcp add multitool --url https://mcp.multitools.pro/mcp
```

Codex opens the sign-in page right away. If it does not, run `codex mcp login multitool`.

As a plugin instead (Codex and the ChatGPT desktop app): `codex plugin marketplace add multitool-ads/mcp`,
then `codex plugin add multitool@multitool-ads`.

### Gemini CLI

```shell
gemini extensions install https://github.com/multitool-ads/mcp
```

Start `gemini`; if the browser does not open by itself, run `/mcp auth multitool`.

Without the extension: `gemini mcp add --scope user --transport http multitool https://mcp.multitools.pro/mcp`

### OpenCode

```shell
opencode mcp add multitool --global --url https://mcp.multitools.pro/mcp
```

```shell
opencode mcp auth multitool
```

### Antigravity

**Antigravity CLI** — one command, then sign in from `/mcp` inside `agy`:

```shell
agy mcp add multitool https://mcp.multitools.pro/mcp
```

As a plugin instead: `agy plugin install https://github.com/multitool-ads/mcp`

**Antigravity IDE and the Antigravity App** — add the server, then press **Authenticate**:

1. Add the server to `~/.gemini/config/mcp_config.json`, or paste the prompt below into the agent.
   In the IDE the file opens from `Ctrl+Shift+P` → **Manage MCP Servers** → **View raw config**:
   ```json
   {
     "mcpServers": {
       "multitool": { "serverUrl": "https://mcp.multitools.pro/mcp" }
     }
   }
   ```
   Keep any servers that are already in the file.
2. Open the server list:
   - **IDE:** press `Ctrl+Shift+P` (`Cmd+Shift+P` on Mac) and run **Manage MCP Servers**.
   - **App:** **Customizations → Installed → MCP Servers**.
3. Click **Authenticate** next to `multitool` and sign in to Multitool in the browser.
4. The browser shows an authorization code. Copy it, paste it into **Enter authorization code** in
   Antigravity and click **Submit**.

Prompt for the Antigravity agent:

```text
Add an MCP server to my Antigravity config. Open the file ~/.gemini/config/mcp_config.json (create it if it does not exist) and add this entry inside "mcpServers", keeping every existing entry unchanged:
"multitool": { "serverUrl": "https://mcp.multitools.pro/mcp" }
Save the file and check that it is valid JSON. Then tell me exactly this: "Press Ctrl+Shift+P (Cmd+Shift+P on Mac), run Manage MCP Servers, click Authenticate next to multitool, sign in, then copy the code from the browser into Enter authorization code and click Submit." Do not do anything else and do not ask me for an API key: there is none.
```

### Windsurf and other clients

Any client that supports remote MCP servers with OAuth works. Add a server with the URL
`https://mcp.multitools.pro/mcp` (transport: Streamable HTTP) and sign in when the client asks.
The client registers itself automatically; there is no client ID or API key to copy.

Most clients use this JSON:

```json
{
  "mcpServers": {
    "multitool": { "url": "https://mcp.multitools.pro/mcp" }
  }
}
```

Windsurf uses `serverUrl` instead of `url` in `~/.codeium/windsurf/mcp_config.json`.

### Let your AI agent install it

If you would rather not type anything, paste this into the agent chat of the app you use. It is
written so that even a small model follows it step by step.

```text
Install the Multitool Ads MCP server for me. Server URL: https://mcp.multitools.pro/mcp (Streamable HTTP, sign-in with OAuth, no API key). Do only the step for the app you are running in:
- Claude Code: run `claude mcp add --transport http --scope user multitool https://mcp.multitools.pro/mcp`, then tell me to run `claude mcp login multitool`.
- Codex: run `codex mcp add multitool --url https://mcp.multitools.pro/mcp`; it opens the sign-in page itself. If it does not, tell me to run `codex mcp login multitool`.
- Gemini CLI: run `gemini mcp add --scope user --transport http multitool https://mcp.multitools.pro/mcp`, then tell me to restart Gemini CLI and run `/mcp auth multitool`.
- OpenCode: run `opencode mcp add multitool --global --url https://mcp.multitools.pro/mcp`, then tell me to run `opencode mcp auth multitool`.
- Antigravity: add "multitool": { "serverUrl": "https://mcp.multitools.pro/mcp" } inside "mcpServers" in ~/.gemini/config/mcp_config.json, keeping existing entries; then tell me to press Ctrl+Shift+P, run Manage MCP Servers, click Authenticate next to multitool and paste the code from the browser.
- Cursor: add "multitool": { "url": "https://mcp.multitools.pro/mcp" } inside "mcpServers" in ~/.cursor/mcp.json, keeping existing entries; then tell me to open Customize and sign in to multitool.
- Windsurf: add "multitool": { "serverUrl": "https://mcp.multitools.pro/mcp" } inside "mcpServers" in ~/.codeium/windsurf/mcp_config.json, keeping existing entries; then tell me to refresh the MCP servers and sign in.
After that, stop. Do not invent other steps.
```

## What you can ask

- "Show today's spend and results across all my ad accounts"
- "Which campaigns spent more than $50 today with no results?"
- "Why is this ad set not delivering?"
- "Rank my creatives by cost per result over the last 7 days"
- "Pause every ad in campaign X" — the agent shows a preview first and waits for your confirmation

## Safe by design

- **Your access, nothing more.** Multitool only sees the ad accounts your connected Facebook
  profiles can access, and you choose which workspace the client may use when you sign in.
- **Preview before every change.** Pausing, resuming, budgets, names and creatives are previewed
  first; nothing is sent to Meta until you confirm.
- **Disconnect any time** in Multitool under **Settings → AI connections**, or sign out of the
  server in your client.

## Troubleshooting

| Symptom | What to do |
|---|---|
| The server shows *Unauthorized*, *needs authentication* or a red dot | Sign-in was not finished. Use the sign-in step for your app above: Authenticate, `/mcp`, `mcp login` or `mcp auth`. |
| No Multitool tools in the chat after signing in | Start a new chat or reload the window; some clients load tools only at the start of a conversation. |
| The browser says there is no workspace | Create a workspace at [multitools.pro](https://multitools.pro) and connect a Facebook profile first. |
| Numbers look empty for a period | Ask the agent whether the data is synced; it reports freshness instead of showing zeros. |

## About

Multitool is an operational Meta Ads manager for media buyers and agencies who run many ad accounts
and Facebook profiles. Website: [multitools.pro](https://multitools.pro) · Support:
[support@multitools.pro](mailto:support@multitools.pro) ·
[Privacy Policy](https://multitools.pro/privacy) · [Terms of Service](https://multitools.pro/terms)

This repository contains the client configuration (plugins and manifests) for the hosted server. It
is released under the [MIT License](LICENSE).
