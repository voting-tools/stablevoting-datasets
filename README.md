# Stable Voting Datasets Repository

## Overview

This repository contains anonymized polling data collected from the [stabelvoting.org](https://stabelvoting.org).  The datasets are intended for use by researchers, educators, and practitioners interested in analyzing and understanding patterns of voter preferences and the properties of different voting methods.

## Versions

Release date: **12-17-2024**

* Dataset Overview: The dataset contains a total of **657 profiles**.
* Candidate Statistics:
    * Number of candidates per profile ranges from 2 to 43.
    * Average number of candidates per profile: 4.59.
    * Median number of candidates per profile: 3.0.
    * Modal number of candidates per profile: 2.
* Voter Statistics:
    * Number of voters per profile ranges from 2 to 512.
    * Average number of voters per profile: 9.39.
    * Median number of voters per profile: 6.0.

* Types of Profiles:
    * Linear Orders: 366 profiles (56.0%) where each voter submitted a linear order of all the candidates.
    * Truncated Linear Orders: 85 profiles (13.0%) where each voter submitted a linear order over a subset of the candidates, and at least one voter did not rank all the candidates.
    * Rankings with Ties: 146 profiles (22.0%) where each voter submitted a ranking (allowing ties) over all the candidates, and at least one voter submitted a ranking with a tie.
    * Truncated Rankings with Ties: 60 profiles (9.0%) where each voter submitted a ranking  (allowing ties) over a subset of the candidates, at least one voter submitted a ranking with a tie, and at least one voter did not rank all the candidates.



## Usage Instructions

To access the datasets, clone this repository or download it as a ZIP file. Each subdirectory contains a README file with specific details on the format, structure, and usage of the contained files.

```
git clone https://github.com/voting-tools/svdb_datasets.git
```

To read the data into a `ProfileWithTies` object from the pref_voting package ([https://pref-voting.readthedocs.io/](https://pref-voting.readthedocs.io/)), use the following code:


```python

from pref_voting.profiles_with_ties import ProfileWithTies

prof = ProfileWithTies.read('datasets/preflib/sv_poll_0.toc')

prof = ProfileWithTies.read('datasets/csv/sv_poll_0.csv', file_format='csv')

prof = ProfileWithTies.read('datasets/json/sv_poll_0.json', file_format='json')

prof = ProfileWithTies.read('datasets/abif/sv_poll_0.abif', file_format='abif')

```

By default, in a `ProfileWithTies` object, if a voter ranks candidate $x$ but does not rank candidate $y$, $x$ is not treated as being ranked above $y$. This affects calculations such as the margin between candidates.

To change this behavior, you can use the `use_extended_strict_preference` method. After applying this method, if a voter ranks $x$ but leaves $y$ unranked, $x$ is considered to be ranked above $y$.

Here is an example to illustrate this behavior:

```python

prof = ProfileWithTies.read('datasets/preflib/sv_poll_7.soi')

prof.anonymize().display()

print(f"The margin of 3 over 0 is {prof.margin(3, 0)}")

prof.use_extended_strict_preference()

print(f"After applying use_extended_strict_preference, the margin of 3 over 0 is {prof.margin(3, 0)}")

prof.use_strict_preference()

print(f"Returning to the default behavior, the margin of 3 over 0 is {prof.margin(3, 0)}")

```

```sql

+---+---+---+
| 1 | 1 | 1 |
+---+---+---+
| 3 | 0 | 2 |
| 0 | 3 | 0 |
| 1 | 1 |   |
| 2 | 2 |   |
+---+---+---+
The margin of 3 over 0 is 0
After applying use_extended_strict_preference, the margin of 3 over 0 is -1
Returning to the default behavior, the margin of 3 over 0 is 0

```
## Licensing and Privacy

All datasets in this repository are released under the MIT license. This license allows for reuse and modification under the terms specified in the license file.

The privacy of participants in the polls is of utmost importance. All data has been anonymized to remove any personally identifiable information (PII). We follow best practices for anonymization to ensure participant confidentiality.

## Citing the Dataset

This dataset has been published on Zenodo and can be cited using its Digital Object Identifier (DOI). We encourage users to cite the dataset in any academic work, presentation, or publication that makes use of it.


To cite this dataset, use the following format:

Wesley H. Holliday and Eric Pacuit. (2024). Stable Voting Datasets, Release 12-17-2024, doi: [DOI Placeholder].

## Contact

If you have questions about this repository or the datasets, please contact Wes Holliday ([wesholliday@berkeley.edu](mailto:wesholliday@berkeley.edu)) and Eric Pacuit ([epacuit@umd.edu](mailto:epacuit@umd.edu)).
