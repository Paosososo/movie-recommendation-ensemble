# Ensemble Recommendation System for Movie Ratings

A Python notebook that compares three collaborative filtering models and combines their rating predictions into top 10 movie recommendations.

[Open the notebook](Ensemble_Recommendation_System.ipynb) · [Run it in Colab](https://colab.research.google.com/github/Paosososo/movie-recommendation-ensemble/blob/main/Ensemble_Recommendation_System.ipynb)

## Approach

The notebook loads rating splits and movie metadata, prepares the data, and trains SVD, item based KNN, and NMF with scikit-surprise. It evaluates each model using Precision@10, tries four sets of ensemble weights, and writes recommendation lists to output.csv. The saved output shows 987,961 training ratings and 6,037 validation rows.

## Results shown in the notebook

| Method | Precision@10 |
| --- | ---: |
| SVD | 0.0030 |
| Item based KNN | 0.0006 |
| NMF | 0.0005 |
| Selected ensemble, weights 0.5 / 0.4 / 0.1 | 0.0033 |

The displayed ensemble score is 10% higher than the displayed SVD score in relative terms. The weights were chosen on the same validation split used for the table. These are not independent test results.

## Running the notebook

Open the notebook in Colab and run the cells in order. It installs numpy<2 and scikit-surprise and uses pandas, NumPy, Matplotlib, Seaborn, and tqdm.

The repository does not contain train.csv, val.csv, movies.dat, or users.dat. Place the corresponding files in the Colab working directory before running the data loading cell. The saved outputs document an earlier run; the repository alone is not enough to reproduce that run.

The method and figures above come from the [notebook code and saved outputs](Ensemble_Recommendation_System.ipynb).
