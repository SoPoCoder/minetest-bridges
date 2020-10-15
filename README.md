# Minetest Bridges
Bridge schems of varying length in cardinal and intercardinal directions (N-S, W-E, NW-SE, SW-NE) that can be loaded into Minetest using the WorldEdit tool.
![bridge-demo](https://user-images.githubusercontent.com/7158003/96159020-c3151c00-0f46-11eb-84de-8aabd52c3ada.jpg)

### Dependencies:
To place the schem files in your minetest world you will need the [Minetest-WorldEdit tool](https://github.com/Uberi/Minetest-WorldEdit)

### Instructions
1. Drop the schems folder into the root folder of the world you wish to add bridges to (i.e. /minetest/worlds/myworld/)
2. If you haven't already, enable the Minetest-WorldEdit mod for the world you wish to add bridges to
3. Survey the area in your world you wish to add a bridge, taking note of your bearings (press F9 to view a HUD map that includes an arrow that points north)
4. Use the Minetest-WorldEdit tool to measure distances by placing position markers one and two (in the chat window use command "//1" and "//2" ) then chat command "//volume" to get the distances between positions one and two. Volume will display as (x,y,z) where x is the distance on the east-west axis, y is the distance on the up-down axis and z is the distance on the north-south axis.
5. When considering what length bridge to use, consider that there is some wiggle room for where the arch falls (a few blocks at most), but the distance from the edges of the abutments to the edge of the river/stream/gorge/etc. should be about the same to look good.
6. Based on your survey choose the bridge you wish to use from the bridge dimensions below (or modify the length of a bridge using the Minetest-WorldEdit tool in a seperate sandbox world to create your own custom length bridge schem)

| Schem File Name       | Height | Width | Length¹ | Abutment¹| Arch
| ------                | ------ | ----- | ------  | -------- | ----
| sbridge_long_N-S      | 7      | 11    | 66      | 17       | 32
| sbridge_long_W-E      | 7      | 11    | 66      | 17       | 32
| sbridge_short_N-S     | 7      | 9     | 45      | 12       | 21
| sbridge_short_W-E     | 7      | 9     | 45      | 12       | 21
| dbridge_long_NW-SE    | 6      | 9     | 50 (56) | 13 (16)  | 24 
| dbridge_long_SW-NE    | 6      | 9     | 50 (56) | 13 (16)  | 24 
| dbridge_short_NW-SE   | 6      | 9     | 36 (39) | 9  (12)  | 17
| dbridge_short_SW-NE   | 6      | 9     | 36 (39) | 9  (12)  | 17

¹ numbers in parantheses are the effective lengths for purposes of placing diagonal bridges

![straight-bridge](https://user-images.githubusercontent.com/7158003/96159041-c6a8a300-0f46-11eb-825b-6c78a3553353.jpg)

![diagonal-bridge](https://user-images.githubusercontent.com/7158003/96159028-c4464900-0f46-11eb-986b-f536026441fc.jpg)

### Placing Diagonal Bridges
When measuring distances for diagonal bridges in the SW-NE direction, simply set position two at the bank in the center of where you wish the bridge to be, then set position one and check volume until both x and z coordinates equal the abutment length. This might seem counter-intuitive if you are accustomed to using the Pythagorean thereom to calcuate the diagonal distance of a right triange, but the difference in length of the straight edges and the diagonal edge is factored into each block, so measuring by block means all three sides will be the same distance! When placing diagonal bridges you must set position one at the corner of the square that the bridge is enclosed in, rather than the edge of the diagonal side. So for a diagonal bridge with length of 50, the effective length for purpose of placing it is 56.

![diagonal-bridge-measurement](https://user-images.githubusercontent.com/7158003/96159031-c4dedf80-0f46-11eb-8b7e-6b91541f7150.jpg)

Consider where you must place position one ("//1") in order to place the bridge in the correct position. The Minetest-WorldEdit tool always places schems with position one in the south-west bottom most corner of the schem, regardless of where position two happens to be. Diagonal bridges in the NW-SE direction are therefor a bit trickier to place, since position one must be set south of the west abutments west-most edge by the distance of the bridge.

![placements](https://user-images.githubusercontent.com/7158003/96159037-c6100c80-0f46-11eb-9693-f52e126bde8c.jpg)

### World Edit vs. Minetest Schematic
Two types of schems can be created and used by the Minetest-WorldEdit tool:
- World Edit File (.we): larger than .mts, takes note of air nodes and does not replace the existing map where air nodes are present in the loaded schem. Use chat command "//load <filename>" (no quotes) to load
- Minetest Schematic File (.mts): smaller than .we, does not care what is within the schem file, it will replace everthing in the world in which it is loaded that falls within it's volume.

![mts-vs-we](https://user-images.githubusercontent.com/7158003/96159035-c5777600-0f46-11eb-8d72-fc524e66fc9f.jpg)