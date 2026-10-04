# Polymarket signals: track record

The journal is maintained automatically. Every signal is written to `signals.csv` when it is
published, before its market resolves. Results come only from the actual market payout.
The commit history of this repository timestamps every entry.

Premium members get signals first. Until the free channel gets a signal (or its market
resolves), its row is sealed: only `seq`, `created_at`, status `SEALED` and `commitment`
are shown. The full row and its `salt` are published later.

Stats page: `index.html` (published via GitHub Pages).

## Summary

```
📊 Track record as of Oct 4, 2026 08:12 UTC
Fixed notional stake per signal, results counted only from actual market resolution.

All signals: 14 signals, 1 open, 13 closed
  won 10, lost 3, flat 0 · win rate 77%
  expected wins 10.5 of 13, actual 10
  staked 1239.92 USD, result -117.40 USD (-9.47%)
  at work 103.15 USD, profit if right +78.67 USD

Options model: 9 signals, 1 open, 8 closed
  won 5, lost 3, flat 0 · win rate 63%
  expected wins 5.6 of 8, actual 5
  staked 738.11 USD, result -134.92 USD (-18.28%)
  at work 103.15 USD, profit if right +78.67 USD

Near-resolved markets: 5 signals, 0 open, 5 closed
  won 5, lost 0, flat 0 · win rate 100%
  expected wins 4.8 of 5, actual 5 · chance of this by luck 83%
  staked 501.81 USD, result +17.52 USD (+3.49%)

Entries in the hash chain: 14 · chain intact ✅
```

## How to verify the journal

Entries are linked by a SHA-256 chain. For each row of `signals.csv`:

1. `hash` = SHA-256 of `prev_hash + "|" + canonical`, UTF-8, lowercase hex.
2. `prev_hash` equals the `hash` of the previous row. The first row uses 64 zeros.
3. `canonical` holds the id, time, strategy, markets, prices and stake of that row.
4. If `salt` is set, `commitment` = SHA-256 of `salt + "|" + hash`, and the same
   `commitment` appears in the commit that first added the row, while it was still sealed.

Sealed rows are always the last rows of the file: rows are revealed strictly in order.
Skip them when checking the chain; check them once they are revealed.

An old entry cannot be changed or deleted unnoticed: every later hash would break,
and the commit history would show the edit.

Not financial advice. Prediction markets can lose the whole stake.

Updated: 2026-10-04T08:12:44.347089270Z
