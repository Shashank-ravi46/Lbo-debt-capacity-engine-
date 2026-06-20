# LBO Debt Capacity & Capital Structure Engine

Multi-tranche debt sizing engine computing DSCR, FCCR and interest 
coverage across TLB, HY Notes and Mezzanine — applied to Lockheed 
Martin vs. Palantir under four stress scenarios.

## Tools
Python · Google Colab · Excel · yfinance · scipy · plotly · openpyxl

## What It Does
- Sizes debt tranches using cash-flow coverage metrics
- Backs out maximum permissible leverage via scipy solver
- Stress-tests capital structures across Base/Mild/Moderate/Severe scenarios
- Outputs banker-ready Excel term sheet with covenant breach flags

## Files
| File | Description |
|---|---|
| LBO_Debt_Capacity_Engine.ipynb | Full Colab notebook |
| LBO_Debt_Capacity_Engine.xlsx | Banker-ready Excel output |

## Screenshot
<img width="1470" height="956" alt="Screenshot 2026-06-20 at 15 27 51" src="https://github.com/user-attachments/assets/5cba625b-c0b3-48ad-82cc-73a71ee49f17" />

