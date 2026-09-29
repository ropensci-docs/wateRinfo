# Package index

## Main download functionalities

Functions for downloading stations, variables and time series

- [`get_stations()`](https://docs.ropensci.org/wateRinfo/reference/get_stations.md)
  : Get list of stations for a variable
- [`get_variables()`](https://docs.ropensci.org/wateRinfo/reference/get_variables.md)
  : Get list of variables for a given station
- [`get_timeseries_tsid()`](https://docs.ropensci.org/wateRinfo/reference/get_timeseries_tsid.md)
  : Download timeseries data from waterinfo.be

## Check the VMM supported variables

The supported variables can be requested on timeseriesgroupID

- [`supported_frequencies()`](https://docs.ropensci.org/wateRinfo/reference/supported_frequencies.md)
  : VMM supported timeseriesgroups frequencies
- [`supported_variables()`](https://docs.ropensci.org/wateRinfo/reference/supported_variables.md)
  : VMM supported timeseriesgroups variables
- [`is_supported_variable()`](https://docs.ropensci.org/wateRinfo/reference/is_supported_variable.md)
  : Check if variable is supported by VMM ts group id

## Resolving of identifiers to names

- [`resolve_timeseriesgroupid()`](https://docs.ropensci.org/wateRinfo/reference/resolve_timeseriesgroupid.md)
  : Get timeseriesgroupID for a supported variable
- [`resolve_datasource()`](https://docs.ropensci.org/wateRinfo/reference/resolve_datasource.md)
  : Define the datasource using the station number

## Date handling support functions

- [`isdatetime()`](https://docs.ropensci.org/wateRinfo/reference/isdatetime.md)
  : Check if the string input can be converted to a date, provides FALSE
  or date
- [`check_date_format()`](https://docs.ropensci.org/wateRinfo/reference/check_date_format.md)
  : Check if the date can be parsed to a datetime object in R
- [`check_period_format()`](https://docs.ropensci.org/wateRinfo/reference/check_period_format.md)
  : Check period string format
- [`parse_period()`](https://docs.ropensci.org/wateRinfo/reference/parse_period.md)
  : Check the from/to/period arguments

## Token handling

- [`get_token()`](https://docs.ropensci.org/wateRinfo/reference/get_token.md)
  [`is.expired()`](https://docs.ropensci.org/wateRinfo/reference/get_token.md)
  [`expires.in()`](https://docs.ropensci.org/wateRinfo/reference/get_token.md)
  : Get waterinfo Token

## Underlying API request function

- [`call_waterinfo()`](https://docs.ropensci.org/wateRinfo/reference/call_waterinfo.md)
  : http call to waterinfo.be
- [`print(`*`<waterinfo_api>`*`)`](https://docs.ropensci.org/wateRinfo/reference/print.waterinfo_api.md)
  : Custom print function of the API request response

## Example datasets

- [`liedekerke`](https://docs.ropensci.org/wateRinfo/reference/liedekerke.md)
  : Soil moisture data of Liedekerke, January 2017
- [`air_pressure`](https://docs.ropensci.org/wateRinfo/reference/air_pressure.md)
  : Air pressure data of January 1st, 2017
