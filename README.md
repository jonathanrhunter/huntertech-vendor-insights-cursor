# Huntertech.io

Professional infrastructure monitoring tools and business solutions for Zscaler networks.

## Huntertech Vendor Insights Cursor Plugin

Huntertech Vendor Insights is a hosted MCP server for public infrastructure incident status across monitored SaaS, cloud, security, developer, and infrastructure vendors. Cursor can use it to ask questions like "Is Zscaler having an outage?" or "Are any monitored vendors having issues right now?"

### What It Provides

- Public access to active ongoing and monitoring incidents.
- Vendor discovery for supported monitored vendors.
- Targeted vendor incident lookup.
- Broad incident awareness across the monitored vendor catalog.
- Optional authenticated access for plan-scoped historical incident data.

### MCP Server

The plugin connects Cursor to the hosted Huntertech MCP endpoint:

```json
{
  "mcpServers": {
    "huntertech-vendor-insights": {
      "url": "https://www.huntertech.io/api/v1/mcp"
    }
  }
}
```

### Available Tools

- `list_monitored_vendors`: Lists vendors currently monitored by Huntertech.
- `get_vendor_incidents`: Retrieves incident status for a specific vendor.
- `get_all_vendor_incidents`: Retrieves active incident status across monitored vendors.

### Authentication

Authentication is optional. Anonymous users can access public active incident data. Customers can provide an `Authorization: Bearer <token>` header from their Huntertech account to enable authenticated, plan-scoped historical access.

### Registry

The MCP server is published in the official MCP Registry as `io.huntertech/vendor-insights`.