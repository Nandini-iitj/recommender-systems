# CSL7110 - Recommender Systems

Assignment 3 | MovieLens ml-latest-small dataset

## Setup

Python 3.11 is required. Create a virtual environment and install dependencies:

```bash
python3.11 -m venv .venv311
source .venv311/bin/activate
pip install "numpy<2" "shap==0.45.1" scikit-surprise --force-reinstall --no-cache-dir
pip install pandas scikit-learn scipy tensorflow lime matplotlib seaborn tqdm jupyter ipykernel
```

## Dataset

Download MovieLens ml-latest-small from https://grouplens.org/datasets/movielens/ and update `base_path` in the notebook to point to the folder.

## Running

Open `M25DE1012_CSL7110_Assignment3.ipynb`, select the Python 3.11 kernel and run all cells.
