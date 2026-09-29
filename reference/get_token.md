# Get waterinfo Token

Retrieve a fresh waterinfo token. A token is not required to get
started, see Details section for more information.

## Usage

``` r
get_token(
  client = NULL,
  client_id = NULL,
  client_secret = NULL,
  token_url = "http://download.waterinfo.be/kiwis-auth/token"
)

is.expired(token)

expires.in(token)
```

## Arguments

- client:

  base64 encoded client containing the client id and client secret,
  seperated by :

- client_id:

  client id string

- client_secret:

  client secret string

- token_url:

  url to get the token from

- token:

  a token object

## Value

An object of class token containing the token string with the token_url,
token type and moment of expiration as attributes.

## Details

Notice you do not need to get a token right away to download data. For
limited and irregular downloads, a token will not be required. The
amount of data downloaded from waterinfo.be is limited via a credit
system. When you require more extended data requests, request a download
token.

Either client or client_id and client_secret need to be passed as
arguments. If provided, client is always used. Tokens remain valid for
24 hours, after which a fresh one must be acquired. To limit load on the
server, token objects should be reused as much as possible until
expiration in stead of creating fresh ones for each call.

The client_id and client_secret provided in the examples are for test
purposes, get your very own client via <hydrometrie@waterinfo.be>.

## Examples

``` r
# Get token via client_id and client_secret
client_id <- '32dceece-826c-4b98-9c2d-b16978f0ca6a'
client_secret <- '4ada871a-9528-4b4d-bfd5-b570ce8f4d2d'
my_token <- get_token(client_id = client_id,client_secret = client_secret)
print(my_token)
#> Token:
#> eyJhbGciOiJSUzUxMiJ9.eyJqdGkiOiJiMWM4NWE1Zi02NTY0LTQzYjgtOGM2MS03MjI2ZTJiOTk4N2YiLCJpYXQiOjE3OTA2NzAwMTUsImlzcyI6Imh0dHA6Ly92cC10c21jYWxjMDE6ODA4MC9LaVdlYlBvcnRhbC9hdXRoLyIsImF1ZCI6IjMyZGNlZWNlLTgyNmMtNGI5OC05YzJkLWIxNjk3OGYwY2E2YSIsImV4cCI6MTc5MDc1NjQxNX0.KRlgj2BXGGWlezRhQhFXpV2WvhXt0M4d_n9EASH6AdI7zwuyrnoBc4osSxFW6vATEN75ByujQz3mFH_tmC_Bcge3DA8cSXLGWlNG2uUISVMOUJSwqMFj9_je-vW113s9zt1_HLqrUr7jcyyaW31BbPvky5XSSyYdg3zoELBcqPfEo9H4W2U0ZXOKz7eSpyRtPFhn-cD5gdJYciL5cb6z6KnGf4MNQD0ZW2XOTuAQXEhDDujkmOJEGDYAaXABVHkBYhQKzxbu9MAXwWu_WEjCwAhXh_5hTa4gBu8mX8vCVa5ErOLaLHTwYsTvjLEBXihEJveEn5fRN95gvBcRYnpLZg
#> 
#> Attributes:
#>  url: http://download.waterinfo.be/kiwis-auth/token
#>  type: Bearer
#>  expires: 2026-09-30 08:20:15 UTC

# get token via client
client <- paste0('MzJkY2VlY2UtODI2Yy00Yjk4LTljMmQtYjE2OTc4ZjBjYTZhOjRhZGE4',
                'NzFhLTk1MjgtNGI0ZC1iZmQ1LWI1NzBjZThmNGQyZA==')
my_token <- get_token(client = client)
print(my_token)
#> Token:
#> eyJhbGciOiJSUzUxMiJ9.eyJqdGkiOiJhYzg3MGQzZS03ZmVhLTQ0ZTMtOGRlNy1kOTNlMDc0Y2JjOGYiLCJpYXQiOjE3OTA2NzAwMTUsImlzcyI6Imh0dHA6Ly92cC10c21jYWxjMDE6ODA4MC9LaVdlYlBvcnRhbC9hdXRoLyIsImF1ZCI6IjMyZGNlZWNlLTgyNmMtNGI5OC05YzJkLWIxNjk3OGYwY2E2YSIsImV4cCI6MTc5MDc1NjQxNX0.GVu1PUlxi8s69aZbCJ8t8t7wYe_8E5TlNDbzrwWN9qSUbH4aPRn-wq0j2r95KKone_1V5FEY7F2qxjMxhUtoX2zF7QPZ9KormydwdedmlSpQvimkyv6IKbCdB_01j8CZcqRYT6RsnjF6qCqY2dudwZg8Ch7s54kB9eqFuqKSE1GfjV9x-jLbuC5gCk9p8evEGYbYZcz48rtXymoWRj0JKgHQIjgzNASaf73EnTj8widWjFgkuR1c1b-SbrbC2l_8igV49VbLS7OdaRP2FTV0BXGscRkqZm5Bmaimn3TXUEm4r2M75UYY6hIbIv8jIcPapErMVxMxLyaVSZ6R-HLHuQ
#> 
#> Attributes:
#>  url: http://download.waterinfo.be/kiwis-auth/token
#>  type: Bearer
#>  expires: 2026-09-30 08:20:15 UTC
is.expired(my_token)
#> [1] FALSE
expires.in
#> function (token) 
#> {
#>     UseMethod("expires.in", token)
#> }
#> <bytecode: 0x5643e0c1b428>
#> <environment: namespace:wateRinfo>

# Use the token when requesting for data (i.e. get_* functions), e.g.
get_stations(variable_name = "verdamping_monteith", token = my_token)
#>      ts_id station_latitude station_longitude station_id station_no
#> 1 94310042         51.02263          2.970584      12206   ME01_003
#> 2 94544042         51.20300          5.439589      12213   ME11_002
#> 3 94516042         50.73795          5.141976      12211   ME09_012
#> 4 94530042         51.16224          4.845708      12212   ME10_011
#> 5 94488042         50.86149          3.411318      12209   ME05_019
#> 6 94460042         51.27226          3.728299      12207   ME03_017
#> 7 94474042         51.24379          4.266912      12208   ME04_001
#> 8 94502042         50.88663          4.094898      12210   ME07_006
#>              station_name stationparameter_name parametertype_name
#> 1               Zarren_ME                   pET                PET
#> 2             Overpelt_ME                   pET                PET
#> 3 Niel-bij-St.-Truiden_ME                   pET                PET
#> 4            Herentals_ME                   pET                PET
#> 5              Waregem_ME                   pET                PET
#> 6            Boekhoute_ME                   pET                PET
#> 7              Melsele_ME                   pET                PET
#> 8           Liedekerke_ME                   pET                PET
#>   ts_unitsymbol dataprovider
#> 1            mm          VMM
#> 2            mm          VMM
#> 3            mm          VMM
#> 4            mm          VMM
#> 5            mm          VMM
#> 6            mm          VMM
#> 7            mm          VMM
#> 8            mm          VMM
```
