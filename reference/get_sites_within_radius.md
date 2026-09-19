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
#> Simple feature collection with 1317 features and 5 fields
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: -156.6674 ymin: -78 xmax: 175.085 ymax: 83.07682
#> Geodetic CRS:  WGS 84
#> First 10 features:
#>                                                  name
#> 1                            McMurdo Dry Valleys LTER
#> 2       Mooring A: Southwestern Ross Sea, Ross Island
#> 3                    IT17-Antarctica Research Station
#> 4  Mooring D: Western Ross Sea, TerraNova Bay Polynya
#> 5                     OZCAR-RI Glacioclim Dome C site
#> 6                      Macrosito Baia Terranova (MBT)
#> 7     Mooring B: North Central Ross Sea, Joides Basin
#> 8                      LTSER Zone Atelier Antarctique
#> 9             OZCAR-RI Glacioclim Cap Prud'Homme Site
#> 10                                Palmer Station LTER
#>                                                   deimsid field_coordinates_lat
#> 1  https://deims.org/61320397-64ef-4d2f-b774-97ea094bc5d2             -78.00000
#> 2  https://deims.org/86b6465c-b604-4efa-9145-0805f62216f4             -76.70000
#> 3  https://deims.org/a0df48f6-bd2b-42b2-919a-77cb41220440             -75.69570
#> 4  https://deims.org/b4121cd7-8b02-4872-b1d2-516d1c02056a             -75.13300
#> 5  https://deims.org/13ee3167-efbc-4046-a74e-11156b58bb81             -75.10000
#> 6  https://deims.org/7fb8e2c6-b11f-41a7-b494-44ceeb3bed2d             -74.71670
#> 7  https://deims.org/1fb62b9c-4d5c-4f1f-8882-807032337de7             -74.01050
#> 8  https://deims.org/5d621971-e68c-4015-b01f-a259f27dd6a0             -67.00000
#> 9  https://deims.org/4a405a4b-5eed-40a7-be42-bfda96d02c00             -66.69289
#> 10 https://deims.org/0c24abb5-ebe1-49ef-a324-fd9d16ae3ee5             -64.77430
#>    field_coordinates_lon field_elevation_avg_value                   geometry
#> 1               162.0000                       100            POINT (162 -78)
#> 2               169.0920                      -400      POINT (169.092 -76.7)
#> 3               171.5170                      -350   POINT (171.517 -75.6957)
#> 4               164.5420                     -1157    POINT (164.542 -75.133)
#> 5              -123.3300                      3200      POINT (-123.33 -75.1)
#> 6               164.1330                      -200   POINT (164.133 -74.7167)
#> 7               175.0850                      -300   POINT (175.085 -74.0105)
#> 8               139.0000                       300            POINT (139 -67)
#> 9               139.9092                       100 POINT (139.9092 -66.69289)
#> 10              -64.0529                         0  POINT (-64.0529 -64.7743)
```
