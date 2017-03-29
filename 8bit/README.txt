/*******************************************************************
 *                              README                             *
 *                         8bit test dataset                       *
 *                                                                 *
 *  Authors:	Luca Calderoni, Dario Maio, University of Bologna  *
 *		Paolo Palmieri, Cranfield University               *
 *                                                                 *
 *    https://github.com/spatialbloomfilter/libSBF-testdatasets    *
 *******************************************************************/

The included datasets are provided to enable the testing of Spatial Bloom 
Filters implementations. The sets have been designed for a filter built as an 
array of 1-byte values: because of this, the maximum number of areas is 255.

The test datasets are based on 65280 elements (255*256) and 255 areas. Four 
element-area allocation cases are provided: a uniform distribution (each area 
has 256 elements); a random distribution (each area has a random number of 
elements); a linear-increment distribution (where the first set has 2 elements, 
the second 4, the third 6 and the last 510); and the reverse linear decrement 
distribution (where the first set has 510 elements, the second 508, and the last 
has 2). A larger list of elements not in test dataset is also provided 
(non-elements.csv), to be used for checking false positives. This counter-set 
contains 500,000 elements.

FILES			CONTENT
- - -			- - -
elements.csv		list of elements, one per line, where elements are
			alphanumeric (0-9,a-z,A-Z) strings of length 4
non-elements.csv	list of elements not in elements.csv, for false positive
			testing
area-element-unif.csv	areas and the assigned elements, distributed uniformly;
			the first value is the area, the second (separated by a
			comma) is the element
area-element-rand.csv	same as above, but with random distribution of elements
			into the areas.
area-element-lininc.csv	same as above, but with a linearly increasing number of
			elements into the areas.
area-element-lindec.csv	same as above, but with a linearly decreasing number of
			elements into the areas.

For each of the files above, a '-count' CSV file is also included. The file 
lists the number of elements for each area.
