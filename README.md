# Polymarket signals: track record

The journal is maintained automatically. Every signal is written to `signals.csv` when it is
published, before its market resolves. Results come only from the actual market payout.
The commit history of this repository timestamps every entry.

Stats page: `index.html` (published via GitHub Pages).

## Summary

```
📊 Track record as of Oct 3, 2026 00:16 UTC
Fixed notional stake per signal, results counted only from actual market resolution.

All signals: 12 signals, 3 open, 9 closed
  won 6, lost 3, flat 0 · win rate 67%
  expected wins 6.8 of 9, actual 6
  staked 836.15 USD, result -184.43 USD (-22.06%)
  at work 301.60 USD, profit if right +24.27 USD

Options model: 7 signals, 1 open, 6 closed
  won 3, lost 3, flat 0 · win rate 50%
  expected wins 3.9 of 6, actual 3
  staked 534.89 USD, result -194.27 USD (-36.32%)
  at work 101.05 USD, profit if right +16.60 USD

Near-resolved markets: 5 signals, 2 open, 3 closed
  won 3, lost 0, flat 0 · win rate 100%
  expected wins 2.9 of 3, actual 3 · chance of this by luck 90%
  staked 301.26 USD, result +9.84 USD (+3.27%)
  at work 200.55 USD, profit if right +7.67 USD

Entries in the hash chain: 12 · chain intact ✅
```

## How to verify the journal

Entries are linked by a SHA-256 chain. For each row of `signals.csv`:

1. `hash` = SHA-256 of `prev_hash + "|" + canonical`, UTF-8, lowercase hex.
2. `prev_hash` equals the `hash` of the previous row. The first row uses 64 zeros.
3. `canonical` holds the id, time, strategy, markets, prices and stake of that row.

An old entry cannot be changed or deleted unnoticed: every later hash would break,
and the commit history would show the edit.

Not financial advice. Prediction markets can lose the whole stake.

Updated: 2026-10-03T00:16:27.679165044Z
