# FAA attribution forecaster — polymarket-faa-attribution-01

Entry for make.fun's `polymarket-faa-attribution-01` (deadline
2026-11-15 09:00 UTC). Same forecaster family as our Nvidia and
faa-attribution-02 entries: per-market empirical quantiles of h-minute
price changes, decay-weighted, log-h interpolated across 28 anchors,
with a partition-sum conditioning that only engages for genuine
partition families — and a small-family path (drift, wider spread and
tails) tuned on the FAA attribution markets' own tape, which is what
this competition's final actually grades. Offline, stdlib-only
Python. See TUNING.md.
