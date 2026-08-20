# Get all sites within a given distance of a point location

**\[experimental\]** retrieve all sites within a given distance from the
center point (in coordinates lat, lon), and in the (optionally)
specified elevation range.

## Usage

``` r
get_sites_within_radius(
  lat = 39.1386,
  lon = -8.33305,
  distance = 1,
  elevation_range = c(NULL, NULL),
  show_map = TRUE
)
```

## Arguments

- lat:

  latitude of radius center

- lon:

  longitude of radius center

- distance:

  distance from point (actually it is in degrees for a limitation of the
  endpoint)

- elevation_range:

  min and max elevation in meters

- show_map:

  `logical` print a map with retrieved sites (default is TRUE)

## Value

list of deims_id, distance from given coordinates

## See also

[`geojsonsf::geojson_sf()`](https://rdrr.io/pkg/geojsonsf/man/geojson_sf.html)

## Examples

``` r
# example code
get_sites_within_radius(lat=39.1386, lon=-8.33305, distance=900)
#> Warning: URL 'https://deims.org/geoserver/deims/ows?service=WFS&version=2.0.0&request=GetFeature&TypeName=deims:deims_all_sites&outputFormat=application/json&CQL_FILTER=DWITHIN(geom,Point(39.1386%20-8.33305),900,kilometers)': Timeout of 300 seconds was reached
#> Error in value[[3L]](cond): There was an error downloading the geojson
```
