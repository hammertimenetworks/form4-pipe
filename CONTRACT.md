# FORM4 PIPE contract

Product: form4-pipe
Host: https://aurora-lion-clear-hill.grok.me
Source: SEC EDGAR current Form 4 filings
Disclaimer: Public SEC Form 4 data. Not investment advice, not a solicitation, not an offer of securities.

## Endpoints

| Method | Path | Purpose |
| --- | --- | --- |
| GET | /api/v1/health | Liveness. Lists the contract. |
| GET | /api/v1/form4 | Full tape: filings, transactions when XML parsed, clusters, stats. |
| GET | /api/v1/form4?format=clusters | Issuer rollup only. Smaller payload for bots. |
| GET | /api/v1/form4?format=csv | Spreadsheet tape. |

Auth: none on the public grok.me URL. X-Pipe-Key is not required yet.

## Health shape

```json
{
  "ok": true,
  "product": "form4-pipe",
  "endpoints": [
    "/api/v1/form4",
    "/api/v1/form4?format=csv",
    "/api/v1/form4?format=clusters"
  ]
}
```

## Tape fields (filings[])

- accession, filed, issuerName, issuerCik, ticker
- reporters[]: name, cik, role
- txs[]: code, acquired, shares, price, date, security

Transaction codes follow EDGAR Table I/II. Code P = open-market / private purchase. Code S = sale.

## Flags

- cluster_buy: >=2 reporting persons, code P, same issuer, this window
- open_market_buy: at least one P, single reporter
- sale / mixed / other: S prints or mixed / non-P activity
