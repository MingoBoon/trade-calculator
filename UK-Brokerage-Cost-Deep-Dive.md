---
title: UK Brokerage Cost Deep Dive
created: 2026-06-09
tags: [trading, brokers, costs, uk]
status: research-reference
---

# UK Brokerage Cost Deep Dive

> **Purpose:** Catalogue every cost attached to a UK share/ETF trade, broker by broker, to power the true cost-per-trade model in the Position Size & Risk Calculator (`index.html`).
>
> **Data as of:** June 2026. Fees change often — always confirm on the broker's own charges page before opening an account. Sources listed at the bottom.

---

## 1. The anatomy of a trade's cost

A trade rarely costs just "the commission". For UK/US/Canadian shares there are up to **seven** separate cost layers. The dashboard model needs all of them:

| # | Cost layer | When it applies | Who charges it | Typical size |
|---|-----------|-----------------|----------------|--------------|
| 1 | **Dealing commission** | Each buy and each sell | Broker | £0 – £11.95 per trade |
| 2 | **Platform / custody fee** | Ongoing (annual, often charged monthly) | Broker | £0, or 0.10%–0.45%, or flat £4–£12/mo |
| 3 | **FX conversion fee** | Buying anything not in your account's currency (e.g. £ account buying US/CA shares) | Broker | 0.03% – 0.99% per leg |
| 4 | **Stamp Duty (SDRT)** | Buying UK **Main Market** shares only | UK Government | 0.5% of buy value |
| 5 | **PTM Levy** | Any UK trade over £10,000 (buy *and* sell) | Takeover Panel | £1 flat per leg |
| 6 | **Bid–ask spread** | Every trade, invisible | The market | Tiny on liquid stocks; **large on small-caps/penny shares** |
| 7 | **Ancillary fees** | Situational | Broker | Withdrawal, inactivity, paper statements, telephone dealing |

### Notes that matter for £0–£20 / small-cap trading
- **Stamp Duty is NOT charged on AIM-listed shares** (most UK penny/small-cap stocks live on AIM) — exempt. It also doesn't apply to US, Canadian or most ETFs. So for a lot of cheap UK stocks, layer 4 = £0.
- **The spread is the real killer on cheap stocks.** A share quoted 9.8p–10.2p has a ~4% round-trip spread cost before any commission. This dwarfs commission and must be respected in position sizing. The dashboard should let you enter the bid and ask, not just one price.
- **FX fee is per leg.** Buying *and* selling a US stock from a £ account = the FX fee twice.
- **PTM levy** only bites above £10k per order — rarely relevant at small size.

---

## 2. Commission-free / neo-brokers (best fit for active £0–£20 trading)

| Broker | Commission (shares & ETFs) | Platform fee | FX fee | ISA? | Withdrawal | Inactivity | Notes |
|--------|---------------------------|--------------|--------|------|-----------|-----------|-------|
| **Trading 212** | £0 | £0 | **0.15%** | Free | Free | None | Full UK/US/EU stocks + ETFs. Stamp duty/levies passed through at cost. Best all-round zero-fee. |
| **Lightyear** | £0 | £0 | **0.10%** (lowest) | Free | Free | None | Cheapest FX. Slightly smaller instrument range; pays interest on cash. |
| **Freetrade** | £0 | £0 Basic / £5.99mo Standard / £11.99mo Plus | **0.99% Basic, 0.59% Standard, 0.39% Plus** | Free (all plans) | Free | None | US stocks are **fractional only**; high FX on free plan makes US trading pricey. |
| **InvestEngine** | £0 | £0 (DIY) | ~0% (GBP-listed ETFs) | Free | Free | None | **ETFs only — no individual shares.** Auto-rebalancing. Not for stock picking. |
| **IG (Share Dealing GIA)** | £0 UK & US shares | £0 GIA (ISA has custody fee unless 3+ trades/qtr) | **0.70%** | Yes (fee'd) | Free | Custody fee if dormant | Commission-free since 2024 but **high FX**; better for GBP/UK trades. |
| **eToro** | £0 | £0 | ~1.5% on non-USD deposits/withdrawals | No (GIA only) | $5 per withdrawal | $10/mo after 12mo dormant | Account held in **USD** — currency drag for £ traders. |
| **Revolut** | Limited free trades/month then ~£1, by plan | £0 | FX free up to plan allowance then ~0.5–1% | Yes (newer) | Free | None | Convenient if already a customer; thin for serious trading. |

**Verdict for your use case (active £0–£20 UK/US shares):** **Trading 212** (breadth + free ISA) or **Lightyear** (lowest FX) are the clear value leaders. Avoid Freetrade Basic for US trades (0.99% FX).

---

## 3. Traditional platform brokers (percentage or flat-fee, better for larger buy-and-hold)

| Broker | Share dealing | Frequent-trader rate | Platform fee | Share/ETF fee cap | FX fee | Flat annual fee |
|--------|--------------|---------------------|--------------|-------------------|--------|-----------------|
| **Hargreaves Lansdown** | £6.95/trade (cut from £11.95 in Jan 2026) | £3.95 if >20 deals prior month | 0.35% (cut from 0.45%) | £150/yr (raised from £45) | ~1% tiered | — |
| **AJ Bell** | £5.00/trade | £3.50 if 10+ deals prior month | 0.25% | £42/yr | ~0.75% tiered | — |
| **Interactive Investor (ii)** | £3.99/trade (free regular investing) | flat | — | — | 1.5% → 0.25% tiered | **£4.99–£11.99/mo plans** |
| **Fidelity** | £7.50/trade (£1.50 regular savings) | — | 0.35% (<£25k as flat £90 option) | shares capped ~£90 | ~1% tiered | — |
| **Halifax Share Dealing** | £9.50/trade | — | — | n/a | n/a | £36/yr |
| **iWeb (Scottish Widows)** | £5.00/trade | — | £0 | n/a | ~1.5% | £0 (no ongoing fee) |
| **Barclays Smart Investor** | £6.00/trade (funds £3) | — | 0.20% funds / 0.10% other | min £48 / max £1,500 | ~1% | — |
| **Vanguard** | £0 (own funds only) | — | 0.15% capped £375 | — | n/a | — — **no individual shares** |

**Takeaway:** These suit large, infrequent, buy-and-hold portfolios. For active small trades the flat per-trade commissions (£5–£9.50) destroy the economics of a £200–£2,000 position. **ii**'s flat £3.99 is the most trade-friendly of this group.

---

## 4. Professional / global brokers (lowest variable cost at scale)

| Broker | Commission | FX fee | Platform/custody | Notes |
|--------|-----------|--------|------------------|-------|
| **Interactive Brokers (IBKR)** | UK shares ~0.05% (min £1); US $0.0035/share (min ~$0.35) | **0.03%** (min $2) — best in market | £0 (IBKR Lite) | Cheapest FX anywhere; pro-grade. Steeper learning curve. Offers ISA. |
| **Saxo** | 0.08% per trade (min removed) | ~0.25% | 0.12%/yr custody | Strong platform/app; mid-cost. |

For someone trading larger US positions frequently, **IBKR's 0.03% FX** can beat even Trading 212/Lightyear once size is meaningful, despite the small commission.

---

## 5. Mandatory costs that apply at EVERY broker (UK shares)

These are not broker fees — you pay them no matter who you use:

- **Stamp Duty Reserve Tax (SDRT): 0.5%** of the purchase value on UK **Main Market** shares. Rounded to nearest penny, collected automatically on the buy. **Exempt: AIM-listed shares, ETFs, US & Canadian shares, gilts.**
- **PTM Levy: £1 flat** on any UK trade (buy or sell) with a consideration **over £10,000**.
- **Bid–ask spread:** implicit, set by the market. Negligible on FTSE 100 names; can be **2–6%+ round trip on illiquid small-caps and penny shares** — the single biggest cost at the £0–£20 end.
- **FX spread on dividends:** US/CA dividends converted back to £ incur the broker's FX fee again.

---

## 6. Worked examples — what a real trade actually costs

### Example A — £2,000 buy of a UK AIM penny stock @ 10p (Trading 212)
- Commission: **£0**
- Stamp duty: **£0** (AIM exempt)
- PTM levy: £0 (under £10k)
- FX: £0 (GBP)
- Spread (assume 9.9p/10.1p, ~2% round trip): **~£40** ← dominant cost
- **Total round-trip cost ≈ £40 (2.0%)** — almost entirely spread.

### Example B — £2,000 buy of a UK Main Market share @ £15 (Hargreaves Lansdown)
- Commission buy + sell: £6.95 × 2 = **£13.90**
- Stamp duty: 0.5% × £2,000 = **£10.00**
- Spread (liquid, ~0.1%): ~£2
- Platform fee: 0.35%/yr on holding (separate, ongoing)
- **Total round-trip cost ≈ £25.90 (1.3%)** + ongoing platform fee.

### Example C — £2,000 buy of a US share (Freetrade Basic vs Trading 212)
- Freetrade Basic FX 0.99% × £2,000 × 2 legs = **£39.60** in FX alone
- Trading 212 FX 0.15% × £2,000 × 2 legs = **£6.00**
- **Same trade, £33.60 cheaper on Trading 212** — shows why FX rate dominates US trading.

---

## 7. Quick-reference value ranking (for active small-size UK/US trading)

1. **Trading 212** — £0 commission, 0.15% FX, free ISA. Best all-round.
2. **Lightyear** — £0 commission, 0.10% FX. Best if mostly US/foreign shares.
3. **Interactive Brokers** — unbeatable 0.03% FX + tiny commission once size grows.
4. **IG** — £0 commission but 0.70% FX; fine for UK-only.
5. **interactive investor** — flat £3.99 + monthly fee; good for frequent larger UK trades.
6. **Freetrade Plus** — only if you pay up to 0.39% FX; Basic plan poor for US.

> Avoid percentage-platform brokers (HL, Fidelity, Vanguard) and high flat-commission brokers (Halifax £9.50) for active small trades — the fixed cost per trade ruins small positions.

---

## 8. Cost model for the dashboard (integration spec)

Structure to wire into the calculator. **Round-trip total cost** for a position:

```
buyValue   = shares × entryPrice
sellValue  = shares × exitPrice

commission     = buyCommission + sellCommission          // per broker
stampDuty      = isUKMainMarket ? 0.005 × buyValue : 0    // buy only, not AIM/US/CA/ETF
ptmLevy        = (buyValue > 10000 ? 1 : 0) + (sellValue > 10000 ? 1 : 0)
fxCost         = isForeignCcy ? fxRate × (buyValue + sellValue) : 0   // per leg
spreadCost     = (ask - bid) × shares                     // if user enters bid/ask
platformCost   = optional, annualised (info only)

totalCost      = commission + stampDuty + ptmLevy + fxCost + spreadCost
netProfit      = (sellValue - buyValue) - totalCost
breakevenMove  = totalCost / shares     // pence the price must move just to cover costs
```

> **Status:** fully implemented in `index.html`. The broker dropdown, spread input, FX toggle, stamp duty toggle and exit-price calculation are all live. The exit price formula correctly splits spread cost across the buy and sell legs so the sell-side spread scales with the exit value.

### Per-broker parameters (implemented in the dashboard dropdown):

| Broker | buyCommission | sellCommission | fxRate | passesStampDuty | platformFee |
|--------|--------------|----------------|--------|-----------------|-------------|
| Trading 212 | 0 | 0 | 0.0015 | yes | 0 |
| Lightyear | 0 | 0 | 0.0010 | yes | 0 |
| Freetrade Basic | 0 | 0 | 0.0099 | yes | 0 |
| Freetrade Plus | 0 | 0 | 0.0039 | yes | 9.99/mo |
| IG | 0 | 0 | 0.0070 | yes | 0 (GIA) |
| Hargreaves Lansdown | 6.95 | 6.95 | ~0.01 | yes | 0.35%/yr |
| AJ Bell | 5.00 | 5.00 | ~0.0075 | yes | 0.25%/yr |
| interactive investor | 3.99 | 3.99 | ~0.0145 | yes | £4.99–11.99/mo |
| iWeb | 5.00 | 5.00 | ~0.015 | yes | 0 |
| Halifax | 9.50 | 9.50 | n/a | yes | £36/yr |
| Interactive Brokers | ~1.00 | ~1.00 | 0.0003 | yes | 0 |

> Custom broker entry is also supported — select "Custom" to enter your own commission and FX rate and see it ranked alongside the presets.

---

## Sources

- [QuantRoutine — Best Broker UK 2026](https://quantroutine.com/brokers/best-broker-uk/)
- [Good Money Guide — UK Share Trading Platforms](https://goodmoneyguide.com/trading/shares/)
- [Freetrade vs Trading 212 vs InvestEngine 2026](https://investplatforms.co.uk/blog/freetrade-trading212-investengine/)
- [Lightyear vs Trading 212](https://financialinterest.com/compare/lightyear-vs-trading-212/)
- [Hargreaves Lansdown slashes ISA & SIPP fees Jan 2026 — Kepler](https://www.trustintelligence.co.uk/investor/articles/hargreaves-lansdown-slashes-isa-and-sipp-fees-jan-2026)
- [AJ Bell vs Hargreaves Lansdown 2026](https://generationmoney.co.uk/aj-bell-vs-hargreaves-lansdown/)
- [Interactive Investor fee changes explained](https://financialinterest.com/interactive-investor-fees-explained/)
- [Compare investment platform fees — Which?](https://www.which.co.uk/money/investing/investment-platforms-and-fund-supermarkets/best-investment-platforms/compare-investment-platform-fees-and-charges-anYec4l0G9J5)
- [Halifax Share Dealing review — StockBrokers.com](https://www.stockbrokers.com/uk/review/halifax)
- [iWeb / Scottish Widows charges](https://www.iweb-sharedealing.co.uk/charges/competitor-charges.html)
- [Stamp Duty Reserve Tax Guide 2026](https://calculatemystampduty.co.uk/guides/stamp-duty-reserve-tax)
- [Stamp Duty on Shares — interactive investor](https://www.ii.co.uk/learn/tax/stamp-duty)
- [Interactive Brokers Commissions & Fees](https://www.interactivebrokers.co.uk/en/pricing/commissions-home.php)
- [Saxo UK review — StockBrokers.com](https://www.stockbrokers.com/uk/review/saxo)
- [IG share dealing costs & fees](https://www.ig.com/uk/investments/share-dealing/costs-fees)

*Educational reference, not financial advice. Verify all figures with the provider before acting.*
