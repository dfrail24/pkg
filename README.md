
pkg
===

[![Build Status](https://travis-ci.org/dfrail24/pkg.svg?branch=master)](https://travis-ci.org/dfrail24/pkg)

The goal of pkg is to allow the user to easily import FARS data into R and create simple summary statistics/visualization from the imported data.

Installation
------------

You can install pkg from github with:

``` r
# install.packages("devtools")
devtools::install_github("dfrail24/pkg")
```

Example
-------

This is a basic example which shows you how to solve a common problem:

``` r
## basic example code

# Create filename
filename <- pkg::make_filename(2013)

# Read the file
pkg::fars_read(filename)
#> # A tibble: 30,202 x 50
#>    STATE ST_CASE VE_TOTAL VE_FORMS PVH_INVL  PEDS PERNOTMVIT PERMVIT
#>    <int>   <int>    <int>    <int>    <int> <int>      <int>   <int>
#>  1     1   10001        1        1        0     0          0       8
#>  2     1   10002        2        2        0     0          0       2
#>  3     1   10003        1        1        0     0          0       1
#>  4     1   10004        1        1        0     0          0       3
#>  5     1   10005        2        2        0     0          0       3
#>  6     1   10006        2        2        0     0          0       3
#>  7     1   10007        1        1        0     0          0       1
#>  8     1   10008        2        2        0     0          0       2
#>  9     1   10009        1        1        0     0          0       1
#> 10     1   10010        2        2        0     0          0       4
#> # ... with 30,192 more rows, and 42 more variables: PERSONS <int>,
#> #   COUNTY <int>, CITY <int>, DAY <int>, MONTH <int>, YEAR <int>,
#> #   DAY_WEEK <int>, HOUR <int>, MINUTE <int>, NHS <int>, ROAD_FNC <int>,
#> #   ROUTE <int>, TWAY_ID <chr>, TWAY_ID2 <chr>, MILEPT <int>,
#> #   LATITUDE <dbl>, LONGITUD <dbl>, SP_JUR <int>, HARM_EV <int>,
#> #   MAN_COLL <int>, RELJCT1 <int>, RELJCT2 <int>, TYP_INT <int>,
#> #   WRK_ZONE <int>, REL_ROAD <int>, LGT_COND <int>, WEATHER1 <int>,
#> #   WEATHER2 <int>, WEATHER <int>, SCH_BUS <int>, RAIL <chr>,
#> #   NOT_HOUR <int>, NOT_MIN <int>, ARR_HOUR <int>, ARR_MIN <int>,
#> #   HOSP_HR <int>, HOSP_MN <int>, CF1 <int>, CF2 <int>, CF3 <int>,
#> #   FATALS <int>, DRUNK_DR <int>

# Create a map
pkg::fars_map_state(1, 2013)
```

![](README-example-1.png)
