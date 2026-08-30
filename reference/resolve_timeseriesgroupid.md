# Get timeseriesgroupID for a supported variable

Translate the usage of available variables to the corresponding
timeseriesgroupID, based on the provided lookup table from VMM

## Usage

``` r
resolve_timeseriesgroupid(variable_name, frequency = "15min")
```

## Arguments

- variable_name:

  valid variable name, supported by VMM API

- frequency:

  valid frequency for the given variable

## Value

list containing the `timeseriesgroup_id` of the variable frequency
combination

## Details

Remark that this information is NOT based on a query, but on information
provided by the package itself to make variable names more readable

The lookup table is provided as external data of the package, see
inst/extdata

## Examples

``` r
resolve_timeseriesgroupid("rainfall", "15min")
#> $timeseriesgroup_id
#> [1] 192896
#> 
```
