# VMM supported timeseriesgroups frequencies

Provide list of VMM supported frequencies for a given timeseriesgroupID
in either dutch or english

## Usage

``` r
supported_frequencies(variable_name)
```

## Arguments

- variable_name:

  char name of a valid variable in either dutch or english

## Examples

``` r
supported_frequencies('rainfall')
#> [1] "1min"  "15min" "hour"  "day"   "month" "year" 
```
