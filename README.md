# GeoDev Lab Africa — Abel Tesfaye

Monthly practicals for GeoDev Lab Africa, Cohort One. This repository follows one project from question to result.

## Project question

**How much has the built-up area of Bahir Dar expanded since 2015?**

## Progress

| Week | What I did | Where to look |
|---|---|---|
| 1 | Chose the question, listed the data I need and checked that it is free | [project-brief.md](project-brief.md) |
| 2 | Downloaded real data, opened it in QGIS, described each layer | [data-notes.md](data-notes.md) |
| 3 | Reprojected everything to UTM zone 37N (EPSG:32637) and clipped to the study area | [data-notes.md](data-notes.md) |
| 4 | Ran a spatial operation (buffer), checked it, made a map and wrote a summary | [month-1-summary.md](month-1-summary.md) |

## Month 1 result

I asked how many of Bahir Dar's small settlements sit close to the city's two main built-up areas, since these are the places where the city edge is closest to its neighbours.

![Small settlements near Bahir Dar's built-up areas](month-1-map.png)

- Study area: Bahir Dar city, about 213 km².
- The GRID3 settlement layer has 317 polygons: 2 large built-up areas (about 78.7 km², roughly 37% of the city) and 315 smaller settlements (hamlets and small settlement areas).
- I buffered the two built-up areas by 500 m and by 1 km, then extracted the settlements that touch each ring.
- **147 of the 315 small settlements (47%) touch the 500 m ring, and 200 (63%) touch the 1 km ring.** The other 115 are farther than 1 km away.

## Method

1. Work in EPSG:32637 (WGS 84 / UTM zone 37N), so distances are in metres.
2. Split the GRID3 settlements into the 2 built-up areas and the 315 others (Extract by attribute).
3. Buffer the built-up areas by 500 m and 1000 m, dissolving each result into one shape (Buffer).
4. Extract the other settlements that intersect each buffer (Extract by location).
5. Check the result four ways: on the map, the row counts, one feature measured by hand, and empty geometry.

All processing was done in QGIS.

## Data

| Data | Source |
|---|---|
| Settlement extents (317 polygons after clipping) | GRID3 Ethiopia Settlement Extents v3.0, https://data.grid3.org/datasets/5bf298c9a55141a082911b406068e276_0/explore |
| Bahir Dar city boundary (1 polygon, about 213 km²) | City limit polygon from my own working data |

The data files are large, so they are not stored in this repository. `data-notes.md` describes each layer, and the link above shows where to get the GRID3 data.



## Month 2: development environment and early Python

Week 5: set up Python, VS Code and the terminal. hello.py runs.








## About

Abel Tesfaye Tsega, Institute of Land Administration, Bahir Dar University, Ethiopia.
GitHub: [abel-tesfaye-geo](https://github.com/abel-tesfaye-geo)
