GeoDev Lab Africa — Abel Tesfaye

Monthly practicals for GeoDev Lab Africa, Cohort One. This repository follows one project from question to result.

Project question

How much has the built-up area of Bahir Dar expanded since 2015?

Progress
Week	What I did	Where to look
1	Chose the question, listed the data I need and checked that it is free	project-brief.md
2	Downloaded real data, opened it in QGIS, described each layer	data-notes.md
3	Reprojected everything to UTM zone 37N (EPSG:32637) and clipped to the study area	data-notes.md
4	Ran a spatial operation (buffer), checked it, made a map and wrote a summary	month-1-summary.md
Month 1 result

I asked how many of Bahir Dar's small settlements sit close to the city's two main built-up areas, since these are the places where the city edge is closest to its neighbours.

Show Image

Study area: Bahir Dar city, about 213 km².
The GRID3 settlement layer has 317 polygons: 2 large built-up areas (about 78.7 km², roughly 37% of the city) and 315 smaller settlements (hamlets and small settlement areas).
I buffered the two built-up areas by 500 m and by 1 km, then extracted the settlements that touch each ring.
147 of the 315 small settlements (47%) touch the 500 m ring, and 200 (63%) touch the 1 km ring. The other 115 are farther than 1 km away.
Method
Work in EPSG:32637 (WGS 84 / UTM zone 37N), so distances are in metres.
Split the GRID3 settlements into the 2 built-up areas and the 315 others (Extract by attribute).
Buffer the built-up areas by 500 m and 1000 m, dissolving each result into one shape (Buffer).
Extract the other settlements that intersect each buffer (Extract by location).
Check the result four ways: on the map, the row counts, one feature measured by hand, and empty geometry.

All processing was done in QGIS.

Data
Data	Source
Settlement extents (317 polygons after clipping)	GRID3 Ethiopia Settlement Extents v3.0, https://data.grid3.org/datasets/5bf298c9a55141a082911b406068e276_0/explore
Bahir Dar city boundary (1 polygon, about 213 km²)	City limit polygon from my own working data

The data files are large, so they are not stored in this repository. data-notes.md describes each layer, and the link above shows where to get the GRID3 data.

Repository contents
File	What it is
README.md	This overview
project-brief.md	The question, the data needed and where each dataset comes from
data-notes.md	Description of every layer: source, features, columns, geometry, gaps, CRS
month-1-summary.md	The Month 1 write-up
month-1-map.png	The Month 1 map
Limitations
The GRID3 layer is a snapshot dated 2024. It shows where things are now, not how the city changed over time, so this month's result does not yet measure growth since 2015.
A settlement is counted if any part of it touches a ring, so some counted settlements extend outside it.
Building counts and areas are not recalculated when a polygon is clipped, so they are too high for polygons cut by the city boundary. I used polygon geometry for areas instead.
Next steps
Get built-up data for 2015 and a recent year (for example the GHSL built-up surface) so I can measure actual growth.
Repeat the buffer analysis on both years to see whether settlements near the city edge became part of it.
About

Abel Tesfaye Tsega, Institute of Land Administration, Bahir Dar University, Ethiopia. GitHub: abel-tesfaye-geo
