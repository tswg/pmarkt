# Polymarket signals: track record

The journal is maintained automatically. Every signal is written to `signals.csv` when it is
published, before its market resolves. Results come only from the actual market payout.
The commit history of this repository timestamps every entry.

Stats page: `index.html` (published via GitHub Pages).

## Summary

```
📊 Track record as of Oct 1, 2026 00:26 UTC
Fixed notional stake per signal, results counted only from actual market resolution.

All signals: 4 signals, 4 open, 0 closed
  at work 345.62 USD, profit if right +17.48 USD

Options model: 1 signals, 1 open, 0 closed
  at work 44.36 USD, profit if right +7.64 USD

Near-resolved markets: 3 signals, 3 open, 0 closed
  at work 301.26 USD, profit if right +9.84 USD

Entries in the hash chain: 4 · chain intact ✅
```

## How to verify the journal

Entries are linked by a SHA-256 chain. For each row of `signals.csv`:

1. `hash` = SHA-256 of `prev_hash + "|" + canonical`, UTF-8, lowercase hex.
2. `prev_hash` equals the `hash` of the previous row. The first row uses 64 zeros.
3. `canonical` holds the id, time, strategy, markets, prices and stake of that row.

An old entry cannot be changed or deleted unnoticed: every later hash would break,
and the commit history would show the edit.

Not financial advice. Prediction markets can lose the whole stake.

Updated: 2026-10-01T00:26:03.193547645Z
