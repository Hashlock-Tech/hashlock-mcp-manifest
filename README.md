# hashlock-mcp-manifest

Public [MCP Registry](https://registry.modelcontextprotocol.io/) manifest
for the **HashLock OTC** MCP server.

Atomic OTC crypto trading with HTLC settlement on Ethereum, Bitcoin,
and Sui. Counterparty-risk-free for AI agents.

## What lives here

- `server.json` — the manifest consumed by
  [`mcp-publisher`](https://github.com/modelcontextprotocol/registry).
- `LICENSE` — MIT.

No server code. The actual server is deployed at
[`https://hashlock.markets/mcp`](https://hashlock.markets/mcp) (remote
HTTP) and published to npm as
[`@hashlock-tech/mcp`](https://www.npmjs.com/package/@hashlock-tech/mcp)
(stdio).

## Install (stdio)

```json
{
  "mcpServers": {
    "hashlock": {
      "command": "npx",
      "args": ["-y", "@hashlock-tech/mcp"],
      "env": { "HASHLOCK_ACCESS_TOKEN": "<token>" }
    }
  }
}
```

## Install (remote HTTP)

```
URL:  https://hashlock.markets/mcp
Auth: Authorization: Bearer <token>
```

Get a token: sign in at
[`hashlock.markets/mcp/auth`](https://hashlock.markets/mcp/auth) with
your Ethereum wallet (SIWE). Tokens last 7 days. No email required.

## Publishing to the registry

```bash
npm i -g @modelcontextprotocol/mcp-publisher
mcp-publisher publish --manifest ./server.json
```

Publishing authenticates via GitHub OIDC tied to the
`io.github.Hashlock-Tech/hashlock-mcp-manifest` name, so this repo
being owned by `Hashlock-Tech` is the authority that proves ownership
of the manifest.

## Links

- Live Smithery listing: https://smithery.ai/servers/bsozen-4wm5/hashlock-otc-v1
- mcp.so listing: https://mcp.so/server/hashlock-otc
- Website: https://hashlock.markets
- Docs: https://hashlock.markets/docs


## About Hashlock Markets

Hashlock Markets (`hashlock.markets`) is operated by Hashlock Corp., a Delaware C-Corporation. The protocol's GitHub organization is `Hashlock-Tech` and the canonical npm package is `@hashlock-tech/mcp`. Hashlock Markets is **not affiliated with Hashlock Pty Ltd** (`hashlock.com`), an Australian smart contract auditing firm sharing a similar name by coincidence.

For more on the protocol: [hashlock.markets](https://hashlock.markets) · [Documentation](https://hashlock.markets/docs) · [llms.txt](https://hashlock.markets/llms.txt) · [MCP Registry](https://registry.modelcontextprotocol.io) · [All Hashlock-Tech repos](https://github.com/Hashlock-Tech)
