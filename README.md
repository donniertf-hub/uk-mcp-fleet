# UK public data for agents

Ten specialist sources, each with a free sample and a one-time pack for £0.49. Built for agents, not dashboards.

## Products

| Product | What you get | Page | Buy |
|---------|----------------|------|-----|
| Companies House | Company profile, officers, and filings | https://uk-ch-mcp.donniertf.workers.dev | that page plus /buy — https://uk-ch-mcp.donniertf.workers.dev/buy |
| Land Registry | Sold prices and area comparisons | https://uk-lr-mcp.donniertf.workers.dev | that page plus /buy — https://uk-lr-mcp.donniertf.workers.dev/buy |
| Planning | Planning applications and decisions | https://uk-planning-mcp.donniertf.workers.dev | that page plus /buy — https://uk-planning-mcp.donniertf.workers.dev/buy |
| Tenders | Live public-sector notices | https://uk-tenders-mcp.donniertf.workers.dev | that page plus /buy — https://uk-tenders-mcp.donniertf.workers.dev/buy |
| Places | Nearby amenities and local context | https://uk-places-mcp.donniertf.workers.dev | that page plus /buy — https://uk-places-mcp.donniertf.workers.dev/buy |
| Flood | Flood risk for a postcode | https://uk-flood-mcp.donniertf.workers.dev | that page plus /buy — https://uk-flood-mcp.donniertf.workers.dev/buy |
| Crime | Local crime figures | https://uk-crime-mcp.donniertf.workers.dev | that page plus /buy — https://uk-crime-mcp.donniertf.workers.dev/buy |
| Food hygiene | Food hygiene ratings | https://uk-hygiene-mcp.donniertf.workers.dev | that page plus /buy — https://uk-hygiene-mcp.donniertf.workers.dev/buy |
| EPC | Energy performance certificates | https://uk-epc-mcp.donniertf.workers.dev | that page plus /buy — https://uk-epc-mcp.donniertf.workers.dev/buy |
| CQC | Care provider ratings | https://uk-cqc-mcp.donniertf.workers.dev | that page plus /buy — https://uk-cqc-mcp.donniertf.workers.dev/buy |

Places is also listed on [Smithery](https://smithery.ai/servers/donniertf/uk-places).

## Price

Each pack is £0.49, paid once through Stripe Checkout. There is no subscription. A free sample is on every product page. The buy link is that page plus `/buy`.

## Free and paid

| Capability | Free sample | Paid pack |
|------------|-------------|-----------|
| See the tools | Yes | Yes |
| Small sample | Yes | Yes |
| Full structured result | Limited | Yes |
| Larger result set | No | Yes |
| Ready-to-use JSON | Limited | Yes |

## Connect

Point an MCP client at each product’s `/mcp` address:

```json
{
  "mcpServers": {
    "uk-companies-house": { "url": "https://uk-ch-mcp.donniertf.workers.dev/mcp" },
    "uk-land-registry": { "url": "https://uk-lr-mcp.donniertf.workers.dev/mcp" },
    "uk-planning": { "url": "https://uk-planning-mcp.donniertf.workers.dev/mcp" },
    "uk-tenders": { "url": "https://uk-tenders-mcp.donniertf.workers.dev/mcp" },
    "uk-places": { "url": "https://uk-places-mcp.donniertf.workers.dev/mcp" },
    "uk-flood": { "url": "https://uk-flood-mcp.donniertf.workers.dev/mcp" },
    "uk-crime": { "url": "https://uk-crime-mcp.donniertf.workers.dev/mcp" },
    "uk-food-hygiene": { "url": "https://uk-hygiene-mcp.donniertf.workers.dev/mcp" },
    "uk-epc": { "url": "https://uk-epc-mcp.donniertf.workers.dev/mcp" },
    "uk-cqc": { "url": "https://uk-cqc-mcp.donniertf.workers.dev/mcp" }
  }
}
```

Connecting is free. A pack that needs payment returns a checkout link.

## Example asks

**Companies House.** Get a structured company pack for company number `00000006`.

**Land Registry.** Compare sold prices around postcode `M1`. England and Wales residential sales only.

**Planning.** Show recent planning applications for Doncaster.

**Tenders.** Find UK public-sector notices for IT support, with buyer and deadline.

**Places.** List nearby shops, cafes, and pubs for postcode `SW1A 1AA`.

**Flood, crime, food hygiene, EPC, CQC.** Look up the matching public record for a postcode or provider, then buy the pack if you need the full result.

## Sources

| Product | Source | Notes |
|---------|--------|-------|
| Companies House | companieshouse.gov.uk | Open Government Licence. Not the official register. Check important facts there. |
| Land Registry | HM Land Registry Price Paid | Open Government Licence. Not the register of title and not a valuation. England and Wales residential only. |
| Planning | planning.data.gov.uk | Open Government Licence. Coverage varies. Check the local authority. |
| Tenders | Contracts Finder | Open Government Licence. Confirm deadlines on the official site. |
| Places | OpenStreetMap | Open Database Licence. |
| Flood | UK flood open data | Check the official flood service for a decision. |
| Crime | data.police.uk | Open data. Not a safety assessment. |
| Food hygiene | Food Standards Agency | Ratings can change. Check the FSA. |
| EPC | Energy performance open data | Not a survey. |
| CQC | Care Quality Commission | Not the official register. Check CQC. |
