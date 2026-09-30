# UK MCP Fleet — product cheat sheet

Soft-Offer **OFF**. Full names: Companies House, Land Registry.

| Product | Base | Outcome line | Discover peek |
|---------|------|--------------|---------------|
| Companies House | https://uk-ch-mcp.donniertf.workers.dev | Get a structured KYB pack for this company. | `/v1/discover/new-cos?area=Glasgow` |
| Land Registry | https://uk-lr-mcp.donniertf.workers.dev | Compare sold prices around this postcode. | `/v1/discover/price-paid?area=M1` |
| Planning | https://uk-planning-mcp.donniertf.workers.dev | Retrieve relevant planning applications and decision details. | `/v1/discover/planning?lpaOrPostcode=Doncaster` |
| Tenders | https://uk-tenders-mcp.donniertf.workers.dev | Return matching tenders with buyer, deadline and category. | `/v1/discover/tenders?query=construction` |
| Places | https://uk-places-mcp.donniertf.workers.dev | Map nearby amenities and local context for this postcode. | `/v1/discover/local-amenities?postcode=M1` |

MCP (all): `POST https://{worker}.donniertf.workers.dev/mcp`

Price: £0.49 smoke; pro tiers dormant.
