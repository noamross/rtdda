
<!-- README.md is generated from README.Rmd. Please edit that file -->
tdda
====

This package wraps the [tdda python module](https://github.com/tdda/tdda), which generates automatic *constraints* on data sets given examples. More info can be found on [the TDDA blog](http://www.tdda.info/introducing-rexpy-automatic-discovery-of-regular-expressions).

This is an extremely alpha package wrapping some pretty beta code, so use with caution!

Installation
------------

You can install tdda from github with:

``` r
# install.packages("devtools")
devtools::install_github("noamross/tdda")
```

Since tdda calls python code via the [**SnakeCharmR**](https://github.com/asieira/SnakeCharmR) package, you need Python &gt;= 2.7 and a build environment to install it.

Usage
-----

Currently only one function, `rex_extract()` is implemented, for regular expression generation from a character vector:

``` r
library(tdda)
rex_extract(c("EH1", "7JQ", "WC1", "4AA", "G2", "3PQ"))
#> [1] "^[A-Za-z0-9]{2,3}$"
rex_extract(c("123-AA-971", "12-DQ-802", "198-AA-045", "1-BA-834"))
#> [1] "^\\d{1,3}\\-[A-Z]{2}\\-\\d{3}$"
```