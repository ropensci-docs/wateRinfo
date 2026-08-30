# Check period string format

Check if the format of the period is conform the specifications of VMM

## Usage

``` r
check_period_format(period_string)
```

## Arguments

- period_string:

  input string according to format required by waterinfo: The period
  string is provided as P#Y#M#DT#H#M#S, with P defines \`Period\`, each
  \# is an integer value and the codes define the number of... Y - years
  M - months D - days T required if information about sub-day resolution
  is present H - hours D - days M - minutes S - seconds Instead of D
  (days), the usage of W - weeks is possible as well Examples of valid
  period strings: P3D, P1Y, P1DT12H, PT6H, P1Y6M3DT4H20M30S.

## Value

str period string itself if valid

## Examples

``` r
check_period_format("P2DT6H") # period of 2 days and 6 hours
#> [1] "P2DT6H"
check_period_format("P3D") # period of 3 days
#> [1] "P3D"
```
