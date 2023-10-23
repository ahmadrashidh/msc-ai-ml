> Feature selection/dimensionality reduction on sample sets is either to improve estimators’ accuracy scores or to boost their performance on very high-dimensional datasets.

## Removing features with low variance

Any feature which has variance less than the variance threshold will be removed

Var(X) = p(1-p)

## Univariate feature selection

Feature Selection Routines:

1. Removes all but the k highest scoring features - `SelectKBest` in `scikitlearn`
2. Removes all but a user-specified highest scoring percentage for features - `SelectPercentile`
3. Using common univariate statistical tests for each feature
	1. False Positive Rate - `SelectFpr`
	2. False Discovery Rate - `SelectFdr`
	3. Family Wise Error - `SelectFwe`
4. Perform univariate feature selection with a configurable strategy. This allows to select the best univariate selection strategy with hyper-parameter search estimator - `GenericUnivariateSelect`

## Recursive Feature Elimination

- Given Feature Estimator with weighted coefficient, recursively, least important features are pruned from current set of features.


