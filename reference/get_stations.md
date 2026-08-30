# Get list of stations for a variable

For a given timeseriesgroup (variable), provide a list of measurement
stations providing data. An overview of the variables is provided by the
function
[`supported_variables`](https://docs.ropensci.org/wateRinfo/reference/supported_variables.md).

## Usage

``` r
get_stations(variable_name = NULL, frequency = "15min", token = NULL)
```

## Format

A data.frame with 10 variables:

- ts_id:

  Unique timeseries identifier to access time series data corresponding
  to a combination of the station, measured variable and frequency.

- station_latitude:

  Latitude coordinates of the station (WGS84)

- station_longitude:

  Longitude coordinates of the station (WGS84)

- station_id:

  Identifier of the station as used in the waterinfo backend

- station_no:

  Station ID as provided on the waterinfo.be website.

- station_name:

  Official name of the measurement station.

- stationparameter_name:

  Station specific variable description.

- parametertype_name:

  Measured variable description.

- ts_unitsymbol:

  Unit of the variable.

- dataprovider:

  Data provider of the time series data.

The URL of the specific request is provided as a comment attribute to
the returned data.frame. Use `comment(df)` to get the request URL.

## Arguments

- variable_name:

  char valid nam of available variable as timeseriesgroup

- frequency:

  char valid frequency for the given variable, for most variables, the
  15min frequency is available

- token:

  token to use with the call (optional, can be retrieved via
  [`get_token`](https://docs.ropensci.org/wateRinfo/reference/get_token.md))

## Value

data.frame with an overview of the available stations for the requested
variable

## Details

For the moment, this only works for measurement stations of VMM (meetnet
1), and stations from other measurement data sources are not included in
the list

## See also

supported_variables

## Examples

``` r
get_stations('irradiance')
#>      ts_id station_latitude station_longitude station_id station_no
#> 1 78845042         51.27226          3.728299      12207   ME03_017
#> 2 78879042         50.86149          3.411318      12209   ME05_019
#> 3 78947042         51.20300          5.439589      12213   ME11_002
#> 4 78913042         50.73795          5.141976      12211   ME09_012
#> 5 78862042         51.24379          4.266912      12208   ME04_001
#> 6 78896042         50.88663          4.094898      12210   ME07_006
#> 7 78930042         51.16224          4.845708      12212   ME10_011
#>              station_name stationparameter_name parametertype_name
#> 1            Boekhoute_ME                   Rad                 Rn
#> 2              Waregem_ME                   Rad                 Rn
#> 3             Overpelt_ME                   Rad                 Rn
#> 4 Niel-bij-St.-Truiden_ME                   Rad                 Rn
#> 5              Melsele_ME                   Rad                 Rn
#> 6           Liedekerke_ME                   Rad                 Rn
#> 7            Herentals_ME                   Rad                 Rn
#>   ts_unitsymbol dataprovider
#> 1          W/m²          VMM
#> 2          W/m²          VMM
#> 3          W/m²          VMM
#> 4          W/m²          VMM
#> 5          W/m²          VMM
#> 6          W/m²          VMM
#> 7          W/m²          VMM
get_stations('soil_saturation')
#>        ts_id station_latitude station_longitude station_id station_no
#> 1  241832042         51.08705          3.656799     307321    B03_005
#> 2  241952042         51.24379          4.266912     307312    B04_001
#> 3  243519042         51.24379          4.266912     307312    B04_001
#> 4  242192042         51.29507          4.910008     307331    B10_042
#> 5  243639042         51.29507          4.910008     307331    B10_042
#> 6  242072042         50.80630          4.969030     307329    B09_032
#> 7  243444042         50.87758          4.666340     307327    B08_031
#> 8  255019042         50.88663          4.094898     307314    B07_006
#> 9  241922042         51.22551          3.007397     307319    B02_008
#> 10 242162042         51.38797          4.705126     307332    B11_007
#> 11 243414042         51.28378          3.271242     307320    B02_030
#> 12 243534042         51.20300          5.439589     307317    B11_002
#> 13 243459042         50.80959          5.674667     307333    B11_024
#> 14 241892042         50.82688          2.673866     307318    B01_037
#> 15 255017042         51.27226          3.728299     307311    B03_017
#> 16 241772042         51.05209          5.120756     307330    B09_034
#> 17 242132042         51.16224          4.845708     307316    B10_011
#> 18 242012042         51.28378          3.271242     307320    B02_030
#> 19 243579042         50.93779          3.171750     307322    B05_039
#> 20 242222042         51.20300          5.439589     307317    B11_002
#> 21 243384042         51.03254          4.510400     307326    B08_018
#> 22 241676042         51.03254          4.510400     307326    B08_018
#> 23 241862042         50.90567          3.655040     307324    B06_040
#> 24 243429042         51.16224          4.845708     307316    B10_011
#> 25 255484042         50.88663          4.094898     307314    B07_006
#> 26 241742042         50.87758          4.666340     307327    B08_031
#> 27 243669042         50.90567          3.655040     307324    B06_040
#> 28 242102042         50.80959          5.674667     307333    B11_024
#> 29 243565042         50.93779          3.171750     307322    B05_039
#> 30 251706042         51.27226          3.728299     307311    B03_017
#> 31 241694042         51.00600          4.092621     307325    B07_022
#> 32 243594042         51.05209          5.120756     307330    B09_034
#>     station_name    stationparameter_name parametertype_name ts_unitsymbol
#> 1  Vinderhoute_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 2      Melsele_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 3      Melsele_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#> 4    Vosselaar_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 5    Vosselaar_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#> 6       Tienen_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 7     Heverlee_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#> 8   Liedekerke_B Bodemverzadiging(0-70cm)    Soil Saturation             %
#> 9   Klemskerke_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 10    Loenhout_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 11     Dudzele_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#> 12    Overpelt_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#> 13       Kanne_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#> 14   Poperinge_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 15   Boekhoute_B Bodemverzadiging(0-70cm)    Soil Saturation             %
#> 16 Tessenderlo_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 17   Herentals_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 18     Dudzele_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 19   Roeselare_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#> 20    Overpelt_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 21   Bonheiden_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#> 22   Bonheiden_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 23      Zingem_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 24   Herentals_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#> 25  Liedekerke_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 26    Heverlee_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 27      Zingem_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#> 28       Kanne_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 29   Roeselare_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 30   Boekhoute_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 31 Denderbelle_B Bodemverzadiging(0-10cm)    Soil Saturation             %
#> 32 Tessenderlo_B Bodemverzadiging(0-60cm)    Soil Saturation             %
#>    dataprovider
#> 1           VMM
#> 2           VMM
#> 3           VMM
#> 4           VMM
#> 5           VMM
#> 6           VMM
#> 7           VMM
#> 8           VMM
#> 9           VMM
#> 10          VMM
#> 11          VMM
#> 12          VMM
#> 13          VMM
#> 14          VMM
#> 15          VMM
#> 16          VMM
#> 17          VMM
#> 18          VMM
#> 19          VMM
#> 20          VMM
#> 21          VMM
#> 22          VMM
#> 23          VMM
#> 24          VMM
#> 25          VMM
#> 26          VMM
#> 27          VMM
#> 28          VMM
#> 29          VMM
#> 30          VMM
#> 31          VMM
#> 32          VMM
```
