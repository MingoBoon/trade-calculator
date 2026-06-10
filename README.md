# Position Size, Risk & True-Cost Calculator

A single-file web tool for sizing share/ETF trades to a fixed % risk and seeing the real cost after broker fees, FX, stamp duty and spread — with live stock details and a recommended broker for each trade.

**Live version:** _(add your GitHub Pages link here once published)_

## What it does

- **Live price fetch** — pulls a delayed price for any LSE, NYSE/Nasdaq, TSX, ASX or European ticker via Yahoo Finance
- **Stock detail panel** — shows full company name, sector, industry, country, market cap, volume vs average (capital flow), 52-week range, P/E, dividend yield, beta, institutional/insider ownership and short interest
- **Position sizing** — sizes the trade to 1%, 2% and 3% account risk simultaneously, using your entry and stop-loss prices
- **True cost** — calculates round-trip cost including dealing commission, UK stamp duty, PTM levy, FX conversion fee and bid–ask spread
- **Exit price** — shows the exact price you need to sell at to bank your target profit *after* all fees
- **Broker recommendation** — ranks 11 preset brokers (plus custom) by cheapest round-trip cost for the 2% position

## Files

- `index.html` — the calculator (this is what GitHub Pages serves)
- `UK-Brokerage-Cost-Deep-Dive.md` — broker fee reference and cost model behind the engine

## How to update it

Edit `index.html` on GitHub (pencil icon) → Commit changes. The live site refreshes in ~1 minute.

## Notes

- Runs entirely in the visitor's browser. No data is stored or sent anywhere.
- Live prices and stock details come from Yahoo Finance via a public CORS proxy and may occasionally be blocked — the manual price entry always works.
- Educational tool, not financial advice. Fee data as of June 2026 — verify with your broker before trading.
