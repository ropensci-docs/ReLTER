# Obtain the information about of an eLTER activity.

**\[stable\]** This function obtains the information about of an eLTER
activity (e.g.
<https://deims.org/activity/8786fc6d-5d70-495c-b901-42f480182845>)
provided in [DEIMS-SDR catalogue](https://deims.org/).

## Usage

``` r
get_activity_info(activityid, show_map = FALSE)
```

## Arguments

- activityid:

  A `character`. It is the DEIMS ID of activity make from DEIMS-SDR
  website. DEIMS ID information
  [here](https://deims.org/docs/deimsid.html). The DEIMS.iD of activity
  is the URL for the activity page.

- show_map:

  A `boolean`. If TRUE a Leaflet map with occurrences is shown. Default
  FALSE.

## Value

The output of the function is a `list` with two elements:

- `map` A Leaflet map with the activity location, if requested with
  `show_map`.

- `data` A `data.frame` with the information about the activity.

## The function output

![Map of "Study of non-indigenous (alien) species in the Mar Piccolo of
Taranto" activity](figures/get_activity_info_fig.png)

## Author

Alessandro Oggioni, phD (2020) <oggioni.a@irea.cnr.it>

## Examples

``` r
activities <- get_activity_info(
  activityid =
    "https://deims.org/activity/8786fc6d-5d70-495c-b901-42f480182845",
  show_map = TRUE
)
#> Error in httr2::req_perform(.): Failed to perform HTTP request.
#> Caused by error in `curl::curl_fetch_memory()`:
#> ! Timeout was reached [deims.org]:
#> Failed to connect to deims.org port 443 after 10001 ms: Timeout was reached
activities
#> Error: object 'activities' not found
```
