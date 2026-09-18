# Paste this into Gemini sidebar

Correct live Form 4 product (insider trading tape), NOT an xAI console bookmark:

URL: https://aurora-lion-clear-hill.grok.me
GitHub: https://github.com/hammertimenetworks/form4-pipe

This is FORM4 PIPE. Public SEC EDGAR Form 4 data clustered by issuer.

Do not confuse with any other Grok project URL. Confirm with:
curl -s https://aurora-lion-clear-hill.grok.me/api/v1/health
Expected: {"ok":true,"product":"form4-pipe",...}

Endpoints:
- GET /api/v1/form4
- GET /api/v1/form4?format=clusters
- GET /api/v1/form4?format=csv

Flags: cluster_buy (>=2 reporters, code P, same issuer), open_market_buy, sale/mixed/other.

Disclaimer: public data, not advice, not a securities offering.
Stripe is still sandbox. Do not tell users checkout is live.
