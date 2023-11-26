> Reduce the dimensionality of feature vector

## The curse of Dimensionality

- Classifier cannot discriminate with small number of feature dimensions 
- Adding data become 'sparse' with more feature dimensions
- Causing overfitting
- Amount of data must increase exponentially to keep generalisation constant (Called curse of dimensionality)
- Increased computation

There is likely to be optimum number of features that gives the lowest classification error.


### Implication for image

Even the smallest of real world images are of size - 256 x 256 = 65536 features
=> Reduce dimensionality

## PCA
> Mathematically defined as an orthogonal linear transformation that transforms the data to a new coordinate system such that the retained sample variance is maximised

PCA of any distribution can be found by obtaining the eigen-vectors of the sample covariance matrix

Advantage: Lower Dimensionality representation of the sample distribution can be obtained

## Sample Covariance matrix

- It can be obtained from 2D Gaussian Matrix
- 