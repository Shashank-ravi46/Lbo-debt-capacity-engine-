# Lbo-debt-capacity-engine-
Python-based LevFin credit tool that sizes TLB, HY and mezzanine tranches using cash-flow coverage metrics, backs out max permissible debt via scipy solver, and stress-tests capital structures across four economic scenarios.
# LBO Debt Capacity & Capital Structure Engine
### Multi-Tranche Leverage Sizing, DSCR/FCCR Covenant Analysis & Scenario Stress Testing

**Companies:** Lockheed Martin (LMT) vs. Palantir (PLTR)  
**Tools:** Python · Google Colab · Excel · yfinance · scipy · plotly · openpyxl

---

## What This Does
Replicates the core analytical workflow of a Leveraged Finance desk:
given an LBO target, sizes debt across tranches (TLB, Senior Secured Notes,
High Yield, Mezzanine), computes DSCR / ICR / FCCR / leverage year-by-year,
and uses a binary-search solver to back out the maximum permissible debt
at any given covenant threshold.

---

## Key Features
- **Debt capacity solver** (scipy `brentq`) — backs out max TLB principal
  such that DSCR ≥ 1.20x and ICR ≥ 2.50x across all projection years
- **Multi-tranche schema** — TLB (SOFR + 350bps), Senior Secured Notes
  (8.75%), HY Notes (9.50%), Mezzanine (13.00%) — pricing justified from
  Baker McKenzie LevFin 2025 and AFME HY Report Q2 2025
- **Four-scenario stress test** — Base / Mild / Moderate / Severe
- **Pass/fail heatmap** — structure × scenario, coloured by covenant breach
- **Banker-ready Excel output** — Term Sheet tab + Credit Stats tab
  with red-flagged covenant breaches

---

## Why LMT vs. PLTR?
This comparison is intentionally asymmetric.

| | LMT | PLTR |
|---|---|---|
| FY2025 Revenue | $75.0B | $3.9B |
| EBITDA Margin | ~12.5% | ~38.6% |
| FCF | $6.9B | ~$1.8B |
| Existing Leverage | ~1.9x | 0x |
| LBO Viable? | ✅ Yes | ❌ No (~137x EV/EBITDA) |

**Key LevFin insight:** PLTR has materially better coverage ratios at any
leverage level, but its ~$356B market cap makes the entry economics
impossible — the equity check dwarfs any debt capacity. LMT's stable
US government contract revenue (F-35, classified programmes) produces
the predictable FCF that lenders actually underwrite against.

---

## Debt Pricing Justification
| Tranche | Rate | Source |
|---|---|---|
| Term Loan B | SOFR (4.3%) + 350bps | Baker McKenzie LevFin Annual 2025 |
| Senior Secured Notes | 8.75% fixed | AFME HY & LL Report Q2 2025 |    
| High Yield Notes | 9.50% fixed | AFME HY & LL Report Q2 2025 |
| Mezzanine | 13.00% fixed | Standard market pricing |

---

## Files
| File | Description |
|---|---|
| `LBO_Debt_Capacity_Engine_LMT_vs_PLTR.ipynb` | Full Colab notebook (9 cells) |
| `LBO_Debt_Capacity_Engine_LMT_vs_PLTR.xlsx` | Banker-ready Excel output |

---

## Screenshot
[Paste a screenshot of the Credit Stats Summary Excel tab here]
