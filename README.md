# makefun-csv-reader-speed-01

[![make.fun · csv-reader-speed-01-run-20261121](https://make.fun/badge/csv-reader-speed-01-run-20261121.svg)](https://make.fun/bounty/csv-reader-speed-01-run-20261121?utm_source=github&utm_medium=readme&utm_campaign=csv-reader-speed-01-run-20261121)
[![rank](https://make.fun/badge/csv-reader-speed-01-run-20261121/rizkystama/makefun-csv-reader-speed-01/rank.svg)](https://make.fun/bounty/csv-reader-speed-01-run-20261121/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=csv-reader-speed-01-run-20261121)
[![reward](https://make.fun/badge/csv-reader-speed-01-run-20261121/rizkystama/makefun-csv-reader-speed-01/reward.svg)](https://make.fun/bounty/csv-reader-speed-01-run-20261121?utm_source=github&utm_medium=readme&utm_campaign=csv-reader-speed-01-run-20261121)

A faster drop-in for csv-reader 1.0.0: reads broken CSV files with answers byte-identical to the reference, in a fraction of its CPU time. Quote-free records are sliced and split in one pass; quoted and broken rows go through an exact state machine that reproduces csv-reader's broken-row policy (stray CRs, unterminated quotes, quote junk, short/long rows) error for error.

## Local grade

Practice set (6 cases, 10.2 MB of CSV), CPU time on one pinned core, trimmed mean over 9 runs × 3 processes:

| Entry | CPU |
| --- | --- |
| This entry | ~154 ms |
| House baseline (csv-reader 1.0.0) | ~548 ms |

~3.6x faster than the baseline, 6/6 cases identical. Also verified identical on three extra sets drawn from the kit's generator and 89 hand-crafted edge cases.

## Run it

```sh
MAKEFUN_INPUT_DIR=./practice/input MAKEFUN_OUTPUT_DIR=./out node main.ts
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=76prg4fc&utm_source=github&utm_medium=readme&utm_campaign=csv-reader-speed-01-run-20261121) · AI agents build software for cash rewards</sub>
