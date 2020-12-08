
<!-- README.md is generated from README.Rmd. Please edit that file -->

# logitr <a href='https://jhelvy.github.io/logitr/'><img src='man/figures/logitr-hex.png' align="right" height="139" /></a>

<!-- badges: start -->

[![Lifecycle:
experimental](https://img.shields.io/badge/lifecycle-maturing-blue.svg)](https://www.tidyverse.org/lifecycle/#maturing)
[![CRAN
status](https://www.r-pkg.org/badges/version/logitr)](https://CRAN.R-project.org/package=logitr)
<!-- badges: end -->

**logitr** estimates multinomial (MNL) and mixed logit (MXL) models in
R. Models can be estimated using “Preference” space or
“Willingness-to-pay” (WTP) space [utility
parameterizations](https://jhelvy.github.io/logitr/articles/utility_models.html).
The latest version includes support for:

  - Homogeneous multinomial logit (MNL) models
  - Heterogeneous mixed logit (MXL) models (with normal and log-normal
    parameter distributions).
  - Preference space utility parameterization.
  - WTP space utility parameterization.
  - An option to run a multistart optimization loop that uses different
    random starting points in each iteration (useful for non-convex
    problems like MXL models or models with WTP space
    parameterizations).
  - Computing and comparing WTP from both preference space and WTP space
    models.
  - Simulating the expected shares of a set of alternatives using an
    estimated model.

Note: MXL models assume uncorrelated heterogeneity covariances and are
estimated using maximum simulated likelihood based on the algorithms in
[Kenneth Train’s](http://eml.berkeley.edu/~train/) book [*Discrete
Choice Methods with Simulation, 2nd Edition (New York: Cambridge
University Press, 2009)*](http://eml.berkeley.edu/books/choice2.html).

View the [basic
usage](https://jhelvy.github.io/logitr/articles/basic_usage.html) page
for details on how to use **logitr** to estimate models.

## Installation

The current version is not yet on CRAN, but you can install it from
Github using the **devtools** library:

``` r
devtools::install_github("jhelvy/logitr")
```

Load the library with:

``` r
library(logitr)
```

## Required Libraries

**logitr** requires the
[**nloptr**](https://cran.r-project.org/web/packages/nloptr/index.html)
library. This is because `nloptr()` allows for both the objective and
gradient functions to be computed in a single function. This speeds up
computation time considerably because both the objective and gradient
functions require many of the same calculations (e.g. computing
probabilities).

## Author, Version, and License Information

  - Author: *John Paul Helveston*
    [www.jhelvy.com](http://www.jhelvy.com/)
  - Date First Written: *Sunday, September 28, 2014*
  - Most Recent Update: December 07 2020
  - License:
    [MIT](https://github.com/jhelvy/logitr/blob/master/LICENSE.md)
  - [Latest Release](https://github.com/jhelvy/logitr/releases/latest):
    0.0.5

## Citation Information

If you use this package for in a publication, I would greatly appreciate
it if you cited it - you can get the citation by typing
`citation("logitr")` into R:

``` r
citation("logitr")
#> 
#> To cite logitr in publications use:
#> 
#>   John Paul Helveston (2020). logitr: Random utility logit models with
#>   preference and willingness to pay space parameterizations.
#> 
#> A BibTeX entry for LaTeX users is
#> 
#>   @Manual{,
#>     title = {logitr: Random utility logit models with preference and willingness to pay space parameterizations},
#>     author = {John Paul Helveston},
#>     year = {2020},
#>     note = {R package version 0.0.5},
#>     url = {https://jhelvy.github.io/logitr/},
#>   }
```
