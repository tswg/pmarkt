# Polymarket signals: track record

The journal is maintained automatically. Every signal is written to `signals.csv` when it is
published, before its market resolves. Results come only from the actual market payout.
The commit history of this repository timestamps every entry.

Stats page: `index.html` (published via GitHub Pages).

## Summary

```
📊 Track record as of Oct 1, 2026 07:27 UTC
Fixed notional stake per signal, results counted only from actual market resolution.

All signals: 6 signals, 5 open, 1 closed
  won 1, lost 0, flat 0 · win rate 100%
  expected wins 0.9 of 1, actual 1 · chance of this by luck 93%
  staked 44.36 USD, result +7.64 USD (+17.22%)
  at work 511.62 USD, profit if right +1683.54 USD

Options model: 3 signals, 2 open, 1 closed
  won 1, lost 0, flat 0 · win rate 100%
  expected wins 0.9 of 1, actual 1 · chance of this by luck 93%
  staked 44.36 USD, result +7.64 USD (+17.22%)
  at work 210.36 USD, profit if right +1673.70 USD

Near-resolved markets: 3 signals, 3 open, 0 closed
  at work 301.26 USD, profit if right +9.84 USD

Entries in the hash chain: 6 · chain intact ✅
```

## How to verify the journal

Entries are linked by a SHA-256 chain. For each row of `signals.csv`:

1. `hash` = SHA-256 of `prev_hash + "|" + canonical`, UTF-8, lowercase hex.
2. `prev_hash` equals the `hash` of the previous row. The first row uses 64 zeros.
3. `canonical` holds the id, time, strategy, markets, prices and stake of that row.

An old entry cannot be changed or deleted unnoticed: every later hash would break,
and the commit history would show the edit.

Not financial advice. Prediction markets can lose the whole stake.

Updated: 2026-10-01T07:27:11.055145184Z
