# Dataset

This project uses **CICIDS2017** (MachineLearningCSV release), produced by the
Canadian Institute for Cybersecurity (CIC), University of New Brunswick.

The raw dataset is **not included in this repository** due to its size
(2.83 million flow records, several GB) and its licence terms, which permit
research use but not redistribution.

## How to get the data

1. Visit the official dataset page: https://www.unb.ca/cic/datasets/ids-2017.html
2. Download the **MachineLearningCSV.zip** release.
3. Extract the CSV files into this `data/` folder.
4. Run the notebooks in `notebooks/` — they expect the CSVs to be in this
   folder (or update the file paths at the top of each notebook if you keep
   them elsewhere, e.g. Google Drive when running in Colab).

## Citation requirement

Any use of this dataset must cite:

> Sharafaldin, I., Lashkari, A. H., & Ghorbani, A. A. (2018). Toward
> Generating a New Intrusion Detection Dataset and Intrusion Traffic
> Characterization. *Proceedings of the 4th International Conference on
> Information Systems Security and Privacy (ICISSP)*, 108–116.
