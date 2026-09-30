# Landing pattern for Land Registry (`uk-lr-mcp`)

**Do not edit `/workspace/uk-lr-mcp` from the fleet-hub task** — Land Registry agent owns that Worker. Copy this pattern into `htmlLanding()` in `src/index.ts` when ready.

## Outcome line

> **Compare sold prices around this postcode.**

Also useful bullets: recent Price Paid sales; area comps with honest thin-sample flags; one-shot JSON after £0.49 Checkout.

## Free vs paid matrix (required table)

Add table CSS if missing:

```css
table{border-collapse:collapse;width:100%;font-size:.9rem;margin:.75rem 0}
th,td{border:1px solid #ddd;padding:.4rem .55rem;text-align:left}
th{background:#f4f4f5}
```

HTML block:

```html
<h2>Free vs paid</h2>
<table>
  <thead><tr><th>Capability</th><th>Free discovery</th><th>Paid pack</th></tr></thead>
  <tbody>
    <tr><td>Tool/schema discovery</td><td>Yes</td><td>—</td></tr>
    <tr><td>Small sample / metadata</td><td>Yes</td><td>—</td></tr>
    <tr><td>Full structured result</td><td>Limited</td><td>Yes</td></tr>
    <tr><td>Larger result set</td><td>No</td><td>Yes</td></tr>
    <tr><td>Compound interpretation</td><td>No/limited</td><td>Yes</td></tr>
    <tr><td>Export-ready JSON</td><td>Limited</td><td>Yes</td></tr>
  </tbody>
</table>
<p class="off">Paid packs include <code>generated_at</code> and source/retrieval timing in pack JSON where available.</p>
```

## Copy rules

- Always say **Land Registry** (never “LR”) in public HTML.
- Soft-Offer outbound is **OFF**.
- Pricing: £0.49 smoke; note pro tiers dormant if mentioned.
- Licence blurb stays: HM Land Registry Price Paid, Open Government Licence, not official register of title, England & Wales residential only, publication lag.

## Minimal outcome + matrix insert point

Place the outcome `<p><strong>Outcome:</strong> Compare sold prices around this postcode.</p>` near the top (under the H1 / tagline), and the Free vs paid table before “How agents use this”.

## Discovery mirror

After updating the Worker landing, mirror a trimmed HTML copy to:

`/workspace/mcp-free-discovery/landings/lr.html`

Live URL: https://uk-lr-mcp.donniertf.workers.dev
