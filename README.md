# DSCI526HW3

Homework 3: AReM time-series feature extraction and ISLR Section 3.7, Exercise 4.
The repository name follows the requested name; the assignment handout is for DSCI 552.

## Contents

- `Huang_Hao_HW3.ipynb`: completed notebook with saved outputs.
- `AReM/`: supplied data, including all 88 activity recordings.
- `requirements.txt`: Python dependencies.

## Run

From the repository root, install dependencies and launch Jupyter:

```bash
python -m pip install -r requirements.txt
python -m jupyter notebook Huang_Hao_HW3.ipynb
```

Select the installed Python environment and run all cells in order. In VS Code,
open this repository folder, select that Python environment as the notebook kernel,
and use **Run All**. The notebook reads `AReM/` relative to the working directory
and writes generated tables and a figure to `results/`.

For a full noninteractive execution from the repository root:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=300 --output Huang_Hao_HW3.executed.ipynb Huang_Hao_HW3.ipynb
```

Expected results: 69 training instances, 19 test instances, an 88-by-42 feature
matrix, and 42 pointwise 90% bootstrap confidence intervals based on 20,000
resamples with seed 552.

Verified by executing every cell in a fresh Jupyter kernel with NumPy 2.4.6,
pandas 3.0.3, and Matplotlib 3.11.0.

## Data handling

The parser accepts comma or whitespace separators and harmless trailing commas.
`sitting/dataset8.csv` has 479 observed rows, with timestamp 13500 ms missing;
its observed rows are retained without imputation. The remaining recordings
have 480 rows. Original data files are unchanged.

Source: [UCI AReM dataset](https://archive.ics.uci.edu/dataset/366/activity+recognition+system+based+on+multisensor+data+fusion+arem).
