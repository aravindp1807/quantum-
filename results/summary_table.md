# Results Summary — SQD N₂ Benchmark

## Energy Comparison

| Method | Energy (Ha) | Error vs FCI (Ha) | Error (mHa) | Within chemical accuracy (1.6 mHa) |
|---|---|---|---|---|
| HF | -108.835237 | 6.60e-02 | 65.951 | ❌ No |
| CCSD | -108.900003 | 1.18e-03 | 1.184 | ✅ Yes |
| Exact CASCI/FCI | -108.901187 | 0.00e+00 | 0.000 | ✅ Yes |
| SQD + Aer noiseless | -108.866422 | 3.48e-02 | 34.765 | ❌ No |
| SQD + PennyLane noiseless | -108.866422 | 3.48e-02 | 34.765 | ❌ No |
| SQD + Aer noisy | -108.901166 | 2.17e-05 | 0.022 | ✅ Yes |
| SQD + PennyLane noisy | -108.901187 | 1.08e-10 | 0.000 | ✅ Yes |
| SQD + Random bitstrings | -108.901187 | 1.08e-10 | 0.000 | ✅ Yes |

## Sampling Statistics

| Sampler | Shots | Circuit depth | 2q gates | Sampling time (s) | Valid-particle-number shots | Unique bitstrings | Unique valid | SQD subspace dim (full CI = 441) |
|---|---|---|---|---|---|---|---|---|
| Aer noiseless | 10,000 | 62 | 182 | 0.10 | 100.0% | 5 | 5 | 9 |
| PennyLane noiseless | 10,000 | 181 | 188 | 0.09 | 100.0% | 6 | 6 | 9 |
| Aer noisy | 1,000 | 239 | 188 | 302.08 | 32.9% | 421 | 50 | 400 |
| PennyLane noisy | 1,000 | 181 | 188 | 39.19 | 32.4% | 417 | 52 | 441 |
| Random bitstrings | 10,000 | 0 | 0 | 0.05 | 3.0% | 7,509 | 214 | 441 |

## SQD Convergence (|E − E_FCI| per iteration)

| SQD iteration | Aer noiseless | PennyLane noiseless | Aer noisy | PennyLane noisy | Random bitstrings |
|---|---|---|---|---|---|
| 0 | 3.48e-02 | 3.48e-02 | 3.00e-04 | 2.17e-05 | 1.08e-10 |
| 1 | 3.48e-02 | 3.48e-02 | 1.50e-07 | 1.08e-10 | 1.08e-10 |
| 2 | 3.48e-02 | 3.48e-02 | 1.08e-10 | 1.08e-10 | 1.08e-10 |
| 3 | 3.48e-02 | 3.48e-02 | 1.50e-07 | 2.17e-05 | 1.08e-10 |
| 4 | 3.48e-02 | 3.48e-02 | 2.17e-05 | 1.08e-10 | 1.08e-10 |

## Distribution Comparison (Total Variation Distance)

| Comparison | TVD | Notes |
|---|---|---|
| Noiseless Aer vs PennyLane (full bitstring dist.) | **0.002** | ≈ 0 expected — same physics, shot noise only |
| Noisy Aer vs PennyLane (electron-number dist.) | **0.045** | Different noise models — deviation expected |
