
<!-- README.md is generated from README.Rmd. Please edit that file -->

# bang

[![AppVeyor Build
Status](https://ci.appveyor.com/api/projects/status/github/paulnorthrop/bang?branch=master&svg=true)](https://ci.appveyor.com/project/paulnorthrop/bang)
[![R-CMD-check](https://github.com/paulnorthrop/bang/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/paulnorthrop/bang/actions/workflows/R-CMD-check.yaml)
[![Coverage
Status](https://codecov.io/github/paulnorthrop/bang/coverage.svg?branch=master)](https://app.codecov.io/github/paulnorthrop/bang?branch=master)
[![CRAN_Status_Badge](https://www.r-pkg.org/badges/version/bang)](https://cran.r-project.org/package=bang)
[![Downloads
(monthly)](https://cranlogs.r-pkg.org/badges/bang?color=brightgreen)](https://cran.r-project.org/package=bang)
[![Downloads
(total)](https://cranlogs.r-pkg.org/badges/grand-total/bang?color=brightgreen)](https://cran.r-project.org/package=bang)

### Bayesian Analysis, No Gibbs

### What does bang do?

Provides functions for the Bayesian analysis of some simple
commonly-used models, without using Markov Chain Monte Carlo (MCMC)
methods such as Gibbs sampling. The ‘rust’ package
<https://cran.r-project.org/package=rust> is used to simulate a random
sample from the required posterior distribution, using the
ratio-of-uniforms method. Currently three conjugate hierarchical models
are available: beta-binomial, gamma-Poisson and a 1-way Analysis of
Variance (ANOVA). Advantages of the ratio-of-uniforms method over MCMC
in this context are that the user is not required to set tuning
parameters nor to monitor convergence and a random posterior sample is
produced.

### A simple example

The `hef` function samples from the posterior distribution of the
parameters of certain hierarchical exponential family models. The
following code performs essentially the same analysis of the rat tumor
data using a beta-binomial hierarchical model that appears in Section
5.3 of Gelman, A., Carlin, J. B., Stern, H. S. Dunson, D. B., Vehtari,
A. and Rubin, D. B. (2014) Bayesian Data Analysis. Chapman & Hall / CRC.
<http://www.stat.columbia.edu/~gelman/book/>.

``` r
library(bang)
rat_res <- hef(model = "beta_binom", data = rat)
plot(rat_res)
```

### Installation

To get the current released version from CRAN:

``` r
install.packages("bang")
```
