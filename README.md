
- **CPI (Core CPI m/m)**: 50 events, Jun 2022 – Sep 2026. Actual/forecast/previous from economic calendar; XAUUSD price at release and 4H after recorded manually from TradingView H1 charts.
- **FOMC (Fed Funds Rate)**: 21 events, Mar 2024 – Sep 2026. Same method.
- **NFP (Non-Farm Payrolls)**: 21 events, Dec 2024 – Oct 2026. Same method.

Total: 92 events across 3 event types, merged into `data/events.csv`.

surprise_score = (actual - forecast) / std(actual), computed separately per event_type since CPI (%), FOMC (%), and NFP (K jobs) are on different scales.

Impact label thresholds (pip_move_4h, 1 pip = $1): HIGH >15, MED 5–15, LOW <5.
