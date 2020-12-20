# hpc_pfam_search

Fork of `pfam_scan` that uses [`hpc_hmmsearch`](https://github.com/Larofeticus/hpc_hmmsearch) instead of `hmmsearch` to greatly reduce the execution time.

## Benchmark

Benchmark comparing `hpc_pfam_search` to regular `pfam_scan` and [`pfam_search`](https://github.com/Ecogenomics/pfam_search). The commands were executed using an input with 1,000 sequences and 32 cpu cores. Execution times were measured with [hyperfine](https://github.com/sharkdp/hyperfine).

```
pfam_scan.pl
  Time (mean ± σ):     345.319 s ±  1.564 s    [User: 397.618 s, System: 232.994 s]
  Range (min … max):   343.892 s … 347.999 s    5 runs

pfam_search.pl
  Time (mean ± σ):     129.560 s ±  3.295 s    [User: 168.469 s, System: 254.537 s]
  Range (min … max):   126.042 s … 134.696 s    5 runs

hpc_pfam_search.pl
  Time (mean ± σ):     12.331 s ±  0.054 s    [User: 141.741 s, System: 1.694 s]
  Range (min … max):   12.254 s … 12.402 s    5 runs
```