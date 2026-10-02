# Polymarket signals: track record

The journal is maintained automatically. Every signal is written to `signals.csv` when it is
published, before its market resolves. Results come only from the actual market payout.
The commit history of this repository timestamps every entry.

Stats page: `index.html` (published via GitHub Pages).

## Summary

```
📊 Track record as of Oct 2, 2026 11:31 UTC
Fixed notional stake per signal, results counted only from actual market resolution.

All signals: 11 signals, 8 open, 3 closed
  won 2, lost 1, flat 0 · win rate 67%
  expected wins 2.1 of 3, actual 2
  staked 251.06 USD, result -95.97 USD (-38.22%)
  at work 785.64 USD, profit if right +250.80 USD

Options model: 6 signals, 4 open, 2 closed
  won 1, lost 1, flat 0 · win rate 50%
  expected wins 1.1 of 2, actual 1
  staked 150.94 USD, result -98.94 USD (-65.55%)
  at work 383.95 USD, profit if right +236.26 USD

Near-resolved markets: 5 signals, 4 open, 1 closed
  won 1, lost 0, flat 0 · win rate 100%
  expected wins 1.0 of 1, actual 1 · chance of this by luck 97%
  staked 100.12 USD, result +2.97 USD (+2.97%)
  at work 401.69 USD, profit if right +14.54 USD

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

Updated: 2026-10-02T11:31:17.832237497Z
