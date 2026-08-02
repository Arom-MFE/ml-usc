# ml-usc

Eight machine learning projects, each a standalone Jupyter notebook with its own data. The work comes from Machine Learning for Data Science, a graduate course at USC. Methods run from k-nearest neighbours through transfer learning with pretrained convolutional networks; every project covers data preparation, model selection and evaluation on a public dataset.

## Projects

| # | Project | Methods | Key result |
|---|---------|---------|------------|
| 01 | [KNN and Distance Metrics](01-knn-distance-metrics/knn_distance_metrics.ipynb) | KNeighborsClassifier; Euclidean, Manhattan, Minkowski, Chebyshev and Mahalanobis metrics; distance-weighted voting | Test error 0.06 at k = 4; the worst metric, Mahalanobis, sits at 0.17 on the same split |
| 02 | [Linear Regression on Power Plant Output](02-linear-regression/linear_regression_power_output.ipynb) | statsmodels OLS, polynomial and interaction terms, backward elimination on p-values, KNeighborsRegressor | KNN on normalized features reaches test MSE 14.29 against 21.24 for the four-predictor OLS baseline |
| 03 | [Time Series Activity Classification](03-time-series-classification/time_series_activity_classification.ipynb) | Time-domain features, LogisticRegression with RFECV, L1-penalized LogisticRegressionCV, GaussianNB, MultinomialNB | Seven-class test accuracy 0.842; the binary bending detector classifies the test set exactly |
| 04 | [Regularization and Decision Trees](04-regularization-and-trees/regularization_and_decision_trees.ipynb) | DecisionTreeClassifier with cost-complexity pruning, RidgeCV, LassoCV, principal component regression, XGBRegressor | Ridge posts the lowest test MSE, 0.01732, across six models on 122 crime predictors |
| 05 | [Imbalanced Classification with SMOTE](05-imbalanced-classification/imbalanced_classification_smote.ipynb) | RandomForestClassifier, balanced class weights, XGBClassifier with L1 penalty, SMOTE | Class weighting cuts missed failures on the test set from 121 to 35 of 375 |
| 06 | [Multi-Label SVM and K-Means Clustering](06-multilabel-svm-clustering/multilabel_svm_and_kmeans.ipynb) | Gaussian-kernel SVC one-vs-all, L1-penalized LinearSVC, SMOTE, KMeans with silhouette selection | 98.75% exact match across family, genus and species on held-out frog calls |
| 07 | [Semi-Supervised and Active Learning](07-semi-supervised-active-learning/semi_supervised_and_active_learning.ipynb) | L1-penalized LinearSVC, self-training, KMeans, SpectralClustering, margin-based active learning | Supervised SVM averages 0.9708 test accuracy over 30 splits; k-means and spectral clustering stall near 0.88 |
| 08 | [Transfer Learning for Fungi Image Classification](08-transfer-learning-cnn/transfer_learning_fungi_classification.ipynb) | Frozen ImageNet backbones: ResNet50, ResNet101, EfficientNetB0, VGG16, DenseNet201 | ResNet101 leads the five backbones at 0.8476 test accuracy on 912 held-out images |

## Repository layout

Each project is self-contained: one notebook plus the data it reads.

```
01-knn-distance-metrics/             knn_distance_metrics.ipynb                     data/
02-linear-regression/                linear_regression_power_output.ipynb           data/
03-time-series-classification/       time_series_activity_classification.ipynb      data/
04-regularization-and-trees/         regularization_and_decision_trees.ipynb        data/
05-imbalanced-classification/        imbalanced_classification_smote.ipynb          data/
06-multilabel-svm-clustering/        multilabel_svm_and_kmeans.ipynb                data/
07-semi-supervised-active-learning/  semi_supervised_and_active_learning.ipynb      data/
08-transfer-learning-cnn/            transfer_learning_fungi_classification.ipynb   data/
requirements.txt
```

## Running the notebooks

- `pip install -r requirements.txt`. Versions are unpinned; the notebooks were written across several Python versions.
- Start each notebook from its own project directory. Data paths are relative to it; a kernel launched at the repo root will not find the data.
- All data is committed, including the 9,114 fungi images in project 08. Expect a checkout of roughly 250 MB.

## Data

All datasets come from the UCI Machine Learning Repository and are included in the repo; each notebook's header links its dataset's UCI page.
