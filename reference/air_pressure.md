# Air pressure data of January 1st, 2017

A dataset compiled by downloading 1 day of air pressure data for the
available stations of Waterinfo.be

## Usage

``` r
air_pressure
```

## Format

A data frame with 710 rows and 13 variables:

- ts_id:

  identifier of the downloaded time serie

- Timestamp:

  datetime

- Value:

  measured value of the variable

- Quality Code:

  Quality code of the measurement

- station_latitude:

  latitude coordinate

- station_longitude:

  longitude coordinate

- station_id:

  identifier of the measurement station

- station_no:

  short code name of the measurement station

- station_name:

  full name of the measurement station

- stationparameter_name:

  parameter name on station level

- parametertype_name:

  parameter type name

- ts_unitsymbol:

  unit of the variable

- dataprovider:

  provider of the time series value

## Source

<https://www.waterinfo.be/>
