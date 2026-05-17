# Hawkes Process with Exponential Kernel — Markov Property

Proof and numerical illustration of the Markov property for a Hawkes process 
with exponential decay kernel.

## Mathematical Background

A Hawkes process is a self-exciting point process whose intensity takes the form:

λ(t) = μ + α ∑_{t_i < t} e^{-β(t - t_i)}

With an exponential kernel, the intensity process (λ(t), t ≥ 0) is itself a 
continuous-time Markov process. This is a classical but important structural 
result: it allows stochastic control and filtering techniques to be applied to 
Hawkes-driven models, which underpins much of the market microstructure 
literature (e.g. Hawkes-based order flow models).

## Contents

- `project_hawkes.ipynb` — analytic proof of the Markov property via the 
  intensity SDE representation, with simulation of sample paths and 
  verification of the Markov structure numerically.

## Key Result

The Markov property holds because with exponential kernel, the intensity 
satisfies:

dλ(t) = -β(λ(t) - μ) dt + α dN(t)

which is a jump-diffusion SDE driven by the process itself, making (λ(t)) 
adapted and Markovian.

## Dependencies

```bash
pip install numpy matplotlib scipy
```

## Context

Produced as part of coursework at Institut Polytechnique de Paris (M1 Applied 
Mathematics). Related to ongoing research on Volterra–Hawkes stochastic 
volatility models at CMAP, École Polytechnique.
