# Data Science Labs

Ten Jupyter notebooks written for a Data Science / Machine Learning lab course
(R3AI, 2026). Each notebook is self-contained: it loads a CSV from this repo,
preprocesses it, trains one model, and evaluates the result with plots and
metrics. They are coursework — the goal was to implement each algorithm
explicitly and explain it, not to squeeze out the best possible score.

## Experiments

| Notebook | Dataset | Algorithm / topic |
|---|---|---|
| `Online_Retail_Preprocessing.ipynb` | `Online Retail.csv` | Data cleaning: missing values, cancelled orders, returns, feature construction |
| `Heart_Linear_Regression.ipynb` | `heart.csv` | Simple linear regression: `age` → maximum heart rate (`thalach`) |
| `Diabetes_Logistic_Regression.ipynb` | `diabetes.csv` | Logistic regression for diabetes outcome from 8 diagnostic features |
| `Decision_Tree_Play_Tennis.ipynb` | `play_tennis_dataset.csv` | ID3 decision tree from scratch, entropy and information gain, tree plot |
| `Iris_KMeans_Clustering.ipynb` | `iris.csv` | K-Means clustering (species label dropped) with elbow plot |
| `XOR_ANN_Backpropagation.ipynb` | generated | ANN with hand-written forward and backward passes to learn XOR |
| `Iris_MLP_Classification.ipynb` | `iris.csv` | scikit-learn MLP classifier, train/test split, confusion matrix |
| `Spam_Naive_Bayes.ipynb` | `spam.csv` | Multinomial Naive Bayes over TF-IDF text features |
| `Titanic_Random_Forest.ipynb` | `titanic.csv` | Random Forest survival classifier with feature selection |
| `Iris_AdaBoost_Ensemble.ipynb` | `iris.csv` | AdaBoost with decision-stump weak learners |

## Run the notebooks

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

All CSVs sit next to the notebooks, so no download step is needed. Every
notebook was executed before committing, and the saved outputs are included so
the plots and metrics are visible without running anything.

## Dataset provenance

The CSVs are copies of public datasets, redistributed here so the notebooks run
offline. Each keeps its original licence; the MIT licence in this repo covers
the notebook code only.

| File | Source | Notes |
|---|---|---|
| `iris.csv` | [UCI Iris](https://archive.ics.uci.edu/dataset/53/iris) | 150 rows, 4 features, 3 classes |
| `diabetes.csv` | [Pima Indians Diabetes](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database) (UCI data, Kaggle mirror) | 768 rows, 8 features |
| `heart.csv` | [UCI Heart Disease](https://archive.ics.uci.edu/dataset/45/heart+disease) (Kaggle mirror) | 303 rows, Cleveland features, binarised `target` |
| `titanic.csv` | [Kaggle Titanic](https://www.kaggle.com/competitions/titanic) | 891 labelled passengers |
| `spam.csv` | [UCI SMS Spam Collection](https://archive.ics.uci.edu/dataset/228/sms+spam+collection) | 5,572 labelled messages |
| `Online Retail.csv` | [UCI Online Retail](https://archive.ics.uci.edu/dataset/352/online+retail) | Transaction-level e-commerce data |
| `play_tennis_dataset.csv` | Classic Quinlan teaching example | 14 rows, categorical |

These datasets are used for educational purposes. If you reuse them, follow the
terms of the original source rather than this repository's MIT licence.

## Notes and limits

- `Decision_Tree_Play_Tennis` implements ID3 by hand over 14 examples; it is a
  teaching implementation, not a general-purpose tree.
- `XOR_ANN_Backpropagation` uses a tiny hand-rolled network and fixed
  hyperparameters; results depend on the random seed.
- The retail notebook is preprocessing only — there is no model.
- Scores are reported as they were in the lab sessions; no attempt was made to
  tune them for publication.
