> Handling missing data

## Mark Missing Values

- Missing values are out-of-range entries such as negative number, zero. This need to be considered based on domain knowledge
-  We can mark those values by `NaN` using pandas `replace()`, so that they are not counted in arithmetic operation.
- Get count of `NaN` to understand how many missing values collectively

## Missing values causes problems in algorithms

- For eg, Linear Discriminant Analysis (LDA) doesn't allow missing values in the dataset

## Remove rows with missing values
> Simplest approach

- Pandas `dropna()` method used to drop rows/columns having missing values

## Impute missing values
> Using model to replace values

Many ways to replace missing values:
1. A constant values, which has meaning within the domain like 0/
2. A random value from the selected record
3. A mean/median/mode for the column
4. A value estimated by another predictive model

- Pandas `fillna()` to replace missing values.
- The scikit-learn library provides the `SimpleImputer pre-processing`class that can be used to replace missing values.

```
# retrieve the numpy array

values = dataset.values

# define the imputer

imputer = SimpleImputer(missing_values=nan, strategy='mean')

# transform the dataset

transformed_values = imputer.fit_transform(values)

```

## Algorithms that support missing values

1. k-Nearest Neighbours
2. Naive Bayes Classifier
 however, scikit-learn version is not implemented to support missing values

