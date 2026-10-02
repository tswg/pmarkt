# Polymarket signals: track record

The journal is maintained automatically. Every signal is written to `signals.csv` when it is
published, before its market resolves. Results come only from the actual market payout.
The commit history of this repository timestamps every entry.

Stats page: `index.html` (published via GitHub Pages).

## Summary

```
📊 Track record as of Oct 2, 2026 16:20 UTC
Fixed notional stake per signal, results counted only from actual market resolution.

All signals: 11 signals, 3 open, 8 closed
  won 5, lost 3, flat 0 · win rate 63%
  expected wins 6.1 of 8, actual 5
  staked 733.35 USD, result -248.30 USD (-33.86%)
  at work 303.35 USD, profit if right +71.54 USD

Options model: 6 signals, 1 open, 5 closed
  won 2, lost 3, flat 0 · win rate 40%
  expected wins 3.2 of 5, actual 2
  staked 432.09 USD, result -258.14 USD (-59.74%)
  at work 102.80 USD, profit if right +63.87 USD

Near-resolved markets: 5 signals, 2 open, 3 closed
  won 3, lost 0, flat 0 · win rate 100%
  expected wins 2.9 of 3, actual 3 · chance of this by luck 90%
  staked 301.26 USD, result +9.84 USD (+3.27%)
  at work 200.55 USD, profit if right +7.67 USD

Entries in the hash chain: 11 · chain intact ✅
```

## How to verify the journal

Entries are linked by a SHA-256 chain. For each row of `signals.csv`:

1. `hash` = SHA-256 of `prev_hash + "|" + canonical`, UTF-8, lowercase hex.
2. `prev_hash` equals the `hash` of the previous row. The first row uses 64 zeros.
3. `canonical` holds the id, time, strategy, markets, prices and stake of that row.

An old entry cannot be changed or deleted unnoticed: every later hash would break,
and the commit history would show the edit.

Not financial advice. Prediction markets can lose the whole stake.

Updated: 2026-10-02T16:20:26.520449286Z
