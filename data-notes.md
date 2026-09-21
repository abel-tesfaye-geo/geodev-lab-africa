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
Notes: This was a single summary polygon for the whole zone, not many small settlement patches.
Week 3: Reprojection, clipping and quality checks
Study area used from Week 3 onward

From Week 3 the study area is the Bahir Dar city boundary shapefile, replacing the OSM zone boundary from Week 2. Source: [FILL IN: where the shapefile came from]. The GRID3 settlements were clipped again from the original Ethiopia-wide download in data/raw/, not from the Week 2 clipped layer.

CRS choice

I used EPSG:32637 (WGS 84 / UTM zone 37N). Bahir Dar sits at about 37.4°E, inside UTM zone 37N, and I need areas in metres and square kilometres, which EPSG:4326 (degrees) can't give me directly.

What I reprojected and clipped
Settlements: the full Ethiopia GRID3 layer was clipped to the city boundary, giving bahir_dar_settlements_city.gpkg, then reprojected to EPSG:32637 as bahir_dar_settlements_city_utm37n.gpkg. 317 features, with types including Hamlet and Small Settlement.
Study area: the city boundary was reprojected to EPSG:32637 and saved as study_area_city_utm37n.gpkg. 1 feature ("Bahir Dar").

data/processed/study_area_city_utm37n.gpkg
data/processed/bahir_dar_settlements_city_utm37n.gpkg
