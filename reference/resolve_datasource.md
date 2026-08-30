# Define the datasource using the station number

Using the 'stations-nummer' as provided on
[waterinfo.be](https://www.waterinfo.be/default.aspx?path=NL/Rapporten/Downloaden),
this function tries to identify the datasource to use for the particular
variable

## Usage

``` r
resolve_datasource(station_no)
```

## Arguments

- station_no:

  'stations-nummer' as it appears on the download page of
  [waterinfo.be](https://www.waterinfo.be/default.aspx?path=NL/Rapporten/Downloaden)

## Value

integer 1 for VMM, 4 for other 'meetnetten' (HIC,...)

## Details

Notice that VMM did not provide this in the official documentation, but
this has just been derived by checking the API response as such. A more
automated and less hard-coded approach would be beneficial, but this
data is not available at the moment.

## Examples

``` r
resolve_datasource('akl03e-1066')
#> [1] 4
resolve_datasource('K07_OM421')
#> [1] 1
```
