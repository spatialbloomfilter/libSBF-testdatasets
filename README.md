# libSBF-testdatasets #
libSBF - test datasets for the Spatial Bloom Filters implementations ([C++](https://github.com/spatialbloomfilter/libSBF-cpp "libSBF-cpp") / [Python](https://github.com/spatialbloomfilter/libSBF-python "libSBF-python"))

## Synopsis ##
The Spatial Bloom Filters (SBF) are a compact, set-based data structure that extends the original Bloom filter concept. An SBF represents and arbitrary number of sets, and their respective elements (as opposed to Bloom filters, which represent the elements of a single set). SBFs are particularly suited to be used in privacy-preserving protocols, as set-membership queries (i.e. the process of verifying if an element is in a set) can be easily computed over an encrypted SBF, through (somewhat) homomorphic encryption.

## Usage ##
Spatial Bloom Filters have been first proposed for use in location-privacy application, but have found application in a number of domains, including network security and the Internet of Things.

The libSBF-testdatasets repository contains a set of sample datasets useful in testing the [C++](https://github.com/spatialbloomfilter/libSBF-cpp "libSBF-cpp") and [Python](https://github.com/spatialbloomfilter/libSBF-python "libSBF-python") implementations of the SBF data structure. For more details on the implementation, and how to use the library please refer to the [homepage](http://sbf.csr.unibo.it/ "SBF project homepage") of the project.

There are two different kinds of set provided:
- large, *randomly generated datasets* (useful in testing the implamentations and for benchmarking);
- *geospatial datasets*, based on real-world areas and coordinates (that can be used to test the SBF in different application domains).

**Randomly generated datasets**

The datasets are provided in 3 different sizes:
- [8-bit](8bit), with a maximum number of areas of 255 (where the filter is an array of 1-byte values) and more than 65,000 elements in total;
- [8-bit-large](8-bit-large), with the same number of areas as the 8-bit, but more than 16 million elements;
- [16-bit](16bit), with a maximum number of areas of 65,535 (where the filter is an array of 2-byte values) and more than 16 million elements.

The 8/16-bit differentiation reflects the memory management of the implementation of the SBF libraries (1/2 bytes). The 8-bit datasets are also more compact (around 500K each), allowing for easier and quicker testing, while the 16-bit datasets are useful for larger and more comprehensive case studies (each dataset is around 200M). Datasets are provided in CSV format.

For each dimension, a number of datasets (CSV files) are provided:
- `elements.csv`:	a list of elements, one per line, where elements are alphanumeric (0-9,a-z,A-Z) strings;
- `non-elements.csv`:	a list of elements not in elements.csv, for false positive testing;
- `area-element-unif.csv`: a dataset with the areas and the assigned elements, distributed uniformly;
- `area-element-rand.csv`: same as above, but with random distribution of elements into the areas;
- `area-element-lininc.csv`: same as above, but with a linearly increasing number of elements into the areas;
- `area-element-lindec.csv`: same as above, but with a linearly decreasing number of elements into the areas.
Datasets with elements only have one element per line; the datasets with both areas and elements list the values separated by a comma, the area first and the element second.
 
The datasets can be used to test any code that uses the libSBF libraries. Both the [C++](https://github.com/spatialbloomfilter/libSBF-cpp "libSBF-cpp") and [Python](https://github.com/spatialbloomfilter/libSBF-python "libSBF-python") libraries also provide a sample application that can be used with the test datasets. The sample applications create an SBF and insert elements from the selected `area-element-X.csv`, and test membership using the `non-elements.csv` dataset.

**Geospatial datasets**

These datasets contain elements extracted from a conventional geospatial grid on a specified geographical area. Each element represents a single cell of the grid. The grid is derived from the World Geodetic System (WGS84), with an arbitrary precision specific to each dataset.

The following datasets are available in the [geo](geo) folder:
- `vatican-city-0001.csv`:	an area covering the Vatican City with 4 areas of interest.

For each of the files above, two graphical PDF files representing the mapped geographical area are also included. The first file shows the map with an overlay consisting of the World Geodetic System projections (WGS84). The second file also shows the Areas of Interest (AoI) mapped into the dataset.

## Bibliography ##
The SBFs have been proposed in the following research papers:
- Luca Calderoni, Paolo Palmieri, Dario Maio: *Location privacy without mutual trust: The spatial Bloom filter.* Computer Communications, vol. 68, pp. 4-16, September 2015. ISSN 0140-3664
- Paolo Palmieri, Luca Calderoni, Dario Maio: *Spatial Bloom Filters: Enabling Privacy in Location-aware Applications*. In: Inscrypt 2014. Lecture Notes in Computer Science, vol. 8957, pp. 16–36, Springer, 2015.

A comprehensive list of papers that use the SBF data structure can be found [here](http://sbf.csr.unibo.it/publications.html "SBF Publications").

## Authors ##
Luca Calderoni, Dario Maio - University of Bologna (Italy)

Paolo Palmieri - University College Cork (Ireland)

## License ##
The datasets are released under the [MIT License](LICENSE).
