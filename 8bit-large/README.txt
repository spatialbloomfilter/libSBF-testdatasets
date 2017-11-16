/*******************************************************************
 *                              README                             *
 *                     8-bit-large test dataset                    *
 *                                                                 *
 *  Authors:	Luca Calderoni, Dario Maio, University of Bologna  *
 *		Paolo Palmieri, University College Cork            *
 *                                                                 *
 *    https://github.com/spatialbloomfilter/libSBF-testdatasets    *
 *******************************************************************/

The included datasets are provided to enable the testing of Spatial Bloom 
Filters implementations. The sets have been designed for a filter built as an 
array of 1-byte values: because of this, the maximum number of areas is 255.

The test datasets are based on 16,776,960 elements (255*65792) and 255 areas. A 
single element-area allocation case is provided: a uniform distribution where 
each area has 65,792 elements. This set is to be used in conjuction with the 
16-bit datasets list of elements (elements.csv), as they are the same. 
Similarly, the list of elements not in test dataset (non-elements.csv) for the 
16-bit datasets can also be used for checking false positives in the 8-bit-large 
sets. This counter-set contains 500,000 elements.

FILES			CONTENT
- - -			- - -
area-element-unif.csv	areas and the assigned elements, distributed uniformly;
			the first value is the area, the second (separated by a
			comma) is the element

For each of the files above, a '-count' CSV file is also included. The file 
lists the number of elements for each area.
