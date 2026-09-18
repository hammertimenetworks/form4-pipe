# FORM4 PIPE

Public SEC Form 4 tape, clustered by issuer. Not advice. Not a securities offering. Not a dashboard company.

**Live product:** https://aurora-lion-clear-hill.grok.me  
**Health:** https://aurora-lion-clear-hill.grok.me/api/v1/health  
**Operator:** HammerTime Networks / Inertia Holdings Ltd. · [@Dennis_Hammer](https://x.com/Dennis_Hammer)

Verified live on 2026-09-18: `GET /api/v1/health` returns `{"ok":true,"product":"form4-pipe"}`. Tape includes real EDGAR prints (ADBE, KMI, WSM, TYGO, and others).

## Contract

```
GET /api/v1/health
GET /api/v1/form4
GET /api/v1/form4?format=clusters
GET /api/v1/form4?format=csv
```

Base URL: `https://aurora-lion-clear-hill.grok.me`

### curl

```bash
curl -s https://aurora-lion-clear-hill.grok.me/api/v1/health

curl -s https://aurora-lion-clear-hill.grok.me/api/v1/form4 | jq '.stats'

curl -s 'https://aurora-lion-clear-hill.grok.me/api/v1/form4?format=clusters' \
  | jq '.clusters[] | select(.flag=="cluster_buy")'
```

## Flags

- `cluster_buy` — two or more reporting persons, open-market purchases (code P) on the same issuer in this window
- `open_market_buy` — at least one P, single reporter
- `sale` / `mixed` / `other` — S prints, mixed codes, grants/exercises/other

## What this is

Issuer-level cluster detection on open-market P prints. JSON, ~8-minute cache, CSV. Built for quants, Discord bots, and newsletter desks that already have distribution.

Public EDGAR data only. FINRA license is not on this product. You sell parsed filings, not "buy GPUS."

## SKUs (not live-billed yet)

Stripe on Inertia Holdings is still sandbox. Do not claim live checkout.

- Free: poll the public URL (fair use)
- Builder: $49/mo JSON
- Desk: $199/mo JSON + CSV + brief
- Custom filter: $499 one-time

## Disclaimer

Public SEC Form 4 data. Not investment advice, not a solicitation, not an offer of securities.
