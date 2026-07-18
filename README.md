# STRICT12 Adaptive VRBO — Strategy Dashboard

Interactive, **mobile-enabled** research dashboard for the **STRICT12 Adaptive** IDX swing strategy.

## Open locally

```bash
# from this folder
python -m http.server 8080
# then open http://localhost:8080
```

Or just open `index.html` via any static host (GitHub Pages works).

## Strategy snapshot

| Item | Value |
|------|--------|
| Universe | 12 names listed by ~2012: ANTM, HRUM, ADRO, PTBA, ITMG, MEDC, ELSA, BYAN, ENRG, KKGI, INDY, BUMI |
| Style | Daily swing, unlevered |
| Edge | Vol-regime breakout (VRBO) + basket SMA100 gate + adaptive top-k ranking |
| Fee model | 0.15% buy + 0.25% sell = **0.40% RT** on \|Δ portfolio weight\| |
| Params | n=55, scale=1.2, hold=12d, trail=12% |

## Dashboard contents

### `index.html` — overview
- KPIs: CAGR, Max DD, multiple, Sharpe, trades, exposure, selection vs holdout
- Equity + drawdown chart (All / 5Y / Holdout 2024+)
- Yearly returns + **trade counts**
- Rolling 1Y return
- Name activity
- Live snapshot & worst underwater spells
- Rules + audit notes

### `trades.html` — all transactions
- Full trade list (entry/exit, prices, gross %, portfolio PnL contrib, weight, hold days)
- **Filter by year** (chips + dropdown), symbol, win/loss/open, search
- Summary KPIs for filtered set
- Deep link: `trades.html?year=2021`
- Data: `trades.json`

## Important disclaimers

- **Research / education only — not investment advice**
- Backtest, not live fills; residual **survivor bias** (no delisted names in source data)
- Path dominated by boom years (e.g. 2016, 2021–22); MDD can exceed **−40%**
- Prior research expanded universes; STRICT12 is the cleaner audit-friendly book

## Data

`data.json` is generated from local OHLCV research pipeline (`audit_grade_fast` / STRICT12 recipe).

## Contact

Repo owner: amindraa05@gmail.com
