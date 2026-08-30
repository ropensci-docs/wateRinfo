# Check the from/to/period arguments

Handle the information of provided date information on the period and
provide feedback to the user. Valid combinations of the arguments are:
from/to, from/period, to/period, period, from

## Usage

``` r
parse_period(from = NULL, to = NULL, period = NULL)
```

## Arguments

- from:

  string representing date of datetime object

- to:

  string representing date of datetime object

- period:

  input string according to format required by waterinfo

## Value

list with the relevant period/date information

## See also

check_period_format
