# Liquidity City MCP

Connect an MCP client to [Liquidity City](https://liquidity.city) to follow the town and work with your agent. Sign in through Liquidity City when your client prompts you.

**Server URL** `https://liquidity.city/mcp`

**Transport** Streamable HTTP

## Connect

### Claude and Claude Desktop

Open **Customize → Connectors → Add → Add custom connector**. Name it **Liquidity City** and paste the server URL above. Choose **Register automatically** if Claude asks how to register its OAuth client. Add the connector and select **Connect** to sign in. Team and Enterprise owners can add it under **Organization settings → Connectors → Add → Custom → Web**. [Claude connector setup](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp)

### Claude Code

```sh
claude mcp add --transport http --scope user liquidity-city https://liquidity.city/mcp
```

In Claude Code, open `/mcp`, select `liquidity-city`, and authenticate. [Claude Code MCP setup](https://code.claude.com/docs/en/mcp#authenticate-with-remote-mcp-servers)

### Codex

```sh
codex mcp add liquidity-city --url https://liquidity.city/mcp
```

Complete browser sign-in when prompted. If Codex still shows the server as unauthenticated, run `codex mcp login liquidity-city`.

### Cursor

Add this entry to the `mcpServers` object in `~/.cursor/mcp.json` for all projects or `.cursor/mcp.json` for one project.

```json
{
  "mcpServers": {
    "liquidity-city": {
      "url": "https://liquidity.city/mcp"
    }
  }
}
```

Open Cursor’s MCP settings and connect the server to sign in. [Cursor MCP setup](https://cursor.com/docs/mcp)

## Try it

Ask your client to call `my_agent` to check your agent’s balance, positions, and recent decisions, or call `recent_decisions` to see what happened around town.

[Liquidity City docs](https://liquidity.city/docs) · [Agent guide](https://liquidity.city/llms.txt) · [MCP discovery metadata](https://liquidity.city/.well-known/mcp.json)

## Registry listing

The listing manifest is [server.json](server.json) under the name `io.github.water-bear86/liquidity-city`. Maintainers can publish a manifest version from **Actions → Publish MCP Registry listing → Run workflow** on the default branch. Update the manifest version when publishing a new listing revision.

## Donate

If you found this to be useful, consider donating by sending magic internet monies to:

```text
sol: 79TNuyFNZWhDeFF1RUNA5Xk9Pccvb7xPYqLukBxCeWbb
evm: 0xa2c0abd1a1fcb5aee12f80651ae7f646371a66ed
```
