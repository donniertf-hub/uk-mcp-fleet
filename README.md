# UK public data for agents

## 🆕 Subscriptions (free tier + monthly Pro, cancel anytime)

| Product | Free tool | Pro | Page / MCP |
|---|---|---|---|
| **UK Property Deal Finder** — streets selling below the district median (Land Registry sold prices) + planning + EPC refurb hints | `deal_scan` (top 3 streets) | £9/month | https://uk-property-deals-mcp.donniertf.workers.dev · `/mcp` |
| **UK Tender Alerts** — live Contracts Finder tenders matched to your keywords + region, deadlines, values, daily `new_since` | `tender_match` (top 3) | £9/month | https://uk-tender-alerts-mcp.donniertf.workers.dev · `/mcp` |
| **UK Insolvency Alerts** — Gazette winding-up petitions, liquidations, administrations; watch 50 customers/suppliers | `insolvency_check` | £15/month | https://uk-insolvency-alerts-mcp.donniertf.workers.dev · `/mcp` |
| **UK Sanctions Screening** — batch-screen names against the UK Sanctions List (FCDO/OFSI), audit-ready | `sanctions_check` | £19/month | https://uk-sanctions-screen-mcp.donniertf.workers.dev · `/mcp` |
| **UK Visa Sponsor Register** — Home Office licensed sponsors: check, town/route lead lists, new & removed, B-rated | `sponsor_check` | £15/month | https://uk-sponsor-register-mcp.donniertf.workers.dev · `/mcp` |
| **UK Fuel Price Finder** — cheapest diesel/petrol near a postcode, fleet depot reports, £ saved per fill | `cheapest_fuel` | £9/month | https://uk-fuel-prices-mcp.donniertf.workers.dev · `/mcp` |
| **UK Electricity Price Slots** — cheapest half-hour Agile prices by postcode, best N-hour window for EV/heat/batteries | `cheapest_slots` | £9/month | https://uk-energy-prices-mcp.donniertf.workers.dev · `/mcp` |
| **UK Salary Benchmarks** — ONS pay percentiles by postcode, area comparisons, offer checks | `area_salary` | £9/month | https://uk-salary-benchmarks-mcp.donniertf.workers.dev · `/mcp` |
| **UK Business Calendar** — working days, bank holidays, invoice due dates, HMRC & Companies House deadlines | `next_bank_holidays` | £9/month | https://uk-business-calendar-mcp.donniertf.workers.dev · `/mcp` |
| **UK Food Recall Alerts** — FSA recalls & allergy alerts, batch codes, stock watchlists | `latest_alerts` | £9/month | https://uk-food-alerts-mcp.donniertf.workers.dev · `/mcp` |

Subscribe at each page's `/buy`. Not a valuation; not legal or procurement advice.

### Trading data (separate)

| Product | Free tool | Pro | Page / MCP |
|---|---|---|---|
| **Crypto Perps Pulse** — funding rates, open interest, 24h movers across perpetual futures. Read-only, never trades. Not financial advice. | `market_pulse` | £19/month | https://trading-data-mcp.donniertf.workers.dev · `/mcp` |
| **Prediction Market Rule Check** — risk-score Polymarket/Kalshi settlement wording before you trade. Not financial advice. | `rule_check` | £12/month | https://prediction-rules-mcp.donniertf.workers.dev · `/mcp` |

## 💷 Bundles — one-off, no subscription

| Bundle | Packs | Price | Buy |
|---|---|---|---|
| **Property & Area Due-Diligence 5-Pack** | Land Registry sold prices, EPC, flood, crime, planning | **£1.99** (vs £2.45) | https://uk-mcp-bundles.donniertf.workers.dev |
| **All-10 Bundle** | Companies House, Land Registry, planning, tenders, places, flood, crime, food hygiene, EPC, CQC | **£3.99** (vs £4.90) | https://uk-mcp-bundles.donniertf.workers.dev |

One pass, one pack per included server, valid 90 days. Agents: `POST /checkout?bundle=area5|all10` → `GET /token?session_id=` → `Authorization: Bearer <pass>`.

## 🤖 Agent-ready buying
Every subscription server exposes `/llms.txt`, `/.well-known/mcp` (server card), `/pricing.json`, `POST /checkout` (returns a Stripe Checkout URL) and `GET /token?session_id=` (returns the access token once paid). Free tiers need no key.

## ⭐ New: UK Postcode Property Report — £2.99

**One postcode, one complete report**: Land Registry sold prices (every nearby sale, medians by property type), Environment Agency flood warning areas, 3-month crime trend, EPC ratings, food hygiene nearby, CQC care services, planning applications and the nearest schools, GPs, stations and shops. For home buyers, landlords, property investors and agents.

- Free snapshot + sample London report: https://uk-postcode-report-mcp.donniertf.workers.dev
- MCP (no login): `https://uk-postcode-report-mcp.donniertf.workers.dev/mcp` — tools `postcode_summary` (free), `buy_report_link`, `postcode_report` (£2.99 one-time, 7-day refund)
- Not a valuation, not a survey.

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
    "uk-postcode-report": { "url": "https://uk-postcode-report-mcp.donniertf.workers.dev/mcp" },
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
