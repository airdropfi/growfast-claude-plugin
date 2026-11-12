# GrowFast plugins for Claude Code

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
