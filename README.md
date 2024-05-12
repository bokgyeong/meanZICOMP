# Supplemental Code for "Fast Bayesian Inference for Spatial Mean-Parameterized Conway-Maxwell-Poisson Models"
Authors: Bokgyeong Kang, John Hughes, and Murali Haran

We provide instructions for fitting spatial mean-parameterized Conway-Maxwell-Poisson (mean-COMP) and zero-inflated mean-parameterized Conway-Maxwell-Poisson (mean-ZICOMP) regression models. 

## Required Packages:
The code has been tested with R version 4.2.2, "Innocent and Trusting."  The following R packages must be installed before the code will run successfully:

- `Rcpp`
- `RcppArmadillo`
- `sitmo`
- `akima`
- `mpcmp`
- `qrng`
- `ngspatial`
- `foreach`
- `coda`
- `batchmeans`
- `tidyverse`

The `mpcmp` can be installed from [GitHub](https://github.com/thomas-fung/mpcmp):
```s
require(devtools)
devtools::install_github("thomas-fung/mpcmp")
```

## Spatial mean-COMP regression model
Before running any code, ensure the required R packages have been installed. Set the R working directory to `/scomp`.

### Pre-computing for spline approximation
`/scomp/appx.R`
- Generate a number of particles over $\Psi = [\log(0.01), \log(\mu_{\max})] \times [0.01, \nu_{\max}]$ and find $\lambda(\mu, \nu)$ for each particle using the Newtwon-Raphson algorithm
- This step corresponds to Section 3.1 of the manuscript
- All components are saved in file `/scomp/appx/set.RData`

### Simulate data
`/scomp/data.R`
- Generate data from the spatial mean-COMP regression model
- All components are saved in file `/scomp/data/sim.RData`
