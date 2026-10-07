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
📊 Track record as of Oct 7, 2026 00:03 UTC
Fixed notional stake per signal, results counted only from actual market resolution.

All signals: 14 signals, 0 open, 14 closed
  won 11, lost 3, flat 0 · win rate 79%
  expected wins 11.1 of 14, actual 11
  staked 1343.07 USD, result -38.74 USD (-2.88%)

Options model: 9 signals, 0 open, 9 closed
  won 6, lost 3, flat 0 · win rate 67%
  expected wins 6.3 of 9, actual 6
  staked 841.26 USD, result -56.25 USD (-6.69%)

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

Updated: 2026-10-07T00:03:31.019623570Z
