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

## Assumptions

- Ratings >= 4.0 are treated as liked, below 4.0 as disliked
- Missing ratings are filled with per-user mean before SVD (not global mean) to account for individual rating scales
- SVD RMSE being lower than Surprise SVD does not mean it is a better model — filling NaN with user means gives an unfair advantage on RMSE. Surprise's SGD with regularisation generalises better, reflected in its higher P@10 and R@10
- Cold-start users are defined as those with 20 or fewer ratings
- RL reward: +1 for rating >= 4, -1 for rating < 4, 0 for no rating
- numpy must be pinned below 2.0 — scikit-surprise is compiled against numpy 1.x and crashes on import with numpy 2.x
- shap==0.45.1 is pinned as it is the last version compatible with numpy 1.x
