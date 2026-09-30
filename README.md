# UK MCP Fleet (Bossman)

**One-liner:** A UK research toolkit with five specialist MCP sources — company, title-price, planning, tenders, and local amenities — wired for agents, not five unrelated products.

Soft-Offer email is **OFF** across the fleet. Public copy always uses full names **Companies House** and **Land Registry** (never CH/LR shorthand).

## Live products

| Product | URL | Free tools | Paid packs (£0.49) | Who it’s for |
|---------|-----|------------|--------------------|--------------|
| **Companies House** | https://uk-ch-mcp.donniertf.workers.dev | `GET /tools`, `GET /health`, `POST /mcp`, `new_cos_discover` | `kyb_pack`, `new_cos_pack` | Compliance / KYB / new-company lead agents |
| **Land Registry** | https://uk-lr-mcp.donniertf.workers.dev | `GET /tools`, `GET /health`, `POST /mcp`, `price_paid_discover` | `price_paid_pack`, `area_comps_pack` | Estate agents, conveyancers, proptech |
| **Planning** | https://uk-planning-mcp.donniertf.workers.dev | `GET /tools`, `GET /health`, `POST /mcp`, `planning_discover` | `planning_pack`, `lpa_summary_pack` | Planners, surveyors, proptech |
| **Tenders** | https://uk-tenders-mcp.donniertf.workers.dev | `GET /tools`, `GET /health`, `POST /mcp`, `tenders_discover` | `tenders_pack`, `tender_score_pack` | Bid writers, B2B tender agents |
| **Places** | https://uk-places-mcp.donniertf.workers.dev | `GET /tools`, `GET /health`, `POST /mcp`, local-amenities discover | `local_amenities_pack`, `local_context_pack` | Site selection, proptech, local-context |

Directory links (where known):

- Places on Smithery: https://smithery.ai/servers/donniertf/uk-places
- MCP Collection / FindMCP: see each Worker’s README / discovery notes (TODO if not yet listed)

## Pricing

- **Smoke test:** £0.49 one-time via Stripe Checkout per pack (7–14 day learning window).
- **Pro / deep / bundle** tiers are **dormant scaffolding** — only activate after converters; never invent Stripe Price IDs.
- Soft-Offer outbound: **OFF** (no chase emails from these Workers).

## Free vs paid (capability matrix)

Same matrix on each Worker landing:

| Capability | Free discovery | Paid pack |
|------------|----------------|-----------|
| Tool/schema discovery | Yes | — |
| Small sample / metadata | Yes | — |
| Full structured result | Limited | Yes |
| Larger result set | No | Yes |
| Compound interpretation | No/limited | Yes |
| Export-ready JSON | Limited | Yes |

Paid packs include `generated_at` (ISO) and source/retrieval timing in the pack JSON where available.

## Copyable MCP config (Streamable HTTP)

Point any MCP client that supports Streamable HTTP at the Worker `/mcp` endpoint:

```json
{
  "mcpServers": {
    "uk-companies-house": {
      "url": "https://uk-ch-mcp.donniertf.workers.dev/mcp"
    },
    "uk-land-registry": {
      "url": "https://uk-lr-mcp.donniertf.workers.dev/mcp"
    },
    "uk-planning": {
      "url": "https://uk-planning-mcp.donniertf.workers.dev/mcp"
    },
    "uk-tenders": {
      "url": "https://uk-tenders-mcp.donniertf.workers.dev/mcp"
    },
    "uk-places": {
      "url": "https://uk-places-mcp.donniertf.workers.dev/mcp"
    }
  }
}
```

Handshake is free (`initialize` + `tools/list`). Pack tools that need payment return Checkout; redeem once with the Bearer token.

## One end-to-end agent prompt per product

**Companies House**

> Get a structured KYB pack for company number `00000006`. Summarise legal name, status, officers, PSC, recent filings, and any `risk_flags`. If only discovery is free, peek new companies in Glasgow first, then checkout the KYB pack.

**Land Registry**

> Compare sold prices around postcode `M1`. Return recent Price Paid sales and area comps (median/mean) with honest thin-sample flags. England & Wales residential only — say so if coverage does not apply.

**Planning**

> Retrieve relevant planning applications and decision details for Doncaster (or the LPA for postcode `DN1`). Prefer the LPA summary pack so I get `status_mix` and coverage risk flags.

**Tenders**

> Return matching UK public-sector tenders for “IT support” with buyer, deadline, and category. Prefer the scored pack so each notice has fit_score / fit_flags.

**Places**

> For postcode `M1`, list nearby amenities (shops, cafes, pubs) and a local-context density summary I can use for site selection. OSM-first; note if Google enrichment is off.

## Flagship multi-source workflow

**Company → KYB → nearby prices → planning → amenities / tenders**

1. **Companies House** — discover new cos in an area *or* KYB an existing company number → structured profile + risk flags.
2. **Land Registry** — take the trading / registered postcode → Price Paid + area comps around that outcode.
3. **Planning** — same postcode / LPA → recent applications + status mix (development risk / opportunity).
4. **Places** — local amenities + density for site / neighbourhood context.
5. **Tenders** (optional B2B branch) — if the company sells to the public sector, search Contracts Finder for matching notices and score fit.

Agent sketch:

```text
1) Companies House: KYB pack for {company_number} (or new_cos_discover for {area})
2) Extract registered / trading postcode from pack
3) Land Registry: area_comps_pack for that postcode
4) Planning: lpa_summary_pack for same postcode
5) Places: local_context_pack for same postcode
6) Optional: Tenders tender_score_pack with keywords from SIC / trading name
Merge into one research brief; cite generated_at and source licences.
```

## Licence / data-source notes

| Product | Primary source | Licence / notes |
|---------|----------------|-----------------|
| Companies House | companieshouse.gov.uk API | Open Government Licence. Not the official register — verify critical facts on the register. |
| Land Registry | HM Land Registry Price Paid via landregistry.data.gov.uk | Open Government Licence. Not the official register of title; not a valuation. England & Wales residential only; publication lag applies. |
| Planning | planning.data.gov.uk | Open Government Licence. Coverage varies by LPA; verify on the authority’s portal. |
| Tenders | Contracts Finder public search (Find a Tender later add-on) | Open Government Licence. Confirm deadlines on contractsfinder.service.gov.uk. |
| Places | OpenStreetMap Overpass + postcodes.io; optional Google Places | OSM: ODbL. postcodes.io for geocode. Google only if key configured; else OSM-only. |

## Repo layout (this hub)

```text
uk-mcp-fleet/
  README.md              # this file — canonical fleet story
  LANDING-PATTERN.md     # copy-paste pattern for Land Registry agent
  PRODUCTS.md            # short URL + outcome cheat sheet
```

Worker source lives alongside this hub on the box:

- `/workspace/uk-ch-mcp`
- `/workspace/uk-lr-mcp` (owned by Land Registry agent — do not edit from this hub task)
- `/workspace/uk-planning-mcp`
- `/workspace/uk-tenders-mcp`
- `/workspace/uk-places-mcp`

Discovery HTML mirrors: `/workspace/mcp-free-discovery/landings/{ch,planning,tenders,places,lr}.html`

## Soft-Offer

**OFF.** No outbound Soft-Offer email, chase sequences, or cold Soft-Offer lists from these Workers.
