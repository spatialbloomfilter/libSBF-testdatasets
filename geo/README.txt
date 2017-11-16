/*******************************************************************
 *                              README                             *
 *                      geographic test dataset                    *
 *                                                                 *
 *  Authors:	Luca Calderoni, University of Bologna              *
 *		Paolo Palmieri, University College Cork            *
 *                                                                 *
 *    https://github.com/spatialbloomfilter/libSBF-testdatasets    *
 *******************************************************************/

The included datasets are provided to enable the testing of the Spatial Bloom 
Filters implementations on a real geographical areas.

The test datasets are based on several elements and areas.

The datasets contain elements extracted from a conventional geospatial grid on 
a specified area. Each element represents a single cell of the grid. The grid 
is derived from the World Geodetic System (WGS84), with an arbitrary precision. 
The unique identifier of each cell is formed by the latitude and the longitude 
relative to the bottom left corner of the cell, separated by a hash '#' symbol. 
For instance, using a four digit precision, a cell may be represented by the 
identifier 00.0000#00.0000

FILES			CONTENT
- - -			- - -
vatican-city-0001.csv	An area covering the Vatican City. The dataset specifies
			4 areas of interest (AoI); the first value in the CSV is
			the area identifier, the second (separated by a comma)
			is the element (using the convention outlined above).

For each of the files above, two graphical PDF files representing the mapped 
geographical area are also included. The first file shows the map with an 
overlay consisting of the World Geodetic System projections (WGS84). The second 
file also shows the Areas of Interest (AoI) mapped into the dataset.
