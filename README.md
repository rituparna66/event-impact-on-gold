

## LSTM Results

Many-to-one LSTM (hidden_size=8, dropout=0.2, weight_decay=1e-3, gradient clipping, early stopping)
on 10-event sequences of [surprise_score, pip_move_4h, vix, dxy_ret], predicting the next event's
pip_move_4h.

- LSTM Test MAE (early-stopped): 29.04
- XGBoost (lag-features, N=10 rolling mean/std/last) Test MAE: 27.56

Comparable performance once early stopping prevents overfitting — without it, the LSTM overfit
heavily (train loss collapsed toward ~0, test MAE rose to 106). With only ~90 total events,
XGBoost on simple rolling-window features slightly edges out the LSTM. Both models undershoot
rare HIGH-impact spikes and overshoot near-zero moves, regressing toward the dataset mean — a
data-scarcity limitation rather than an architecture flaw. More training events (especially more
HIGH-impact examples) would likely let the LSTM realize its advantage on sequence patterns.
