# Stable Voting Datasets Repository

## Overview

This repository contains anonymized polling data collected from the [stabelvoting.org](https://stabelvoting.org).  The datasets are intended for use by researchers, educators, and practitioners interested in analyzing and understanding patterns of voter preferences and the properties of different voting methods.

## Versions

Release date: **12-17-2024**

* Dataset Overview: The dataset contains a total of **657 profiles**.
* Candidate Statistics:
    * Number of candidates per profile ranges from 2 to 43,
    * Average number of candidates per profile: 4.59.
* Voter Statistics:
    * Number of voters per profile ranges from 2 to 512,
    * Average number of voters per profile: 9.39.
* Types of Profiles:
    * Linear Orders (All candidates are ranked): 366 profiles (56.0%) where each voter submitted a complete, linear order of all the candidates.
    * Truncated Linear Orders (Not all candidates are ranked): 85 profiles (13.0%) where each voter submitted a linear order over a subset of the candidates.
    * Rankings with Ties (All candidates are ranked): 146 profiles (22.0%) where each voter submitted a ranking with ties over all the candidates.
    * Rankings with Ties (Not all candidates are ranked): 60 profiles (9.0%) where each voter submitted a ranking with ties over a subset of the candidates.




## Usage Instructions

To access the datasets, clone this repository or download it as a ZIP file. Each subdirectory contains a README file with specific details on the format, structure, and usage of the contained files.

```
git clone https://github.com/voting-tools/svdb_datasets.git
```

Use the following code to read the data into a ProfileWithTies object from pref_voting: 

```python

from pref_voting.profiles_with_ties import ProfileWithTies

prof = ProfileWithTies.read('datasets/preflib/sv_poll_0.toc')

prof = ProfileWithTies.read('datasets/csv/sv_poll_0.csv', file_format='csv')

prof = ProfileWithTies.read('datasets/json/sv_poll_0.json', file_format='json')

prof = ProfileWithTies.read('datasets/abif/sv_poll_0.abif', file_format='abif')

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
