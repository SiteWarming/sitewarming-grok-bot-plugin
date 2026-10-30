# SiteWarming for Grok Bot and Cursor

SiteWarming turns parked domains into live, content-rich sites that build search trust over time. With this plugin, domain investors and portfolio owners can manage their SiteWarming portfolio in plain language from Grok Bot or Cursor.

Read: list and search your domains, open a full report on any domain (DNS and SSL health, content schedule, warming progress, valuation) and see a portfolio summary.

Act: launch one domain or up to 20 at once through a guided setup, build a Domain Brief through a short interview, add tracked domains, update settings on live domains and connect DNS through supported registrar integrations.

Safety and limits: actions that change live sites, DNS or your portfolio are marked as write actions, and your AI assistant may ask for your confirmation before running them. Removing a domain from SiteWarming never releases or transfers it at your registrar, and registrar transfers are not possible through this plugin. You sign in with your own SiteWarming account, and the plugin can only see and change what that account can.

Requires a SiteWarming account.

## Connect

This plugin connects to SiteWarming's hosted MCP server:

```
https://mcp.sitewarming.com
```

When you first use it, a SiteWarming sign-in page opens. Sign in with your SiteWarming account and click **Allow**. The connector can only see and change what your account can. Access tokens last 7 days.

**Cursor (manual setup):** add this to `.cursor/mcp.json` or your user MCP settings:

```json
{
  "mcpServers": {
    "sitewarming": { "url": "https://mcp.sitewarming.com" }
  }
}
```

## Tools

27 tools. 13 only read data; the other 14 change something and are labelled as write actions (`readOnlyHint` / `destructiveHint` / `openWorldHint` are set on every tool).

| Area | Tools |
|---|---|
| Portfolio | `list_domains`, `search`, `fetch`, `get_domain_report`, `get_portfolio_summary`, `get_warming_status` |
| Launch | `prepare_domain_launch`, `launch_domain`, `check_launch_status`, `prepare_bulk_launch`, `bulk_launch_domains` |
| Domain Brief | `get_domain_interview_questions`, `get_domain_interview_status`, `save_domain_interview`, `draft_domain_content`, `draft_brief_section`, `assemble_domain_brief`, `submit_domain_brief` |
| Manage | `update_domain`, `bulk_update_domains`, `delete_domain`, `convert_to_tracked` |
| Tracked domains | `add_tracked_domain`, `bulk_add_tracked_domains`, `check_tracked_verification` |
| DNS | `detect_dns_integration`, `configure_dns` |

## Example prompts

- "Summarize my SiteWarming portfolio."
- "List all my domains and their status."
- "Show the full report for example.com."
- "What's the warming status of my domains?"
- "Do I have a DNS integration connected for example.com?"

## Privacy and support

- Privacy policy: https://www.sitewarming.com/privacy
- Terms: https://www.sitewarming.com/terms
- Documentation: https://www.sitewarming.com/mcp
- Support: support@sitewarming.com · https://www.sitewarming.com/contact

This repository contains only the plugin manifest and documentation. The MCP server is a hosted service operated by SiteWarming; its source code is not part of this repository.

## License

The files in this repository are released under the MIT License (see `LICENSE`). The SiteWarming service itself is governed by the SiteWarming Terms of Service.
