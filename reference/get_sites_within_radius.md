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
#> Warning: incomplete final line found on 'https://deims.org/geoserver/deims/ows?service=WFS&version=2.0.0&request=GetFeature&TypeName=deims:deims_all_sites&outputFormat=application/json&CQL_FILTER=DWITHIN(geom,Point(39.1386%20-8.33305),900,kilometers)'
#> Simple feature collection with 1318 features and 5 fields
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: -156.6674 ymin: -78 xmax: 175.085 ymax: 83.07682
#> Geodetic CRS:  WGS 84
#> First 10 features:
#>                                                                         name
#> 1                                                       Station Linné, Öland
#> 2                                                        Machuqueira do Grou
#> 3                                                                LTSER-Sabor
#> 4                                               Fray Jorge Experimental Site
#> 5                                            Senda Darwin Biological Station
#> 6                                   Shenyang Experimental Station of Ecology
#> 7  Fengqiu Experimental Station for Agro-ecology Chinese Academy of Sciences
#> 8                                  Luancheng Agricultural Ecological Station
#> 9                                    Taoyuan Agricultural Ecological Station
#> 10                                    Hailun Agricultural Ecological Station
#>                                                   deimsid field_coordinates_lat
#> 1  https://deims.org/8e20a701-1128-4225-9b22-ea145b091d91               56.6190
#> 2  https://deims.org/8430e9a9-211a-493a-8049-73c3339f0c61               39.1386
#> 3  https://deims.org/45722713-80e3-4387-a47b-82c97a6ef62b               41.3333
#> 4  https://deims.org/7fdabe1f-208a-449a-bc29-1e6ab2a1795b              -30.6581
#> 5  https://deims.org/133ec196-71c4-4f33-a230-56723bee35fb              -41.8834
#> 6  https://deims.org/5251a2c7-d44e-4ec1-892e-bf77b8bc3450               41.5167
#> 7  https://deims.org/5425446c-bfcb-448d-9f75-b06718df59ed               35.0167
#> 8  https://deims.org/5de9ae4c-c705-4cd5-b55a-2195c936f7fb               37.8833
#> 9  https://deims.org/9518c7f8-d3f2-4e57-b6a7-67bb4a20f1e5               28.9167
#> 10 https://deims.org/495881b0-52bc-410c-99b7-45575e08f80c               47.4500
#>    field_coordinates_lon field_elevation_avg_value                   geometry
#> 1               16.49800                      45.0      POINT (16.498 56.619)
#> 2               -8.33305                     150.0   POINT (-8.33305 39.1386)
#> 3               -6.95000                     500.0      POINT (-6.95 41.3333)
#> 4              -71.66382                     230.0 POINT (-71.66382 -30.6581)
#> 5              -73.66670                      75.0  POINT (-73.6667 -41.8834)
#> 6              123.40000                      41.0      POINT (123.4 41.5167)
#> 7              114.53300                      67.5    POINT (114.533 35.0167)
#> 8              114.68300                      50.1    POINT (114.683 37.8833)
#> 9              111.43330                        NA   POINT (111.4333 28.9167)
#> 10             126.91700                     236.0      POINT (126.917 47.45)
```
