# VMM supported timeseriesgroups variables

Provide list of VMM supported variables in the timeseriesgroupID in
either dutch or english

## Usage

``` r
supported_variables(language = "nl")
```

## Arguments

- language:

  char `nl` (dutch) or `en` (english) variable names

## Value

data.frame containing the variable names in either english or dutch

## Examples

``` r
# Request supported variables in Dutch
supported_variables("nl")
#>              variable_nl
#> 1                 afvoer
#> 6      bodem_verzadiging
#> 7            bodem_vocht
#> 8   dauwpunt_temperatuur
#> 9       grondtemperatuur
#> 10           grondwarmte
#> 11            instraling
#> 12             luchtdruk
#> 13 luchttemperatuur175cm
#> 14              neerslag
#> 20 relatieve_vochtigheid
#> 21   verdamping_monteith
#> 25     verdamping_penman
#> 29         watersnelheid
#> 34            waterstand
#> 39      watertemperatuur
#> 40          windrichting
#> 41          windsnelheid

# Request supported variables in English
supported_variables("en")
#>              variable_en
#> 1              discharge
#> 6        soil_saturation
#> 7          soil_moisture
#> 8  dew_point_temperature
#> 9     ground_temperature
#> 10           ground_heat
#> 11            irradiance
#> 12          air_pressure
#> 13 air_temperature_175cm
#> 14              rainfall
#> 20     relative_humidity
#> 21  evaporation_monteith
#> 25    evaporation_penman
#> 29        water_velocity
#> 34           water_level
#> 39     water_temperature
#> 40        wind_direction
#> 41            wind_speed
```
