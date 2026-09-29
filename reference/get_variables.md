# Get list of variables for a given station

Get list of variables for a given station

## Usage

``` r
get_variables(station_no, token = NULL)
```

## Format

A data.frame with 6 variables:

- station_name:

  Official name of the measurement station.

- station_no:

  Station ID as provided on the waterinfo.be website.

- ts_id:

  Unique timeseries identifier to access time series data corresponding
  to a combination of the station, measured variable and frequency.

- ts_name:

  Timeseries identifier description name as provided by
  \`waterinfo.be\`.

- parametertype_name:

  Measured variable description.

- stationparameter_name:

  Station specific variable description.

The URL of the specific request is provided as a comment attribute to
the returned data.frame. Use `comment(df)` to get the request URL.

## Arguments

- station_no:

  'stations-nummer' as it appears on the download page of
  [waterinfo.be](https://www.waterinfo.be/default.aspx?path=NL/Rapporten/Downloaden)

- token:

  token to use with the call (optional, can be retrieved via
  [`get_token`](https://docs.ropensci.org/wateRinfo/reference/get_token.md))

## Value

data.frame with the station_name, station_no, ts_id, ts_name and
parametertype_name for each of the variables for this station.

## Examples

``` r
variables_overpelt <- get_variables("ME11_002")
#> Use datasource: 1 for data requests of this station!
```
