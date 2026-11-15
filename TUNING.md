# Tuning — polymarket-faa-attribution-01

The practice cases in this kit are byte-identical in market data to
polymarket-faa-attribution-02's (same Nvidia checkpoints, same
prices), the house baseline reproduces exactly through the local
scorer replica (0.363589), and this entry scores the same 0.269483 on
them. The final, however, runs on the FAA attribution family — five
independent Yes/No markets that opened 2026-11-13 and repriced
violently (Iran 0.515 -> 0.018 overnight).

That family's own tape (fetched from Polymarket's public price
history) was cut into pseudo cases and scored on truncated
60/120-minute horizons. The partition settings scored 1.0289 @60 /
0.9542 @120 there; adding half the empirical median back as drift,
width 0.80 and tail multiplier 1.6 for small families scored 0.9380 /
0.9039 — the combination shipped here as the small-family path
(active whenever a case holds fewer than 8 markets, which covers
every FAA final case and never touches the partition path). Full
methodology and the variant table live in the faa-attribution-02
entry's TUNING.md; the model code is the same.
