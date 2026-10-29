# http call to waterinfo.be

General call used to request information and data from waterinfo.be,
providing error handling and json parsing

## Usage

``` r
call_waterinfo(query, base_url = "vmm", token = NULL)
```

## Arguments

- query:

  list of query options to be used together with the base string

- base_url:

  str vmm \| hic \| pro, default download defined

- token:

  token to use with the call (optional, can be retrieved via
  [`get_token`](https://docs.ropensci.org/wateRinfo/reference/get_token.md))

## Value

waterinfo_api class object with content and info about call
