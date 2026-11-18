# Page Zero plugin

Connect Codex or Claude Code to Page Zero to audit websites, check traffic and visibility, improve content, and install the SDK. The plugin includes five skills and connects to the hosted Page Zero MCP server.

## Install

Use the installer to add Page Zero to the supported coding agents on your computer:

```sh
npx plugins add sillyleo/pagezero-plugin
```

To install for one agent, add `--target codex` or `--target claude-code`. You can also use your agent's native installer below.

### Codex

```sh
codex plugin marketplace add sillyleo/pagezero-plugin
codex plugin add pagezero@pagezero
```

Open the Page Zero plugin settings in Codex and follow the prompts to sign in and authorize access. Open a new session and ask Codex to list your authorized websites.

### Claude Code

```sh
claude plugin marketplace add sillyleo/pagezero-plugin
claude plugin install pagezero@pagezero
```

Restart Claude Code and use `/mcp` to sign in to Page Zero. Ask Claude Code to list your authorized websites.

### Update an existing installation

In Codex, run `codex plugin marketplace upgrade pagezero`, then `codex plugin add pagezero@pagezero`. In Claude Code, run `claude plugin marketplace update pagezero`, then `claude plugin update pagezero@pagezero`. Restart your agent after the update.

### Switch from an older marketplace

If you installed Page Zero before the marketplace moved, remove the existing plugin and marketplace from your agent. Run the install command above again and reopen the agent. Reconnect to Page Zero if prompted.

For Codex:

```sh
codex plugin remove pagezero@pagezero
codex plugin marketplace remove pagezero
```

For Claude Code:

```sh
claude plugin uninstall pagezero@pagezero --keep-data
claude plugin marketplace remove pagezero --scope user
```

## Included skills

| Skill | What it helps you do |
| --- | --- |
| `pagezero-sdk-installation` | Install or verify the Page Zero SDK on a website. |
| `pagezero-site-audit` | Run a site audit or review existing findings. |
| `pagezero-traffic-reporting` | Read crawler, referral, and GA4 traffic data. |
| `pagezero-visibility-tracking` | Review and manage keyword and AI visibility tracking. |
| `pagezero-content-improvement` | Improve existing AEO content and check publication status. |

The plugin only sees the websites you authorize. Connecting the plugin and connecting the SDK to a website are separate steps. Running audits, generating content, and starting tracking may use your plan allowance.

## Verify the package

```sh
node --test plugins/pagezero/plugin.test.mjs
claude plugin validate plugins/pagezero --strict
claude plugin validate .claude-plugin/marketplace.json --strict
```

This GitHub repository is the installation source. See the [Codex plugin docs](https://developers.openai.com/codex/plugins) and [Claude Code plugin docs](https://code.claude.com/docs/en/plugins) for host-specific settings.
