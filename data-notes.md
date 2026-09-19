Data notes
Week 2: Data acquisition
Bahir Dar Special Zone boundary
Source: OpenStreetMap, via QuickOSM (queried by name: Bahir Dar Special Zone) — https://www.openstreetmap.org/relation/13422216. Traced from Ethiopia's National Spatial Data Infrastructure (EthioGIS zonal boundary layer).
Downloaded: 19 September 2026
Features: 1
Geometry: Polygon (MultiPolygon)
Notes: Single feature covering the whole zone as one polygon. admin_level is 5, which is the "zone" tier in Ethiopia's administrative hierarchy (country → region → zone → woreda).
GRID3 settlement extents (clipped to Bahir Dar)
Source: GRID3 (CIESIN, Columbia University) — https://data.grid3.org/datasets/5bf298c9a55141a082911b406068e276_0/explore. Downloaded for all of Ethiopia, then clipped to the Bahir Dar Special Zone boundary above.
Downloaded: 19 September 2026
Features: 1 (after clipping)
Geometry: Polygon (MultiPolygon)
Notes: This is a single summary polygon for the whole zone, not many small settlement patches as might be expected from a "settlement extents" layer.
Week 3: Reprojection, clipping and quality checks
CRS choice

I used EPSG:32637 (WGS 84 / UTM zone 37N). Bahir Dar sits at about 37.4°E, inside UTM zone 37N, and I need areas in metres and square kilometres, which EPSG:4326 (degrees) can't give me directly. Both layers were in EPSG:4326 when I downloaded them.

What I reprojected and clipped
Study area boundary: reprojected from EPSG:4326 to EPSG:32637 and saved as study_area.gpkg. It is the clip boundary, so it was not clipped.
Settlements: reprojected from EPSG:4326 to EPSG:32637 and saved as bahir_dar_settlements_utm37n.gpkg. This layer was already clipped to the study area in Week 2, so it was not clipped again.
Quality checks
#	Check	Result
1	Both layers in EPSG:32637	Coordinates in both files are in metres in the UTM 37N range (x about 322,000 to 326,600, y about 1,279,600 to 1,285,100), matching EPSG:32637.
2	Geometries valid	Not run in Week 3.
3	Study area size	area_km2 = 12.26 km² (calculated with area($geometry) / 1000000).
4	Settlement area vs. building area column	Geometry area = 9.71 km². The building_area attribute is 9,799,668 m² (9.80 km²). The two differ by about 0.9%.
5	Raw files untouched	Not checked in Week 3.
Analysis-ready files
data/processed/study_area.gpkg (EPSG:32637, with area_km2)
data/processed/bahir_dar_settlements_utm37n.gpkg (EPSG:32637, with area_km2)
