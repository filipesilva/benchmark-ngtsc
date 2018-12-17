# Angular compiler comparison

Run `yarn benchmark` to compare initial build speeds across `tsc`, `ngc` and `ngcc`.

Rebuild benchmark not yet supported.

App used is AIO at https://github.com/angular/angular/commit/f8096d499324cf0961f092944bbaedd05364eea1.

To run it, follow these commands:
```
git clone https://github.com/filipesilva/benchmark-ngtsc
cd benchmark-ngtsc
yarn
yarn ngcc
yarn test
```

## Measurements over version/time

All times are in seconds.

| Angular version | Date measured | tsc | ngc | ngtsc | ngcc | ngcc first build |
|-----------------|---------------|-----|-----|-------|------|------------------|
| 7.1.3 | 2018-12-17 | 10.3 | 31.2 | 13.7 | 14.7 | 686.0 |

## Detailed logs

Builds were run on:
- `circleci/node:10.12` linux docker image (node v10.12.0, yarn 1.10.1)
- Windows 10 version 1803 host OS.
- Lenovo X1 Carbon with i7-8650U@2.11GHz CPU, 16GB RAM


### 2018-12-17

Note: first `ngcc` build took 686s, others took ~14.7s.

```
[benchmark] Benchmarking process over 5 iterations, with up to 5 retries.
[benchmark]   tsc -p src/tsconfig.app.json (at /src)
[benchmark] Process Stats
[benchmark]   Elapsed Time: 10320.00 ms (8230.00, 9240.00, 11040.00, 11850.00, 11240.00)
[benchmark]   Average Process usage: 0.99 process(es) (1.00, 0.99, 0.99, 1.00, 0.99)
[benchmark]   Peak Process usage: 1.00 process(es) (1.00, 1.00, 1.00, 1.00, 1.00)
[benchmark]   Average CPU usage: 79.16 % (78.85, 79.34, 78.12, 79.61, 79.87)
[benchmark]   Peak CPU usage: 193.14 % (180.00, 185.71, 211.11, 200.00, 188.89)
[benchmark]   Average Memory usage: 132.66 MB (131.97, 136.52, 135.47, 126.05, 133.31)
[benchmark]   Peak Memory usage: 213.17 MB (213.64, 213.77, 212.61, 212.86, 212.96)
[benchmark] Benchmarking process over 5 iterations, with up to 5 retries.
[benchmark]   ngc -p src/tsconfig.app.json (at /src)
[benchmark] Process Stats
[benchmark]   Elapsed Time: 31178.00 ms (29090.00, 31760.00, 33810.00, 31060.00, 30170.00)
[benchmark]   Average Process usage: 1.00 process(es) (1.00, 1.00, 1.00, 1.00, 1.00)
[benchmark]   Peak Process usage: 1.00 process(es) (1.00, 1.00, 1.00, 1.00, 1.00)
[benchmark]   Average CPU usage: 65.54 % (65.64, 65.31, 65.97, 64.82, 65.95)
[benchmark]   Peak CPU usage: 196.33 % (200.00, 191.67, 200.00, 200.00, 190.00)
[benchmark]   Average Memory usage: 229.92 MB (238.64, 230.83, 218.46, 232.72, 228.95)
[benchmark]   Peak Memory usage: 321.53 MB (329.60, 322.95, 314.53, 318.21, 322.38)
[benchmark] Benchmarking process over 5 iterations, with up to 5 retries.
[benchmark]   ngc -p src/tsconfig.app.ngtsc.json (at /src)
[benchmark] Process Stats
[benchmark]   Elapsed Time: 13728.00 ms (13890.00, 14060.00, 14090.00, 13460.00, 13140.00)
[benchmark]   Average Process usage: 1.00 process(es) (1.00, 0.99, 1.00, 0.99, 0.99)
[benchmark]   Peak Process usage: 1.00 process(es) (1.00, 1.00, 1.00, 1.00, 1.00)
[benchmark]   Average CPU usage: 84.58 % (82.66, 84.93, 85.60, 85.03, 84.68)
[benchmark]   Peak CPU usage: 192.29 % (190.00, 200.00, 191.67, 188.89, 190.91)
[benchmark]   Average Memory usage: 150.40 MB (157.71, 147.35, 146.90, 149.58, 150.45)
[benchmark]   Peak Memory usage: 230.38 MB (230.26, 229.77, 229.09, 229.91, 232.85)
```