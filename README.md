# Polymarket signals: track record

The journal is maintained automatically. Every signal is written to `signals.csv` when it is
published, before its market resolves. Results come only from the actual market payout.
The commit history of this repository timestamps every entry.

Stats page: `index.html` (published via GitHub Pages).

## Summary

```
📊 Track record as of Oct 2, 2026 03:20 UTC
Fixed notional stake per signal, results counted only from actual market resolution.

All signals: 9 signals, 7 open, 2 closed
  won 1, lost 1, flat 0 · win rate 50%
  expected wins 1.1 of 2, actual 1
  staked 150.94 USD, result -98.94 USD (-65.55%)
  at work 708.39 USD, profit if right +194.99 USD

Options model: 4 signals, 2 open, 2 closed
  won 1, lost 1, flat 0 · win rate 50%
  expected wins 1.1 of 2, actual 1
  staked 150.94 USD, result -98.94 USD (-65.55%)
  at work 206.58 USD, profit if right +177.48 USD

Near-resolved markets: 5 signals, 5 open, 0 closed
  at work 501.81 USD, profit if right +17.52 USD

Entries in the hash chain: 9 · chain intact ✅
```

## How to verify the journal

Entries are linked by a SHA-256 chain. For each row of `signals.csv`:

1. `hash` = SHA-256 of `prev_hash + "|" + canonical`, UTF-8, lowercase hex.
2. `prev_hash` equals the `hash` of the previous row. The first row uses 64 zeros.
3. `canonical` holds the id, time, strategy, markets, prices and stake of that row.

An old entry cannot be changed or deleted unnoticed: every later hash would break,
and the commit history would show the edit.

Not financial advice. Prediction markets can lose the whole stake.

Updated: 2026-10-02T03:20:41.438666565Z
