# GrowFast plugins for Claude Code

> GrowFast is a B2B lead-finding and cold-outreach service built for AI agents to operate over MCP and REST: the agent scans a product's domain, finds matching companies with an MX-checked contact address, drafts the emails and, when told to, sends them with follow-ups; the human owner approves and audits.

## At a glance

- **What it is**: GrowFast is a B2B lead-finding and cold-outreach service built for AI agents to operate over MCP and REST. This repository connects Claude Code (and Claude) to the GrowFast MCP server.
- **Who it is for**: AI agents that find customers for a person or company; B2B SaaS founders, small sales teams and agencies who assign that work to an agent and approve it; individuals and small businesses who ask an assistant who their customers could be.
- **What it does not do**: promise leads, replies or meetings; guess email addresses; reach channels other than email (plus Reddit drafts you post yourself). The plugin connects the Claude surface, which only researches and drafts: it cannot send email or post to Reddit.
- **Price**: 3 domain scans a day are free, with no sending. Sending needs a paid plan (from $49/month: 250 outreach emails and 1,000 domain scans a month) or a credit pack (from $29 for 750 emails, one-time, no subscription). Current prices: https://growfast.sh/pricing.md
- **Integrations**: AISend (email delivery), your own Reddit account, Google sign-in, MCP clients over OAuth 2.1 or an API key.
- **Security basics**: API keys are stored hashed and revocable in Settings > API keys; OAuth shows a consent screen and its key expires after 90 days by default; every email carries your postal address and a one-click unsubscribe link.
- **MCP server**: `https://growfast.sh/api/mcp`; Official MCP Registry name `sh.growfast/growfast`.

## Connect in 60 seconds

```text
/plugin marketplace add airdropfi/growfast-claude-plugin
/plugin install growfast@growfast-plugins
/reload-plugins
```
Then open `/mcp`, choose `growfast` and Authenticate (OAuth in your browser, no key to paste).

You need a GrowFast account (https://growfast.sh/sign-up). When you approve, GrowFast shows a consent screen naming the app and what it may do, and creates a revocable API key.

## Example prompts

You tag the work and review the result.

- Assign to GrowFast: scan mynewsletter.com and tell me which kinds of companies would pay for it, with the 5 best fits and why each scored what it did. Show me what you did so I can review it.
- Assign to GrowFast: scan mybakery-supplies.com, then draft first emails to the top 3 companies. Don't send anything. Show me each draft and the page the address was read from so I can approve.
- Assign to GrowFast: listen on Reddit for people who need a tool like mynewsletter.com (keywords: newsletter tool, grow newsletter, find subscribers). Don't post anything; show me the matches with drafted replies and I will choose.
- Assign to GrowFast: for clientsite.com scan the domain, then draft first emails to the 5 best-fit companies, addressed to the named decision-maker where the site names one. Summarise what you did and wait for my approval before anything else.

## Links

- Site: https://growfast.sh
- MCP page, install for every client: https://growfast.sh/mcp
- Agent quickstart (discovery, auth, limits, error codes, human oversight): https://growfast.sh/agents
- MCP server card: https://growfast.sh/.well-known/mcp/server-card.json
- llms.txt: https://growfast.sh/llms.txt
- Privacy: https://growfast.sh/legal/privacy · Terms: https://growfast.sh/legal/terms

---

A Claude Code plugin marketplace with one plugin, [`growfast`](plugins/growfast/README.md): scan a product site for ideal customers, draft first emails to named decision-makers and set up Reddit listening on your GrowFast account. Drafts only; nothing is sent or posted.

## Install

```text
/plugin marketplace add airdropfi/growfast-claude-plugin
/plugin install growfast@growfast-plugins
```

You need a GrowFast account (https://growfast.sh) and Claude Code. From a shell: `claude plugin marketplace add airdropfi/growfast-claude-plugin` then `claude plugin install growfast@growfast-plugins`.

Then `/reload-plugins`, open `/mcp`, choose `growfast` and Authenticate (OAuth sign-in in your browser; no key to paste). Details are in [plugins/growfast/README.md](plugins/growfast/README.md).

## Layout

```text
.claude-plugin/marketplace.json     marketplace "growfast-plugins", lists the plugin
plugins/growfast/
  .claude-plugin/plugin.json        manifest
  .mcp.json                         remote MCP server https://growfast.sh/api/mcp/claude (OAuth)
  skills/                           find-customers, listen-on-reddit
  commands/                         /growfast:scan, /growfast:reddit
  README.md, LICENSE, assets/icon.png
scripts/validate.mjs                schema checks, no dependencies
LICENSE                             MIT
```

## Validate

```bash
node scripts/validate.mjs            # exit 1 on errors
node scripts/validate.mjs --strict   # warnings fail too
node scripts/validate.mjs --cli      # also runs `claude plugin validate --strict` when the claude CLI is installed
```

## Keeping it honest

- The skills name only tools that exist on the GrowFast MCP server surface this plugin connects.
- No outcome or earnings claims; nothing is sent or posted from the agent.

## License

MIT, see [LICENSE](LICENSE).
