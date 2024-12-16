# Polling Data Repository

## Overview

This repository contains anonymized polling data collected from the [stabelvoting.org](https://stabelvoting.org).  The datasets are intended for use by researchers, educators, and practitioners interested in analyzing and understanding patterns of voter preferences and the properties of different voting methods.

## Versions

Release date of the current version of the repository: 12-16-2024

There are 658 polls in the repository...OTHER STATISTICS?

## Data Formats

We provide the polling data in the following formats:

- **Preflib**: A standard format for preference data used in computational social choice.  See [https://preflib.simonrey.fr/format#types](https://preflib.simonrey.fr/format#types) for a description of the format.
- **CSV**: A standard format to store tabular data in plain text....EXPLAIN FORMAT
- **JSON**: A lightweight, text-based format commonly used in web applications and data interchange...EXPLAIN FORMAT
- **ABIF**: This format is described at [https://electowiki.org/wiki/ABIF](https://electowiki.org/wiki/ABIF).

Each of these data formats is can be processed by pref_voting as a ProfileWithTies.  GIVE EXAMPLE CODE


## Usage Instructions

To access the datasets, clone this repository or download it as a ZIP file. Each subdirectory contains a README file with specific details on the format, structure, and usage of the contained files.

```
git clone https://github.com/voting-tools/svdb_datasets.git
```

## Licensing and Privacy

All datasets in this repository are released under the MIT license. This license allows for reuse and modification under the terms specified in the license file.

The privacy of participants in the polls is of utmost importance. All data has been anonymized to remove any personally identifiable information (PII). We follow best practices for anonymization to ensure participant confidentiality.

## Citing the Dataset

This dataset has been published on Zenodo and can be cited using its Digital Object Identifier (DOI). We encourage users to cite the dataset in any academic work, presentation, or publication that makes use of it.
DOI: [DOI Placeholder] (Once available, the DOI will be added here.)

To cite this dataset, use the following format:

Wesley H. Holliday and Eric Pacuit. (Year). Polling Data Repository [Data set]. Zenodo. [[https://doi.org/](https://doi.org/)[DOI](https://doi.org/\[DOI) Placeholder]

## Contact

If you have questions about this repository or the datasets, please contact Wes Holliday ([wesholliday@berkeley.edu](mailto:wesholliday@berkeley.edu)) and Eric Pacuit ([epacuit@umd.edu](mailto:epacuit@umd.edu)).
