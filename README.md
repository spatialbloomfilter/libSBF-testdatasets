# libSBF-testdatasets #
libSBF - test datasets for the Spatial Bloom Filters implementations ([C++](https://github.com/spatialbloomfilter/libSFB-cpp "libSFB-cpp") / [Python](https://github.com/spatialbloomfilter/libSFB-python "libSFB-python"))

## Synopsis ##
The Spatial Bloom Filters (SBF) are a compact, set-based data structure that extends the original Bloom filter concept. An SBF represents and arbitrary number of sets, and their respective elements (as opposed to Bloom filters, which represent the elements of a single set). SBFs are particularly suited to be used in privacy-preserving protocols, as set-membership queries (i.e. the process of verifying if an element is in a set) can be easily computed over an encrypted SBF, through (somewhat) homomorphic encryption.

## Usage ##
Spatial Bloom Filters have been first proposed for use in location-privacy application, but have found application in a number of domains, including network security and the Internet of Things.

The libSBF-testdatasets repository contains a set of sample datasets useful in testing the [C++](https://github.com/spatialbloomfilter/libSFB-cpp "libSFB-cpp") and [Python](https://github.com/spatialbloomfilter/libSFB-python "libSFB-python") implementations of the SBF data structure.

The datasets are provided in 2 dimensions:
- [8-bit](8bit), with a maximum number of areas of 255 (where the filter is an array of 1-byte values);
- [16-bit](16bit), with a maximum number of areas of 65,535 (where the filter is an array of 2-byte values).
This reflects the memory management of the implementation of the SBF libraries. The 8-bit datasets are also more compact (around 500K each), allowing for easier and quicker testing, while the 16-bit datasets are useful for larger and more comprehensive case studies (each dataset is around 200M). Datasets are provided in CSV format.

For each dimension, a number of datasets (CSV files) are provided:
- `elements.csv`:	a list of elements, one per line, where elements are alphanumeric (0-9,a-z,A-Z) strings;
- `non-elements.csv`:	a list of elements not in elements.csv, for false positive testing;
- `area-element-unif.csv`: a dataset with the areas and the assigned elements, distributed uniformly;
- `area-element-rand.csv`: same as above, but with random distribution of elements into the areas;
- `area-element-lininc.csv`: same as above, but with a linearly increasing number of elements into the areas;
- `area-element-lindec.csv`: same as above, but with a linearly decreasing number of elements into the areas.
Datasets with elements only have one element per line; the datasets with both areas and elements list the values separated by a comma, the area first and the element second.
 
The datasets can be used to test any code that uses the libSBF libraries. Both the [C++](https://github.com/spatialbloomfilter/libSFB-cpp "libSFB-cpp") and [Python](https://github.com/spatialbloomfilter/libSFB-python "libSFB-python") libraries also provide a sample application that can be used with the test datasets. The sample applications create an SBF and insert elements from the selected (`area-element.csv`), and test membership using the `non-elements.csv` dataset.

For more details on the implementation, and how to use the library please refer to the [homepage](http://sbf.csr.unibo.it/ "SBF project homepage") of the project.

## Bibliography ##
The SBFs have been proposed in the following research papers:
- Luca Calderoni, Paolo Palmieri, Dario Maio: *Location privacy without mutual trust: The spatial Bloom filter.* Computer Communications, vol. 68, pp. 4-16, September 2015. ISSN 0140-3664
- Paolo Palmieri, Luca Calderoni, Dario Maio: *Spatial Bloom Filters: Enabling Privacy in Location-aware Applications*. In: Inscrypt 2014. Lecture Notes in Computer Science, vol. 8957, pp. 16–36, Springer, 2015.

## Authors ##
Luca Calderoni, Dario Maio - University of Bologna (Italy)

Paolo Palmieri - Cranfield University (UK)

## License ##
The datasets are released under the [MIT License](LICENSE).
