
<!-- README.md is generated from README.Rmd. Please edit that file -->
lmhyp
=====

This package provides an easy way to test hypotheses about continous predictors in multiple regression. A hypothesis may for example be that variable1 and variable2 both have a positive correlation with the outcome variable, but that the correlation of variable1 is stronger. This package enables formal testing of such hypotheses and is particularly useful for testing multiple contradicting hypotheses.

Basic example
-------------

``` r
library(lmhyp)

###Standardize variables and fit a linear model with lm
dt <- as.data.frame(scale(mtcars[, c(1, 3:4, 6)]))
fit <- lm(mpg ~ disp + hp + wt, data = dt)

###Define hypotheses based on theory and test them, separated by ;
hyp <- "wt > disp; wt < disp"
test_hyp(fit, hyp)
#> Hypotheses:
#> 
#>   H1:   "wt>disp"
#>   H2:   "wt<disp"
#> 
#> Posterior probability of each hypothesis (rounded):
#> 
#>   H1:   0.0568
#>   H2:   0.9432
```

Installation
------------

You can install lmhyp from github with:

``` r
# install.packages("devtools")
devtools::install_github("Jaeoc/lmhyp")
```
