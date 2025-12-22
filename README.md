# D502-Data-Analysis-Capstone
Capstone Project for WGU Data Analytics BS

Project code can be found in data_processing.ipynb (Jupyter Notebook) or data_processing.html (HTML)

Note that the original project (all commits from 2025) does not represent the best I am capable of; I started the project in late November and was rushed to get it submitted by mid-December to avoid delays in approval due to the holidays. I believe it is a good representation of my skills, but not by any means the limit of my ability.

The following sections are modified excerpts from the project proposal and report, both of which can be found as PDFs in this repository.

# Project Overview
## Research Question
The research question for this project is: “Can the taxonomic group of a venomous animal be predicted using only the protein composition of its venom?” This project also addresses an organizational need within the multidisciplinary field of venom research: namely, the need for data analysis solutions and tools, both for the field in general, and also specifically for the development of safer and more effective antivenom treatments.

## Background
There are 6 main taxonomic groups of animals that produce venom: Snakes, Spiders, Scorpions, Insects, Jellyfish + Relatives, and Cone Snails. The venom produced by certain species within these groups can cause lasting harm to humans, including death. Therefore, pharmaceutical research has produced many antivenoms to treat medical emergencies caused by these animals. Many compounds in these venoms have also been found to be useful in the development of new medicines to treat all sorts of issues (Morsy et al., 2023). However, this research faces significant difficulties.

The easiest antivenoms to produce are “monovalent” antivenoms, i.e. antivenoms that work to treat the venom from a single species. However, in many medical emergencies, the species of envenomating animal is not known, so a “polyvalent” (multi-species) antivenom must be used. This antivenom is generally tailored to the most common dangerous venomous animals present in the local area. Polyvalent antivenoms are more difficult to produce, and they have a higher rate of medical reactions and complications (Chanda et al., 2024). This project aims to help this issue by providing the a machine learning model to predict the identity of a venomous animal based on the composition of its venom. The model could be used to develop tests to help medical professionals choose the right antivenom for an emergency, allowing for the use of the safer, simpler monovalent antivenoms.

On top of the difficulties that antivenom research faces on the medical side, the entire field of venom research suffers from scattered and disorganized data sources and tools. A centralized database and connected tools are necessary for venom research to reach its fullest potential (Zancolli et al., 2024). The workflow and model that will be produced by this project could be a small step toward such tools, providing a functional proof-of-concept for the usefulness of consolidated data and data analytics methods for venom research.

## Hypothesis
The proteins found in venoms are different enough between taxonomic groups (snakes, spiders, scorpions, insects, jellyfish and relatives, and cone snails) that the composition of the venom of a species can be used to classify it in one of these groups via a machine learning classifier model, without other information on the species.

# Dataset
The data used comes from the UniProtKB/Swiss-Prot Tox-Prot database, which contains expert-reviewed records of proteins found in animal venoms. This dataset is a subset of the larger UniProtKB/Swiss-Prot protein database. At the time of retrieval (November 19, 2025), the dataset contained 7,794 venom protein records. The data was downloaded to venom.tsv. The dataset used can be found here: https://www.uniprot.org/uniprotkb/?query=taxonomy_id%3A33208+AND+%28cc_tissue_specificity%3Avenom+OR+cc_scl_term%3Anematocyst%29+AND+reviewed%3Atrue&facets=reviewed%3Atrue.

# Project Results and Significance

## Practical Application
The model achieved an excellent accuracy score of 95%; far beyond the minimum threshold set for the model to be considered successful. While it would require a larger, more granular dataset to be fully applied in the real world, this result indicates that the model would be well-suited to the practical applications discussed, primarily the application of identifying which antivenom to administer in an emergency situation.

The practical application would look something like this: the model (or a similar one trained on a much larger volume of data) would be applied to a regional set of dangerous venomous animals. The feature importance of the model would be used to determine the crucial proteins useful for distinguishing between the relevant species. A medical test could then be developed that would quickly register which of these diagnostic proteins were present in a victim’s blood, and medical professionals could use this information to accurately select the appropriate monovalent (single-species) antivenom. Since polyvalent (multi-species) antivenoms are associated with more frequent medical complications, this would reduce the rate of these complications, and could also reduce the cost of antivenoms in general, since monovalent antivenoms are easier to produce than polyvalent antivenoms.

## Conclusions
The high accuracy score for the trained random forest model supports the hypothesis that venom composition can be used to distinguish between disparate taxonomic groups of venomous animals. This result indicates that the model would be well-suited for the applications discussed in the proposal and this report. These include:
•	The main practical application, identification of venom by composition for the purpose of administering the correct antivenom in medical emergencies.
•	Use of the model as a tool for venom research using Tox-Prot, one of the largest collections of venom composition data.
•	An argument for the usefulness of consolidated venom data and a step toward a unified suite of venom data and integrated analysis tools.

# References
Chanda, A., Salvi, N. C., Shelke, P. V., Kalita, B., Patra, A., Puzari, U., Khadilkar, M. V., & Mukherjee, A. K. (2024). Supplementation of polyclonal antibodies, developed against epitope-string toxin-specific peptide immunogens, to commercial polyvalent antivenom, shows improved neutralization of Indian big four and Naja Kaouthia snake venoms. Toxicon: X, 24. https://doi.org/10.1016/j.toxcx.2024.100210

Morsy, M. A., Gupta, S., Dora, C. P., Jhawat, V., Dhanawat, M., Mehta, D., Gupta, K., Nair, A. A., & El-Daly, M. (2023). Venoms classification and therapeutic uses: A narrative review. Eur Rev Med Pharmacol Sci, 27(4), 1633–1653. https://doi.org/10.26355/eurrev_202302_31408

Zancolli, G., von Reumont, B. M., Anderluh, G., Caliskan, F., Chiusano, M. L., Fröhlich, J., Hapeshi, E., Hempel, B.-F., Ikonomopoulou, M. P., Jungo, F., Marchot, P., de Farias, T. M., Modica, M. V., Moran, Y., Nalbantsoy, A., Procházka, J., Tarallo, A., Tonello, F., Vitorino, R., … Antunes, A. (2024). Web of venom: Exploration of big data resources in animal toxin research. GigaScience, 13. https://doi.org/10.1093/gigascience/giae054
