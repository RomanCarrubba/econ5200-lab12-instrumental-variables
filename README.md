# econ5200-lab12-instrumental-variables

# Instrumental Variables: Weak Instruments, Compliers and the Exclusion Restriction

## Objective

I wanted to see how instrumental variables estimates behave when the instrument is weak or slightly invalid, and to check them on a real schooling example.

## Methodology

- Simulated a weak instrument with a true effect of 1.0, where OLS is biased upward, and compared the OLS and 2SLS estimates across many repeated draws.
- Recorded the first-stage F statistic for each draw and looked at how the estimates behaved at the median F.
- Looked at how often a statistically significant 2SLS estimate landed far from the true value.
- Replicated Card's (1995) schooling example, using college proximity as the instrument, and compared OLS with 2SLS.
- Added a small direct effect of the instrument on the outcome, which breaks the exclusion restriction, and measured how far it moved the 2SLS estimate.
- Wrote my own two-stage least squares function from two OLS regressions and checked it against the `linearmodels` package.

## Key Findings

- **Weak instrument simulation:** The true effect was 1.0 and OLS was biased upward. At a median first-stage F of 21.4, the median 2SLS estimate was 1.194, against a median OLS estimate of 2.009. A significant 2SLS estimate was usually far from the truth, so significance did not tell me the estimate was close.
- **Card (1995) replication:** The first-stage F was 16.7. The OLS return to schooling was 0.0740 and the 2SLS return was 0.1323.
- **Exclusion restriction:** A small direct effect of the instrument on the outcome moved the 2SLS estimate by 0.111 for every additional 0.05 in the direct effect.
- **Hand-written 2SLS:** My function and `linearmodels` gave matching estimates.
