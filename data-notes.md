data note
Bahir Dar city boundary
Source: city limit polygon for Bahir Dar from my own working data
Features: 1
Columns: fid, OBJECTID, Name, Area, POP_TOT, SHAPE_Leng, SHAPE_Area, area_km2 (plus a few duplicate area columns)
Geometry: Polygon
Notes: Area is about 213.4 km², and the source's own Area column (21,341.8 ha) agrees with my calculated value. POP_TOT is 0, so the layer holds no population data.
GRID3 Ethiopia Settlement Extents v3.0, clipped to Bahir Dar
Source: GRID3 (CIESIN, Columbia University), https://data.grid3.org/datasets/5bf298c9a55141a082911b406068e276_0/explore
Features: 317 after clipping to the city boundary (2 Built-up Area, 34 Small Settlement Area, 281 Hamlet)
Columns: fid, OBJECTID, country, iso3, building_count, building_area, type, probability, date, source, mgrs_code, area_km2
Geometry: Polygon (MultiPolygon)
Notes: All rows are dated 2024, so this is a snapshot, not a time series. The two Built-up Area polygons are much larger than everything else (about 48.7 km² and 29.9 km² inside the city). building_count and building_area keep the values of the original, unclipped polygons, so they are too high where a polygon was cut by the boundary. No null values in the columns I checked.
CRS and preparation
All source layers arrived in EPSG:4326 (WGS 84, degrees).
Working CRS: EPSG:32637 (WGS 84 / UTM zone 37N), because Bahir Dar (about 37.4°E) lies in UTM zone 37N and I need metres for areas and buffer distances.
The boundary and settlement layers were reprojected and saved in data/processed/; the downloaded files in data/raw/ were not edited.
Layers made in Month 1
core_builtup: the 2 Built-up Area polygons.
outer_settlements: the other 315 settlements (2 + 315 = 317).
core_buffer_500m and core_buffer_1km: buffers of core_builtup, each dissolved into one shape.
outer_within_500m (147 features) and outer_within_1km (200 features): settlements that intersect each buffer.
