Month 1 summary
My question

How much has the built-up area of Bahir Dar expanded since 2015? This month I answered one part of it: how many of the city's small settlements lie close to its two main built-up areas today.

The operation and why I chose it

I ran a buffer in UTM zone 37N (EPSG:32637), so distances are in metres. I buffered the two main built-up areas by 500 m and by 1 km, then extracted the small settlements that intersect each ring. 
A buffer fits because "close to the city edge" is a question about distance, and the settlements nearest the built-up land are the ones the city is most likely to reach first.

What I expected and what I got
Expected: looking at the map before counting, I expected a good share of the 315 small settlements to sit close to the two large built-up areas, since many of them appeared clustered around them. I did not have a specific number in mind.
Got: of the 315 small settlements, 147 (47%) touch the 500 m ring and 200 (63%) touch the 1 km ring. That leaves 53 in the ring between 500 m and 1 km, and 115 farther than 1 km.
How I checked it
Map: the extracted settlements sit around the two built-up areas, and none appear in the far corners of the city.
Row counts: 2 built-up + 315 others = 317, the size of the original layer. The 1 km count (200) is larger than the 500 m count (147), and both are below 315.
By hand: I measured the distance from a settlement's nearest edge to the built-up area with the Measure tool, and it fell in the expected distance band.
Empty geometry: features with empty geometry in the results.
What surprised me

nearly half of the small settlements are already within 500 m of the built-up areas.
Some settlements that were counted extend past the edge of the ring, because the tool counts a settlement if any part of it touches the ring.

