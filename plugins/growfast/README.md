# GrowFast for Claude Code

Find B2B customers for your product from Claude Code with your own [GrowFast](https://growfast.sh) account: scan a site for ideal customers, draft first emails to named decision-makers and set up Reddit listening. Nothing is sent or posted: you do that from growfast.sh.

## Install

```text
/plugin marketplace add airdropfi/growfast-claude-plugin
/plugin install growfast@growfast-plugins
```

Then `/reload-plugins`, open `/mcp`, choose `growfast` and Authenticate (OAuth sign-in in your browser; no key to paste). You need a GrowFast account; your plan's limits apply.

## What is inside

- MCP server `growfast` at `https://growfast.sh/api/mcp/claude`: the directory surface of the GrowFast server. It has five tools: `scan_domain`, `draft_outreach_emails`, `list_reddit_monitors`, `set_reddit_monitor`, `list_reddit_matches`. No tool on this surface sends email or posts to Reddit.
- Commands: `/growfast:scan <domain>`, `/growfast:reddit <domain>`.
- Skills: `find-customers`, `listen-on-reddit`.

## Things to know

- `scan_domain` takes about 30 seconds and saves the scan to your account.
- `draft_outreach_emails` takes up to 10 companies and nothing is sent or saved.
- `set_reddit_monitor` takes up to 6 keywords and replaces that product's earlier monitor settings.
- Drafts are starting points; read them and the Reddit thread before you send or post anything. No result is promised.
- Want the full server (outreach history, autopilot, replies)? Add `https://growfast.sh/api/mcp` yourself; those extra tools can send real email and are not part of this plugin.

Support: support@growfast.sh. Docs: https://growfast.sh/docs. [Privacy](https://growfast.sh/legal/privacy), [terms](https://growfast.sh/legal/terms).

MIT, see [LICENSE](LICENSE).
