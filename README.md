# Bitcoin Blockchain Security & the Simple Random Walk
### Probability · Markov Chains · Monte Carlo Simulations · Python · Université Côte d'Azur (M1)

*Project by Hanaa Zaita, Amal El Moussaoui and Alessia Van der Auwermeulen — January 2026*

## Overview

This project studies the **security of Bitcoin's Proof-of-Work blockchain** against double-spending attacks. We model the mining competition as a **biased random walk** and derive a closed-form expression for the attack success probability, then verify it empirically using Monte Carlo simulations.

**Main question:** how many block confirmations are enough to make an attack virtually impossible?

## Mathematical Framework

**1. Mining as a Random Walk**
The difference between the honest chain and the attacker's chain follows a biased random walk with drift p − q > 0 in favour of honest miners.

**2. Gambler's Ruin**
The probability that the attacker (starting z blocks behind) ever catches up:
- P_success(z) = (q/p)^z if q < p → exponential decay with confirmations

**3. Nakamoto Poisson Model**
Refines the model by accounting for random block timing via a Poisson process.

**4. Monte Carlo Validation**
Simulations confirm theoretical results — estimator convergence illustrated via LLN and CLT.

## Key Result

| Confirmations (z) | q=0.1 | q=0.2 | q=0.3 | q=0.4 |
|:-----------------:|:-----:|:-----:|:-----:|:-----:|
| 1 | 0.012 | 0.063 | 0.184 | 0.444 |
| 6 | ~10⁻¹² | ~10⁻⁵ | ~10⁻² | 0.082 |
| 10 | ~10⁻²⁰ | ~10⁻⁹ | ~10⁻³ | 0.012 |

The standard 6-confirmation rule makes attacks practically impossible for q < 0.3.

## Files

- `projetbitcoin (2).ipynb` — full Python simulation notebook
- `Bitcoin-4 (1).pdf` — written report

## How to Run

```bash
pip install numpy matplotlib scipy
jupyter notebook projetbitcoin.ipynb
```

## Concepts Covered
Markov chains · Biased random walks · Gambler's Ruin · Poisson process · Monte Carlo simulation · LLN & CLT

*M1 Mathematics — Probability & Statistics · Université Côte d'Azur · January 2026*
